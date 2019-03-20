---
layout: post
title: R microbenchmark
category: R
tags: [R, microbenchmark]
published: true
comments: true
---

microbenchmark 활용법
-------------

실무에서 활용하는 데이터의 크기가 커지면서 여러가지 문제가 발생하게 되는데,  
그 중에서 가장 껄끄러운 문제가 속도 문제가 아닌가 싶다.  
이를 해결하기 위해 주로 system.time을 이용해 속도를 측정하고 수정하는 작업을 해왔는데,  
Olaf Mersmann이라는 분의 microbenchmark라는 패키지가 상당히 많이 사용되고 있는 듯 하다.  

간단히 테스트 해보자.

``` r
# add memory subsequently
method1 = function(n) {
  vec = NULL
  for (i in seq_len(n)) {
    vec = c(vec, i)
  }
  vec
}

# allocate memories in advance
method2 = function(n) {
  vec = numeric(n)
  for (i in seq_len(n)) {
    vec[i] = i
  }
  vec
}

# directly
method3 = function(n) seq_len(n)

microbenchmark(method1(100), method2(100), method3(100))
```

결과는 다음과 같다.

```r
Unit: nanoseconds
         expr   min      lq     mean  median    uq   max neval cld
 method1(100) 22231 24192.0 26385.17 24949.5 25765 94313   100   c
 method2(100)  5118  5436.5  5808.67  5552.5  5727 22892   100  b
 method3(100)   227   311.0   417.96   374.0   443  4464   100 a 
```
