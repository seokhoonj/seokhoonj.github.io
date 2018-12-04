---
layout: post
title: 코시-슈바르츠 부등식(cauchy-schwartz inequality)
category: Math
tags: [Math, 코시-슈바르츠, cauchy-schwartz]
published: true
comments: true
---

코시-슈바르츠 부등식 (cauchy-schwartz inequality) 증명
---

### 두 벡터의 내적의 절대값은 두 벡터의 길이의 곱보다 작거나 같다.
$$ \vec{x}, \vec{y} \in \mathbb{R}^n \text{(, non-zero vector)} $$
$$ | \vec{x} \cdot \vec{y} | \leq \| \vec{x} \| \| \vec{y}\| $$

### 벡터 x가 벡터 y의 스칼라배인 경우에만(즉, 동일선상에 있는 경우에만) 등호가 성립한다.
$$ | \vec{x} \cdot \vec{y} | = \| \vec{x} \| \| \vec{y}\| \Longleftrightarrow \vec{x} = c \vec{y} $$

### 벡터의 길이와 그 제곱은 다음과 같다.
$$ \| \vec{v} \| = \sqrt{v_1^2 + v_2^2 + \cdots + v_n^2} \geq 0 $$
$$ \| \vec{v} \|^2 = \vec{v} \cdot \vec{v} $$
$$  \|v\|^2\|w\|^2  \geq |v \cdot w|^2 $$
$$ \begin{align}
     p(t) & = \| t \vec{y} - \vec{x} \|^2 ( \geq 0 ) \\
            & = (t \vec{y} - \vec{x}) \cdot (t \vec{y} - \vec{x} ) \\
            & =  t \vec{y} \cdot t \vec{y} - \vec{x} \cdot t \vec{y} - t \vec{y} \cdot \vec{x} + \vec{x} \cdot \vec{x} \\
            & = ( \vec{y} \cdot \vec{y} ) t^2 - 2(\vec{x} \cdot \vec{y})t + \vec{x} \cdot \vec{x} \geq 0 \\
\end{align}$$

### 계산을 간단히 하기위해 치환하면, 
$$ p(t) = at^2 -bt + c \geq 0 $$

### $$ t $$ 에 $$ \frac{a}{2a} $$를 대입하면,
$$ \begin{align}
p( \frac{b}{2a} ) & = a \frac{b^2}{4a^2} - b \frac{b}{2a} + c \geq 0 \\
                             & \Leftrightarrow \frac{b^2}{4a} - \frac{2b^2}{4a} + c \geq 0 \\
                             & \Leftrightarrow - \frac{b^2}{4a} + c \geq 0 \\
                             & \Leftrightarrow 4ac \geq b^2 \\
                             & \Leftrightarrow 4( \| \vec{y} \|^2 \| \vec{x} \|^2 ) \geq (2( \vec{x} \cdot \vec{y} ))^2 \\
                             & \Leftrightarrow  \| \vec{x} \| \| \vec{y} \| \geq | \vec{x} \cdot \vec{y} | \Longleftarrow  \text{코시-슈바르츠 부등식}\\
\end{align}$$
