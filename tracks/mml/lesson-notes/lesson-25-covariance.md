# Lesson 25: Covariance

## Status

Completed.

## Core idea

Covariance tells whether two variables tend to move together or move in opposite directions.

If one variable is above its average while the other variable is also above its average, their product of deviations is positive. If one is below its average while the other is also below its average, their product of deviations is also positive. When this happens often, covariance is positive.

If one variable is above its average while the other is below its average, the product of deviations is negative. When this happens often, covariance is negative.

## Concrete intuition

Use study hours and exam scores:

| Student | Study hours X | Score Y |
|---|---:|---:|
| A | 1 | 50 |
| B | 2 | 60 |
| C | 3 | 70 |

Average study hours:

\[
E[X] = \frac{1 + 2 + 3}{3} = 2
\]

Average score:

\[
E[Y] = \frac{50 + 60 + 70}{3} = 60
\]

Deviation products:

| Student | X - E[X] | Y - E[Y] | Product |
|---|---:|---:|---:|
| A | -1 | -10 | 10 |
| B | 0 | 0 | 0 |
| C | 1 | 10 | 10 |

The products are mostly positive, so study hours and score have positive covariance.

## Main formula

\[
\operatorname{Cov}(X, Y) = E[(X - E[X])(Y - E[Y])]
\]

Meaning:

- \(X\): first random variable
- \(Y\): second random variable
- \(E[X]\): expected value or average of \(X\)
- \(E[Y]\): expected value or average of \(Y\)
- \(X - E[X]\): deviation of \(X\) from its average
- \(Y - E[Y]\): deviation of \(Y\) from its average
- \(E[\cdot]\): average of the deviation products

## Relationship with variance

Variance is a special case of covariance:

\[
\operatorname{Var}(X) = \operatorname{Cov}(X, X)
\]

Variance asks how one variable moves around its own mean. Covariance asks how two variables move around their means together.

## Machine learning connection

Covariance is useful because machine learning often needs to understand relationships between features.

Examples:

- House size and house price may have positive covariance.
- Study hours and exam score may have positive covariance.
- Exercise time and body fat may have negative covariance.

Covariance is also central to PCA. PCA uses covariance to find the directions where data varies the most.

## Practical warning

Covariance shows direction, but its raw value depends on units. Because of this, correlation is often used to normalize covariance:

\[
\rho_{X,Y} = \frac{\operatorname{Cov}(X,Y)}{\sigma_X \sigma_Y}
\]

Correlation is easier to compare because it is usually between -1 and 1.

## Key technical terms

- Covariance: 协方差
- Variance: 方差
- Expected Value: 期望值
- Random Variable: 随机变量
- Deviation: 偏离量
- Positive Covariance: 正协方差
- Negative Covariance: 负协方差
- Correlation: 相关系数
- PCA: 主成分分析

## Next lesson

Lesson 26: Bayes Theorem.
