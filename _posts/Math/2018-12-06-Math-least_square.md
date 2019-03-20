---
layout: post
title: 최소제곱법
category: Math
tags: [Math, 최소제곱법, least square]
published: true
comments: true
---

최소제곱법을 이용한 다중회귀분석 풀이
---

OLS notation  

$$ \begin{align} 
	S &= \varepsilon^T \varepsilon \\
	&= (Y - X\beta)^T(Y - X\beta) \\
	&= Y^T Y - Y^T X \beta - \beta^TX^T Y + \beta^TX^T X \beta \\
	&= Y^T Y - 2 \beta^T X^T Y + \beta^T X^T X \beta 
	\end{align} $$

미분을 이용한 최솟값 정의  

$$  \begin{align}
	\frac{\partial}{\partial \beta} S = -2 X^T Y + 2 X^T X \beta
	\end{align} $$

$$beta$$의 최소제곱추정량 $$\hat{\beta}$$  

$$ \begin{align} (X^T X) \beta = X^T Y, 를 만족시키는 \beta를 \hat{\beta}으로 표현하면,  \end{align} $$
	
$$ \begin{align} \hat{\beta} = (X^T X)^{-1} X^T Y \end{align} $$
