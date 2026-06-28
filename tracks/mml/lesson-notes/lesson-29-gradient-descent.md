# Lesson 29: Gradient Descent

## Status

Completed.

## Core idea

Gradient descent is a method for reducing loss step by step.

It uses the gradient to know which direction makes the loss increase fastest, then moves in the opposite direction to make the loss smaller.

## Concrete intuition

Imagine standing on a hill in fog. You want to walk down to the lowest point, but you cannot see far away.

You check the local slope under your feet. If the ground rises to the right, you walk left. If the ground rises forward, you walk backward.

Gradient descent does the same thing with a loss function.

## Main formula

\[
\theta_{new} = \theta_{old} - \alpha \nabla L(\theta_{old})
\]

Meaning:

- \(\theta\): model parameter, such as weight or bias
- \(L\): loss function
- \(\nabla L(\theta)\): gradient of the loss at the current parameter
- \(\alpha\): learning rate
- minus sign: move opposite the gradient to reduce loss

## Simple numerical example

Let:

\[
L(w) = (w - 3)^2
\]

The minimum is at \(w = 3\).

Derivative:

\[
\frac{dL}{dw} = 2(w - 3)
\]

Start at:

\[
w = 0
\]

Learning rate:

\[
\alpha = 0.1
\]

Gradient:

\[
2(0 - 3) = -6
\]

Update:

\[
w_{new} = 0 - 0.1(-6) = 0.6
\]

The parameter moves from 0 toward 3.

## Machine learning connection

Gradient descent is used to train many machine learning models, including linear regression, logistic regression, and neural networks.

Training means repeatedly updating parameters to reduce loss.

## Practical warning

The learning rate is important.

- If the learning rate is too small, training is very slow.
- If the learning rate is too large, training may jump around or diverge.

## Key technical terms

- Gradient Descent: 梯度下降
- Gradient: 梯度
- Loss Function: 损失函数
- Parameter: 参数
- Learning Rate: 学习率
- Update Rule: 更新规则
- Optimization: 优化
- Convergence: 收敛
- Divergence: 发散
- Local Minimum: 局部最小值

## Next lesson

Lesson 30: Neural Networks.
