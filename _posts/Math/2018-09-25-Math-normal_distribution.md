---
layout: post
title: 정규분포의 유도
category: Math
tags: [Math, 정규분포]
published: true
comments: false
---

정규분포의 유도
-------------

정규분포(Normal distribution)  
\\( f(x) = \frac{1}{\sqrt{2\pi}\sigma} e^{-\frac{(x-m)^2}{2\sigma^2}} \\)

가우스적분(Gaussian integrals) 
1. 다음 함수를 적분해보자.
\\( \int\_{-\infty}^{+\infty} e^{-x^2} dx = \sqrt{\pi} \\)

2. 바로 적분이 불가능하므로 양 변을 제곱하는 식으로 문제를 변형해보자.
\\( \int\_{-\infty}^{+\infty}\int\_{-\infty}^{+\infty} e^{-x^2} e^{-y^2} dx dy = \pi \\)
\\( \int\_{-\infty}^{+\infty}\int\_{-\infty}^{+\infty} e^{-(x^2+y^2)} dx dy = \pi \\)

3. 이 식을 극좌표로 변환해보자.
\\( \int\_{R^2}^{} e^{-(x^2+y^2)} dx dy = \int\_{\theta=0}^{2\pi}\int\_{r=0}^{\infty} re^{-r^2} dr d\theta \-\-1) 주석 \\)
