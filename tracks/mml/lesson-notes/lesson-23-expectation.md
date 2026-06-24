# Lesson 23: Expectation

## Status

Completed.

## Core idea

Expectation is the long-run average value of a random variable. It does not necessarily predict one single future outcome. Instead, it describes what the average result approaches after many repeated trials.

## Concrete intuition

For a fair die, the possible outcomes are 1, 2, 3, 4, 5, and 6. Each outcome has probability 1/6.

\[
E[X] = 1\cdot\frac{1}{6} + 2\cdot\frac{1}{6} + 3\cdot\frac{1}{6} + 4\cdot\frac{1}{6} + 5\cdot\frac{1}{6} + 6\cdot\frac{1}{6} = 3.5
\]

The value 3.5 cannot appear as a die roll, but it is the long-run average result.

## Main formula

For a discrete random variable:

\[
E[X] = \sum_i x_i P(X=x_i)
\]

Meaning:

- \(X\): random variable
- \(x_i\): one possible value of \(X\)
- \(P(X=x_i)\): probability of that value
- \(\sum_i\): sum over all possible values

## Algebraic law

Linearity of expectation:

\[
E[aX + b] = aE[X] + b
\]

More generally:

\[
E[aX + bY] = aE[X] + bE[Y]
\]

This property does not require independence between \(X\) and \(Y\).

## Machine learning connection

Machine learning often minimizes expected loss:

\[
\min_\theta E[L(X;\theta)]
\]

This means the model is trained to reduce average loss over the data distribution, not just loss on one single sample.

## Key technical terms

- Expectation: 期望
- Expected Value: 期望值
- Random Variable: 随机变量
- Probability: 概率
- Weighted Average: 加权平均
- Linearity of Expectation: 期望的线性性
- Expected Loss: 期望损失

## Next lesson

Lesson 24: Variance.
