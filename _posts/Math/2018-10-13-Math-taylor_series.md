---
layout: post
title: 테일러 급수
category: Math
tags: [Math, 테일러급수, taylor series]
published: true
comments: false
---

테일러 급수 (Taylor Series)
---

다항함수
\\( f(x) = c\_0 + c\_1(x-a) + c\_2(x-a)^2 + c\_3(x-a)^3 + \ldots + c\_n(x-a)^n + \ldots \\)

\\( \begin{cases} 
     f^{(0)}(x) = 0!c\_0 + \ldots
\\\\ f^{(1)}(x) = 1!c\_1 + 2 \times 1 c\_2(x-a) + 3c\_3(x-a)^2 + \ldots + nc\_n(x-a)^{n-1} + \ldots
\\\\ f^{(2)}(x) = 2!c\_2 + 3 \times 2 c\_3(x-a) + \ldots
\\\\ f^{(3)}(x) = 3!c\_3 + \ldots
\\\\ \vdots
\end{cases} \\)

\\( \therefore c\_n = \frac{f^{(n)}(a)}{n!} \\)

즉,
\\( \therefore f(x) = \sum\_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!} (x-a)^n \\)

참고,
\\( f(x) - f(a) = \sum\_{n=1}^{\infty} \frac{f^{(n)}(a)}{n!} (x-a)^n \\)
