# Lesson 28: PCA

## Status

Completed.

## Core idea

PCA, or Principal Component Analysis, finds the most important directions in data.

It tries to reduce many features into fewer new features while keeping as much information, or variance, as possible.

## Concrete intuition

Imagine many points on a 2D chart. If the points mostly stretch along one diagonal direction, PCA finds that diagonal direction as the first principal component.

Instead of describing each point with two original coordinates, PCA can describe each point mostly by its position along that important direction.

## Main idea in simple words

PCA asks:

Which direction does the data spread the most?

That direction is the first principal component.

The second principal component is another direction, perpendicular to the first, that explains the next largest amount of spread.

## Important mathematical objects

PCA uses:

- Centered data
- Variance
- Covariance matrix
- Eigenvectors
- Eigenvalues
- Projection

## Main formula ideas

First, center the data:

\[
x_i' = x_i - \bar{x}
\]

Then build the covariance matrix:

\[
\Sigma = \frac{1}{n}X^T X
\]

Then solve the eigenvalue equation:

\[
\Sigma v = \lambda v
\]

Meaning:

- \(\Sigma\): covariance matrix
- \(v\): eigenvector, the principal direction
- \(\lambda\): eigenvalue, the amount of variance in that direction

## Machine learning connection

PCA is used for dimensionality reduction.

Examples:

- Compress high-dimensional data.
- Visualize high-dimensional data in 2D or 3D.
- Remove noise by keeping only the strongest directions.
- Reduce feature redundancy before training models.

## Practical warning

PCA is unsupervised. It does not look at target labels. It only looks at the structure of input data.

PCA keeps directions with large variance, but large variance is not always the same as predictive usefulness.

## Key technical terms

- PCA: 主成分分析
- Principal Component: 主成分
- Dimensionality Reduction: 降维
- Variance: 方差
- Covariance Matrix: 协方差矩阵
- Eigenvector: 特征向量
- Eigenvalue: 特征值
- Projection: 投影
- Centered Data: 中心化数据
- Unsupervised Learning: 无监督学习

## Next lesson

Lesson 29: Gradient Descent.
