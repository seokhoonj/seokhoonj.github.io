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
	\frac{\partial}{\partial \beta} S = -2 X^T Y + 2 X^T X \beta = 0
	\end{align} $$

$$ \beta $$의 최소제곱추정량 $$\hat{\beta}$$  

<center> $$ (X^T X) \beta = X^T Y $$, 를 만족시키는 $$ \beta $$를 $$ \hat{\beta} $$으로 표현하면,  </center>
	
$$ \begin{align} \hat{\beta} = (X^T X)^{-1} X^T Y \end{align} $$

ref 1)  
$$ k \times k $$ 대칭행렬 $$ A $$ 에 대하여 해당 행렬은 $$ 1 \times 1 $$ 행렬이므로,  
$$ (Y^T A \beta)^T = \beta^T A^T Y $$  

ref 2)  
이차형식의 미분: 벡터 $$ \alpha = (\alpha_1, \cdots, \alpha_n)^T $$ 이고 $$ k \times k $$ 행렬 $$ A $$에 대하여,  
$$ \alpha^T A \alpha $$ 를 $$ \alpha $$의 2차 형식이라 한다. 이 때,  
$$  \begin{align}
	\frac{\partial}{\partial \alpha} (\alpha^T A \alpha) = 2A \alpha
	\end{align} $$
