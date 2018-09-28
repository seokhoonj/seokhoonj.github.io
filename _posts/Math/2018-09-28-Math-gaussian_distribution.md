---
layout: post
title: 가우시안 분포
category: Math
tags: [Math, 가우시안 분포]
published: true
comments: false
---

가우시안 분포 (정규 분포)
---

## 단일 실수 변수 $x$에 대한 가우시안 분포
\\( N(x\|\mu, \sigma^2) = \frac{1}{(2\pi\sigma)^{1/2}} exp\left\lbrace-\frac{1}{2\sigma^2}(x-\mu)^2\right\rbrace \\)
1. 상기 식은 두 개의 매개변수 $\mu$와 $\sigma^2$에 의해 통제된다.
2. 

\\( y(x, w) = w\_0 + w\_1x\_1 + ... + w\_Dx\_D  = \left(\begin{array}{ccc} w\_0 & w\_1 & \ldots & w\_D \end{array}\right) \left(\begin{array}{c} 1 \\\\ x\_1 \\\\ \vdots \\\\ x\_D \end{array}\right) = w^T x \\)
\\( y(x, w) = w\_0 + \sum\_{j=1}^{M-1} w\_j\phi\_j(x) \\)
 \\( y(x, w) = \sum\_{j=1}^{M-1} w\_j\phi\_j(x) = w^T \phi(x) \\)
 \\( \phi\_j(x) = exp\left\lbrace-\frac{(x-\mu\_j)^2}{2s^2}\right\rbrace  = exp\left\lbrace-\frac{1}{2}\left(\frac{x-\mu\_j}{s}\right)^2\right\rbrace = e^{-\frac{1}{2}z^2} \\) 
