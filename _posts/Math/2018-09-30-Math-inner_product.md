---
layout: post
title: 벡터의 내적
category: Math
tags: [Math, 벡터, 내적]
published: true
comments: true
---

벡터의 내적
---

## 벡터의 내적
$$ \vec{a} \cdot \vec{b} = \|\vec{a}\| \times \|\vec{b}\| \times \cos\theta = \|\vec{b}\| \times \|\vec{a}\| \times \cos\theta \\ $$
$$ \vec{a} \cdot \vec{b} = \sqrt{\displaystyle\sum_{i=1}^{D} a_i^2} \times \sqrt{\displaystyle\sum_{i=1}^{D} b\_i^2} \times \cos\theta = \sqrt{a^T a} \times \sqrt{b^T b} \times \cos{\theta} \\ $$
$$ \vec{a} \cdot \vec{b} = a_1 b_1 + a_2 b_2 + \ldots + a_D b_D = \displaystyle\sum_{i=1}^{D} a_i b_i = \left(\begin{array}{cccc} a_1 & a_2 & \ldots & a_D \end{array}\right) \left(\begin{array}{c} b_1 \\ b_2 \\ \vdots \\ b_D \end{array}\right) = a^T b \\ $$
$$ \cos{\theta} = \frac{a^T b}{\sqrt{a^T a} \times \sqrt{b^T b}} \approx \rho (correlation) $$

## 코사인 법칙
$$ a = c \cdot \cos{B} + b \cdot \cos{C} $$
