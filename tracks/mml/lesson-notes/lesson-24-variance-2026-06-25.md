# Lesson 24: Variance

Date: 2026-06-25
Track: Mathematics for Machine Learning
Part: Probability

## Summary

Variance measures how spread out a random variable is around its expected value. Expectation tells us the center, while variance tells us how unstable or dispersed the outcomes are.

## Core idea

If two random variables have the same expectation, they can still behave very differently. A low-variance variable stays close to its mean. A high-variance variable often moves far away from its mean.

## Important formula

Variance is defined as:

```text
Var(X) = E[(X - E[X])^2]
```

Equivalent computational form:

```text
Var(X) = E[X^2] - (E[X])^2
```

## Example

For values 1, 2, 3:

- Mean = 2
- Squared deviations: 1, 0, 1
- Variance = (1 + 0 + 1) / 3 = 2/3

## Machine learning connection

Variance is used to understand data spread, model instability, overfitting, feature scaling, Gaussian distributions, loss functions, and uncertainty.

## Next lesson

Lesson 25: Covariance
