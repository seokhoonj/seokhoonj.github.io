---
layout: post
title: 정규분포의 유도
category: Math
tags: [Math, 정규분포]
published: true
comments: false
---

정규분포의 유도
---


## 정규 분포 \(Normal Distribution\) 

\\( f(x) = \frac{1}{\sqrt{2\pi}\sigma} e^{-\frac{(x-m)^2}{2\sigma^2}} \\)

## 가우스 적분 \(Gaussian Integrals\)

1. 다음 함수를 적분해보자.
\\( \int\_{-\infty}^{+\infty} e^{-x^2} dx = ? \\)

2. 바로 적분이 불가능하므로 양 변을 제곱하는 식으로 문제를 변형해보자.
\\( \left[ \int\_{-\infty}^{+\infty} e^{-x^2} dx \right]^2 = \\int\_{-\infty}^{+\infty} e^{-x^2} dx \int\_{-\infty}^{+\infty} e^{-y^2} dy \\)
\\( \int\_{-\infty}^{+\infty}\int\_{-\infty}^{+\infty} e^{-x^2} e^{-y^2} dx dy = \int\_{-\infty}^{+\infty}\int\_{-\infty}^{+\infty} e^{-(x^2+y^2)} dx dy  \\)

3. 이 식을 극좌표<sup>1<\\sup>로 변환해보자.
\\( \int\_{R^2}^{} e^{-(x^2+y^2)} dx dy = \int\_{\theta=0}^{2\pi}\int\_{r=0}^{\infty} re^{-r^2} dr d\theta \\)
 - r 과 관련된 부분부터 적분을 하면, 
\\( \int\_{r=0}^{\infty} re^{-r^2} dr = -\frac{1}{2} \int\_{r=0}^{\infty} -2re^{-r^2} dr = -\frac{1}{2}[e^{-r^2}]\_{r=0}^{\infty} = -\frac{1}{2}[e^{-\infty^2} - e^{-0^2}] = -\frac{1}{2}[0-1] = \frac{1}{2} \\) 
 - 이제 상기 결과를 토대로 $\theta$ 부분을 적분해 보자. 
\\( \int\_{\theta=0}^{2\pi} \frac{1}{2} d\theta = \left[\frac{1}{2}\theta \right]\_{\theta=0}^{2\pi} = [\pi-0] = \pi \\)

4. 최종 결과는 다음과 같다.
\\( \int\_{-\infty}^{+\infty} e^{-x^2} dx = \sqrt{\pi} \\)
