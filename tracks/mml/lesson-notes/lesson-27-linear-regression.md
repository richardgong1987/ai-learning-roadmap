# Lesson 27: Linear Regression

## Status

Completed.

## Core idea

Linear regression learns a straight-line relationship between input features and a numeric target.

For one input variable, the model has the form:

\[
\hat{y} = wx + b
\]

The goal is to choose \(w\) and \(b\) so the predicted values \(\hat{y}\) are close to the real values \(y\).

## Concrete intuition

Suppose we want to predict exam score from study hours.

| Study hours x | Real score y |
|---:|---:|
| 1 | 50 |
| 2 | 60 |
| 3 | 70 |

A good line is:

\[
\hat{y} = 10x + 40
\]

Predictions:

- If \(x = 1\), \(\hat{y} = 10 \cdot 1 + 40 = 50\)
- If \(x = 2\), \(\hat{y} = 10 \cdot 2 + 40 = 60\)
- If \(x = 3\), \(\hat{y} = 10 \cdot 3 + 40 = 70\)

## Main formula

Single-feature linear regression:

\[
\hat{y} = wx + b
\]

Meaning:

- \(x\): input feature
- \(y\): real target value
- \(\hat{y}\): predicted target value
- \(w\): weight or slope
- \(b\): bias or intercept

## Loss function

A common loss function is mean squared error:

\[
L(w,b) = \frac{1}{n}\sum_{i=1}^{n}(\hat{y}_i - y_i)^2
\]

Since \(\hat{y}_i = wx_i + b\), this can also be written as:

\[
L(w,b) = \frac{1}{n}\sum_{i=1}^{n}(wx_i + b - y_i)^2
\]

The model learns by finding \(w\) and \(b\) that minimize this loss.

## Machine learning connection

Linear regression is one of the simplest supervised learning models.

It connects earlier lessons:

- Functions: the model is a function from input to output.
- Derivatives and gradients: used to reduce loss.
- Expectation and variance: help understand average error and spread.
- Covariance: explains how input and target move together.

## Practical warning

Linear regression is simple and interpretable, but it assumes the relationship is approximately linear. If the real relationship is curved or complex, a straight line may underfit.

## Key technical terms

- Linear Regression: 线性回归
- Feature: 特征
- Target: 目标值
- Prediction: 预测值
- Weight: 权重
- Bias: 偏置
- Slope: 斜率
- Intercept: 截距
- Loss Function: 损失函数
- Mean Squared Error: 均方误差
- Gradient Descent: 梯度下降
- Underfitting: 欠拟合

## Next lesson

Lesson 28: PCA.
