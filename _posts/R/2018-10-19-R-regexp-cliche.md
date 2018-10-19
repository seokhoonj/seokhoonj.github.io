---
layout: post
title: R 정규표현식 - 자주 쓰는 표현
category: R
tags: [R, 정규표현식]
published: false
comments: false
---

R 정규표현식 - 자주 쓰는 표현
---

데이터 분석시 데이터의 유효성에 대한 검증 차원에서 몇 가지 process를 모아보고자 한다.


1. 생년월일(1900년 이전 출생이 없다고 가정한다면) 

``` r
dob <- c("19980102", "20071230", "20172130")
pattern <- "^[19|20]{2}[0-9]{2}[0-1]{1}[0-9]{1}[0-3]{1}[0-9]{1}$"
```

to be continued...  
