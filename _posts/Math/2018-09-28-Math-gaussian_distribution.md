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

## 연속 변수로 이루어진 D차원 벡터 x에 대한 가우시안 분포
\\( N(x\|\mu, \Sigma) = \frac{1}{(2\pi)^{D/2}}\frac{1}{\|\Sigma\|^{1/2}} exp\left\lbrace-\frac{1}{2}(x-\mu)^T\Sigma^{-1}(x-\mu)\right\rbrace \\)
