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
2. $\mu$는 평균, $\sigma^2$은 분산, $\sigma$는 표준편차, $\beta = \frac{1}{\sigma^2}$는 <strong><em>정밀도(precision)</em></strong>라고 한다. \(정밀도의 개념 알아보기.\)

## 가우시안 분포의 정규화

## 가우시안 분포의 기댓값

## 연속 변수로 이루어진 $D$차원 벡터 $x$에 대한 가우시안 분포
\\( N(x\|\mu, \Sigma) = \frac{1}{(2\pi)^{D/2}}\frac{1}{\|\Sigma\|^{1/2}} exp\left\lbrace-\frac{1}{2}(x-\mu)^T\Sigma^{-1}(x-\mu)\right\rbrace \\)
1. $x = (\begin{array}{ccc} x\_1 & \ldots & x\_n \end{array})^T \text{: } D \times 1 \text{행렬}$
2. $\mu = (\begin{array}{ccc} \mu\_1 & \ldots & \mu\_n \end{array})^T \text{: } D \times 1 \text{행렬}$ ($x$ 행렬로 부터 $\mu$ 행렬을 구하는 방법)
3. $\Sigma \text{: } D \times D \text{ 공분산 행렬}$
4. $\Sigma^{-1} \text{: } D \times D \text{ 공분산 행렬의 역행렬}$
5. $\|\Sigma\| \text{: 공분산 행렬의 행렬식}$ 

## 관측된 데이터 $x$ 
\\( \boldsymbol{x} = (\begin{array}{ccc} x\_1 & \ldots & x\_N \end{array})^T \\)

