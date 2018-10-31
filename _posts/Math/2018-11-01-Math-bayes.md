---
layout: post
title: Bayesian Probability
category: [Math]
tags: [Math, Bayesian]
published: true
comments: true
---

Bayesian Probability
----------------

H: 가설(Hypothesis)  
D: 데이터(Data)  
P(H): 사전확률(Priori), Data가 보이기 전 (즉, 관측전)의 Hypothesis가 참일 확률  
P(D|H): 가능도(Likelihood), Hypothesis가 참일 때, Data를 보게 될 조건부 확률  
P(D): Data의 사전확률   
P(H|D): 사후확률(Posterior), Data가 보이고 나서의 Hypothesis가 참일 조건부 확률  


\\( P(H|D) = \frac{P(D|H)P(H)}{P(D)} \\)
\\( \text{데이터가 발견된 상태에서 가설이 참일 확률} = \frac{\text{가설이 참일 때 데이터가 발견될 확률} \times \text{가설이 참일 확률}}{\text{데이터가 발견될 확률}} \\)

\\( P(H|D)P(D) = P(D|H)P(H) \\)
\\( \text{데이터가 발견된 상태에서 가설이 참일 확률} \times \text{데이터가 발견될 확률} = \text{가설이 참일 때 데이터가 발견될 확률} \times \text{가설이 참일 확률} \\)

ref.
\\( \begin{align} 
  P(H) = P(H|A)P(A) + P(H|B)P(B)
\\\\ & = \frac{P(A|H)P(H)}{P(A)}P(A) + \frac{P(B|H)P(H)}{P(B)}P(B) 
\\\\ & = P(A|H)P(H) + P(B|H)P(H)
\\\\ & = \frac{P(H|A)P(A)}{P(H)}P(H) + \frac{P(H|B)P(B)}{P(H)}P(H)
\\\\ & = P(H|A)P(A) + P(H|B)P(B)
\end{align} \\)
