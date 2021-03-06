---
layout: post
title: 통계분석 정리 
category: Math 
tags: [Statistics]
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
 - 중위수(median)가 0인지 검정
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
 - 분산이 다른 경우 ( \\( \sigma\_1^2 \neq \sigma\_2^2, \ t^{\prime} = \frac{\bar{y\_1} - \bar{y\_2}}{\sqrt{\frac{s\_1^2}{n\_1} + \frac{s\_2^2}{n\_2}}} \sim t(df = \nu^{\prime}) \\) )
 - 자유도를 조정하여 t-분포에 근사시킬 수 있다. ( \\( \nu^\prime = \frac{ (\frac{\sigma\_1^2}{n\_1} + \frac{\sigma\_2^2}{n\_2})^2 }{ \frac{s\_1^4}{n\_1^2(n\_1 - 1)} + \frac{s\_2^4}{n\_2^2(n\_2 - 1)} }\\) )
 - 분산이 같은 경우 ( \\( \sigma\_1^2 = \sigma\_2^2, \ s\_\text{pooled_variance}^2 = \frac{(n\_1 - 1)s\_1^2 + (n\_2 - 1)s\_2^2}{n\_1 + n\_2 - 2} \\) )
 - 평균차이의 분산은 다음과 같이 추정된다. ( \\( s\_p^2(\frac{1}{n\_1} + \frac{1}{n\_2} ) \\) )
 - 이 추정치를 이용한 검정통계량은 자유도가 \\( (n\_1 + n\_2 - 2) \\) 인 t-분포를 따른다. ( \\( t = \frac{\bar{y\_1} - \bar{y\_2}}{s\_p\sqrt{\frac{1}{n\_1} + \frac{1}{n\_2}}} \sim t(df = n\_1 + n\_2 -2) \\) ) 

8. Wilcoxon Rank-Sum Test
 - two sample t-test에 대응하는 비모수 방법
 - 데이터 값 자체를 사용하지 않고 그 순위를 데이터로 사용한다. 두 집단을 섞어서 순위를 구한 후, 둘 중 한 집단의 순위합을 귀무가설이 사실일(두 집단의 median이 같을) 이론적인 순위합의 분포와 비교하여 두 집단의 median이 통계적으로 유의한 차이가 있는지 검정한다.
 - wilcox.test(y ~ 그룹변수) 즉, 그룹변수에 따른 y의 값

9. 상관분석(Correlation Analysis)
 - 공분산은 두 변수가 같은 방향으로 움직이는지 다른 방향으로 움직이는지를 보여준다.
 - 그러나 공분산은 측정된 값의 단위(scale)에 영향을 받는데, 공분산을 두 변수의 표준편차로 나누어 (-1, 1)사이의 값을 갖도록 조정한 것이 피어슨의 상관계수로 두 변수의 *직선관계*정도를 측정한다.
 - 비모수 방법인 Kendall의 \\( \tau \\), Spearman의 \\( \rho \\)도 있다.
 - \\( cov(x,y) = \frac{\sum\_{i = 1}^{n} (x\_i - \bar{x}) (y\_i - \bar{y})}{n - 1}, \ corr(x,y) = \frac{cov(x,y)}{sd(x)sd(y)} \\) 
 - 하나라도 결측치가 있으면 NA를 출력한다. 이를 방지하려면 다음의 코드를 사용한다. cor(data, method = "상관계수종류", use = "pairwise.complete.obs")
 - p-value를 알고 싶다면 cor.test()를 이용한다.

10. 단순회귀분석(Simple Linear Regression)
 - \\( \hat{\beta} = \frac{cov(x, y)}{var(x)} = 4.5 \\)  
