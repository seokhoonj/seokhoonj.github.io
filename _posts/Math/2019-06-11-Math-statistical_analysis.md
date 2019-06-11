---
layout: post
title: Statistical Analysis 
category: Math 
tags: [Statistical, Analysis]
published: true
comments: true
---

2. Descriptive Statistics
 - 모집단(Population)과 표본(Sample)
 - 평균, 분산, 표준편차, 변동계수
 - 중위수(Median), 사분위수(Quartiles) and Boxplot
 - Histogram, Stem-and-Leaf plot, Q-Q Normality plot

3. 가설과 검정
 - 가설설정, 단측검정, 양측검정
 - 검정통계량(Test Statistic)
 - 유의수준(Level of Significance)
 - 유의확률(P-value)
 - 검정력(Power)과 표본수(Sample Size)
 - 표본이 모집단을 대표하는가?

4. One Sample T-Test
 - T분포 ( \\( Var(\bar{x}) = \frac{\sigma^2}{n},\ Z = \frac{\bar{x} - \mu}{\sigma / \sqrt{n}} \sim N(0, 1), \ t = \frac{\bar{x} - \mu}{s / \sqrt{n}} \sim t(n - 1) \\) )
 - 검정통계량
 - 유의확률
 - 분석과 해석( 정규성 검정: shapiro-wilk normality test, t-test)

5. Paired T-Test
 - 쌍을 이룬 두 변수(matched-pair)의 차이를 보는 검정
 - 정규성 검정
 - t-test(사후 - 사전)
 - mvrnorm test in r (n = length(n), mu = c(x1, x2), Sigma = sigma matrix)

6. Wilcoxon Signed-Rank Test
 - one-sample t-test와 paired t-test에 해당하는 비모수 방법
 - non-parametric method (데이터의 순서에 의존)
 - 중위수(median)이 0인지 검정
 - 양수인 데이터의 수와 음수인 데이터의 수가 같다면 중위수가 0
 - 부호를 무시하고 절대값으로 순위를 구한 후 +의 순위합을 구하여 귀무가설이 사실(median = 0)일 때의 순위합의 분포와 비교
 - 동일한 값들이 있으면 순서를 정하는데 문제가 생겨 exact test로 p-value를 구하지 못하고 대신 정규분포에 근사시켜 p-value를 구한다.

7. Two-Sample T-Test
 - 실험군과 대조군에 서로 다른 개입(intervention)을 적용시킨 후 두 집단의 평균이 같은지를 비교하여 개입 효과의 차이를 평가
 - 쌍을 이룬 두 변수 간의 차이의 평균이 0인지를 검정하는 paired t-test와는 달리 서로 독립적인 두 집단의 평균의 차이가 0인지를 검정 
 - 두 집단의 분산이 같은지 검정 (var.test) -> 분산이 다르면 Welch의 t-test -> 같으면 pooled variance를 이용한 t-test
 - 모두 독립적이므로 쌍을 이룬 paired t-test와는 다르다.
 - 검정통계량은 두 그룹의 평균의 차이를 그것의 표준오차로 나눠준 것이다. ( \\( \frac{\bar{y\_1} - \bar{y\_2}}{\sqrt{Var(\bar{y\_1} - \bar{y\_2})}} \\) )
 - 평균 차이의 분산은 \\( Var(\bar{y\_1} - \bar{y\_2}) = \frac{\sigma\_1^2}{n\_1} + \frac{\sigma\_2^2}{n\_2} \\)
 - 두 집단의 분산이 같은가 다른가에 따라 분산의 추정 방법이 달라진다.
 - 분산이 다른 경우( \\( \sigma\_1^2 \neq \sigma\_2^2 \\) )
 - \\( t^\prime = \frac{ \bar{y\_1} - \bar{y\_2} }{ \sqrt{\frac{\sigma\_1^2}{n\_1} + \frac{\sigma\_2^2}{n\_2} } \sim t(df = \nu^\prime) \\)


Mean-Variance Portfolio Theory
---

1. sample mean
\\( \bar{R} = \frac{\sum\_{i=1}^{n}R\_i}{n} \\)

2. sample variance
\\( \sigma = \sqrt{\frac{\sum(R\_i - \bar{R})^2}{n - 1}} \\)

3. standard error
\\( s.e. = \frac{\sqrt{\frac{\sum(R\_i - \bar{R})^2}{n - 1}}}{\sqrt{n}} \\)

평균이 $\mu$ 이고 분산이 $\sigma^2$인 모집단에서 크기 $n$인 표본을 임의 추출
