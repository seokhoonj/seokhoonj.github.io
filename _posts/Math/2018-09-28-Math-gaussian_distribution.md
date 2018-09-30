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

## 관측된 데이터 집합 $X$ 
1. $X$의  notation
\\( \begin{pmatrix} x\_1^{(1)} & x\_2^{(1)} & \ldots & x\_D^{(1)} \\\\ x\_1^{(2)} & x\_2^{(2)} & \ldots & x\_D^{(2)} \\\\ \vdots & \vdots & \vdots & \vdots \\\\ x\_1^{(N)} & x\_2^{(N)} & \ldots & x\_D^{(N)} \end{pmatrix} = \left(\begin{array}{c} x^{(1)^T} \\\\ x^{(2)^T} \\\\ \vdots \\\\ x^{(N)^T} \end{array}\right) = \left(\begin{array}{cccc} x\_1 & x\_2 & \ldots & x\_D \end{array}\right) = X \\)
2. $X^T X$의 관측치 기준 notation ($D \times D$ 행렬)
\\( \begin{pmatrix} x\_1^{(1)} & x\_1^{(2)} & \ldots & x\_1^{(N)} \\\\ x\_2^{(1)} & x\_2^{(2)} & \ldots & x\_2^{(N)} \\\\ \vdots  & \vdots & \vdots & \vdots \\\\ x\_D^{(1)} & x\_D^{(2)} & \ldots & x\_D^{(N)} \end{pmatrix} \begin{pmatrix} x\_1^{(1)} & x\_2^{(1)} & \ldots & x\_D^{(1)} \\\\ x\_1^{(2)} & x\_2^{(2)} & \ldots & x\_D^{(2)} \\\\ \vdots  & \vdots  & \vdots & \vdots \\\\ x\_1^{(N)} & x\_2^{(N)} & \ldots & x\_D^{(N)} \end{pmatrix} = \left(\begin{array}{cccc} x^{(1)} & x^{(2)} & \ldots & x^{(N)} \end{array}\right) \left(\begin{array}{c} x^{(1)^T} \\\\ x^{(2)^T} \\\\ \vdots \\\\ x^{(N)^T} \end{array}\right) = X^T X \\) 
3. $X^T X$의 feature 기준 notation ($D \times D$ 행렬)
\\( \begin{pmatrix} x\_1^{(1)} & x\_1^{(2)} & \ldots & x\_1^{(N)} \\\\ x\_2^{(1)} & x\_2^{(2)} & \ldots & x\_2^{(N)} \\\\ \vdots & \vdots & \vdots & \vdots \\\\ x\_D^{(1)} & x\_D^{(2)} & \ldots & x\_D^{(N)} \end{pmatrix} \begin{pmatrix} x\_1^{(1)} & x\_2^{(1)} & \ldots & x\_D^{(1)} \\\\ x\_1^{(2)} & x\_2^{(2)} & \ldots & x\_D^{(2)} \\\\ \vdots  & \vdots  & \vdots & \vdots \\\\ x\_1^{(N)} & x\_2^{(N)} & \ldots & x\_D^{(N)} \end{pmatrix} = \left(\begin{array}{c} x\_1^T \\\\ x\_2^T \\\\ \vdots \\\\ x\_D^T \end{array}\right) \left(\begin{array}{cccc} x\_1 & x\_2 & \ldots & x\_D \end{array}\right) = X^T X \\) 
4. $\mu$의 notation ($D \times D$ 행렬)
\\( \begin{pmatrix} x\_1^{(1)} & x\_1^{(2)} & \ldots & x\_1^{(N)} \\\\ x\_2^{(1)} & x\_2^{(2)} & \ldots & x\_2^{(N)} \\\\ \vdots  & \vdots & \vdots & \vdots \\\\ x\_D^{(1)} & x\_D^{(2)} & \ldots & x\_D^{(N)} \end{pmatrix} \left(\begin{array}{c} \frac{1}{N} \\\\ \frac{1}{N} \\\\ \vdots \\\\ \frac{1}{N} \end{array}\right) = \left(\begin{array}{c} \mu\_1 \\\\ \mu\_2 \\\\ \vdots \\\\ \mu\_D \end{array}\right) \\)
5. $(x^{(1)} - \mu)$의 notation ($D \times D$ 행렬)
\\( \left(\begin{array}{c} x\_1^{(1)} \\\\ x\_2^{(1)} \\\\ \vdots \\\\ x\_D^{(1)} \end{array}\right) - \left(\begin{array}{c} \mu\_1 \\\\ \mu\_2 \\\\ \vdots \\\\ \mu\_D \end{array}\right) = \left(\begin{array}{c} x\_1^{(1)}-\mu\_1 \\\\ x\_2^{(1)}-\mu\_2 \\\\ \vdots \\\\ x\_D^{(1)}-\mu\_D \end{array}\right) \\)
6. $(x^{(1)} - \mu)^T (x^{(1)} - \mu)$의 notation
\\( \left(\begin{array}{cccc} x\_1^{(1)}-\mu\_1 & x\_2^{(1)}-\mu\_2 & \ldots & x\_D^{(1)}-\mu\_D \end{array}\right) \left(\begin{array}{c} x\_1^{(1)}-\mu\_1 \\\\ x\_2^{(1)}-\mu\_2 \\\\ \vdots \\\\ x\_D^{(1)}-\mu\_D \end{array}\right) = (x^{(1)} - \mu)^T (x^{(1)} - \mu) = \sum\_{i=1}^{D} (x\_i^{(1)} - \mu\_i)^2 \\)
 - $\sqrt{\sum\_{i=1}^{D} (x\_i^{(1)} - \mu\_i)^2}$는 두 벡터의 유클리드 거리이다. (벡터 $x^{(j)}$와 벡터 $\mu$의 거리)
 - 일변량 함수의 경우 $\frac{(x^{(1)}-\mu)^2}{\sigma^2}$로 표현되는 것이 $(x^{(1)} - \mu)^T \Sigma^{-1} (x^{(1)} - \mu)$로 변경
 - 일변량 함수의 경우 $(x^{(1)} - \mu)^2$으로 평균과의 떨어진 거리를 계산하고 $\sigma^2$으로 나누어 길이를 선형변환 한다. 
 - 마찬가지로, 다변량의 경우에는 $\Sigma$를 기저벡터로 선형변환시키는 $\Sigma^{-1}$를 활용하여 $\x^{(j)} - \mu$벡터를 선형변환한다. 
 - 예를 들어, $X^T X$가 공분산행렬이라면 $(X^T X)^{-1}$는 공분산행렬의 역행렬이 될 것이고 $(x^{(j)} - \mu)^T (X^T X)^{-1} (x^{(j)} - \mu)$
