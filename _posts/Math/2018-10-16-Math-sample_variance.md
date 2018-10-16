---
layout: post
title: 표본분산과 자유도(n - 1)
category: [Math]
tags: [Math, 표본분산, 자유도, n - 1]
published: true
comments: true
---

표본분산과 자유도(n - 1)
----------------

1. 평균
\\( \mu = \frac{\sum\_{k=1}^{n}}{n} \\)

2. 분산
\\( \sigma^2 = \frac{\sum\_{k=1}^{n} (X\_k -\mu)^2}{n} \\)

3. 표본평균의 평균
\\( \begin{align} 
        \bar{X}\_\bar{X} & = E(\bar{X}) 
\\\\ & = E(\sum\_{k=1}^{n} \frac{X\_k}{n}) 
\\\\ & = E\[ \frac{X\_1 + X\_2 + \ldots + X\_n}{n}\] 
\\\\ & = E(\frac{1}{n}X\_1) + E(\frac{1}{n}X\_2) + \ldots + E(\frac{1}{n}X\_n) 
\\\\ & = \frac{1}{n}\mu\_x + \frac{1}{n}\mu\_x + \ldots + \frac{1}{n}\mu\_x 
\\\\ & = \mu\_x 
\end{align} \\)

4. 표본평균의 분산
\\( \begin{align} 
        \sigma\_\bar{X}^2 & = Var(\bar{X}) 
\\\\ & = Var(\frac{X\_1 + X\_2 + \ldots + X\_n}{n})
\\\\ & = Var(\frac{1}{n}X\_1) + Var(\frac{1}{n}X\_2) + \ldots + Var(\frac{1}{n}X\_n)
\\\\ & = (\frac{1}{n})^2Var(X\_1) + (\frac{1}{n})^2Var(X\_2) + \ldots + (\frac{1}{n})^2Var(X\_n)
\\\\ & = n (\frac{1}{n})^2 Var(X)
\\\\ & = \frac{Var(X)}{n}
\\\\ & = \frac{\sigma^2}{n}
\end{align} \\)

5. 표본평균의 표준편차
\\( \begin{align} 
        \sigma\_\bar{X} & = \frac{\sqrt{Var(\bar{X})}}{\sqrt{n}}
\\\\ & = \frac{\sigma}{\sqrt{n}}
\end{align} \\)

6. 표본분산
\\( \begin{align} 
        s^2 & = E\[(X-\bar{X})^2\] 
\\\\ & = E\[\{(X - \mu) + (\mu - \bar{X})\}^2\]
\\\\ & = \frac{1}{n} \sum\_{k=1}^{n}(X\_k - \bar{X})^2 
\\\\ & = \frac{1}{n} \sum\_{k=1}^{n} \[(X\_k - \mu) + (\mu - \bar{X})\]^2
\\\\ & = \frac{1}{n} \[ \sum\_{k=1}^{n}(X\_k - \mu)^2 + 2(\mu - \bar{X})n(\bar{X} - \mu) + n(\mu - \bar{X})^2 \]
\\\\ & = \frac{1}{n} \[ \sum\_{k=1}^{n}(X\_k - \mu)^2 - 2n(\mu - \bar{X})^2 + n(\mu - \bar{X})^2 \]
\\\\ & = \frac{1}{n} \[ \sum\_{k=1}^{n}(X\_k - \mu)^2 - n(\bar{X} - \mu)^2 \]
\\\\ & = \sigma^2 - \frac{\sigma^2}{n}
\\\\ & = \frac{(n - 1)}{n} \sigma^2
\end{align} \\) 

즉, 
\\( \sigma^2} = \frac{n}{n - 1} s^2 \\)
