# Lesson 30: Neural Networks

## Status

Completed.

## Core idea

A neural network is a model made from many connected small calculation units called neurons.

Each neuron takes inputs, multiplies them by weights, adds a bias, applies an activation function, and passes the result forward.

Neural networks can learn complex non-linear relationships by stacking many layers.

## Concrete intuition

A single linear regression model is like one straight line:

\[
\hat{y} = wx + b
\]

A neural network combines many such small calculations and adds activation functions so it can model curves, patterns, and complex decision boundaries.

## Main formulas

One neuron:

\[
z = w_1x_1 + w_2x_2 + b
\]

Activation:

\[
a = \sigma(z)
\]

Layer form:

\[
z = Wx + b
\]

\[
a = \sigma(z)
\]

Meaning:

- \(x\): input features
- \(w\): weights
- \(b\): bias
- \(z\): pre-activation value
- \(\sigma\): activation function
- \(a\): activated output
- \(W\): weight matrix for a layer

## Step-by-step numerical example

Let:

- \(x_1 = 2\)
- \(x_2 = 3\)
- \(w_1 = 0.5\)
- \(w_2 = 1\)
- \(b = -1\)

Calculate:

\[
z = 0.5 \cdot 2 + 1 \cdot 3 - 1 = 3
\]

If using ReLU activation:

\[
a = \max(0, z) = \max(0, 3) = 3
\]

## Machine learning connection

Neural networks are trained by minimizing a loss function. Gradient descent updates the weights and biases. Backpropagation calculates gradients efficiently through all layers using the chain rule.

This connects earlier lessons:

- Linear algebra: vectors, matrices, matrix multiplication
- Calculus: derivatives, chain rule, gradients
- Probability: loss, uncertainty, classification probabilities
- Optimization: gradient descent

## Practical warning

Neural networks are powerful but can overfit, require careful training, and are less interpretable than simple models like linear regression.

## Key technical terms

- Neural Network: 神经网络
- Neuron: 神经元
- Layer: 层
- Input Layer: 输入层
- Hidden Layer: 隐藏层
- Output Layer: 输出层
- Weight: 权重
- Bias: 偏置
- Activation Function: 激活函数
- ReLU: 修正线性单元
- Backpropagation: 反向传播
- Chain Rule: 链式法则
- Overfitting: 过拟合

## Track status

Mathematics for Machine Learning track completed.
