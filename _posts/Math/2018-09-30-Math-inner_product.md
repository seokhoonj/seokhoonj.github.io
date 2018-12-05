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
$$ \vec{a} \cdot \vec{b} = \|\vec{a}\| \times \|\vec{b}\| \times \cos\theta = \|\vec{b}\| \times \|\vec{a}\| \times \cos\theta \\
$$ \vec{a} \cdot \vec{b} = \sqrt{\sum\_{i=1}^{D} a\_i^2} \times \sqrt{\sum\_{i=1}^{D} b\_i^2} \times \cos\theta = \sqrt{a^T a} \times \sqrt{b^T b} \times \cos{\theta} \\ $$
$$ \vec{a} \cdot \vec{b} = a\_1 b\_1 + a\_2 b\_2 + \ldots + a\_D b\_D = \sum\_{i=1}^{D} a\_i b\_i = \left(\begin{array}{cccc} a\_1 & a\_2 & \ldots & a\_D \end{array}\right) \left(\begin{array}{c} b\_1 \\\\ b\_2 \\\\ \vdots \\\\ b\_D \end{array}\right) = a^T b \\ $$
$$ \cos{\theta} = \frac{a^T b}{\sqrt{a^T a} \times \sqrt{b^T b}} \approx \rho (correlation) $$

## 코사인 법칙
$$ a = c \cdot \cos{B} + b \cdot \cos{C} $$
