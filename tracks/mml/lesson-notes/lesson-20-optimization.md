# Lesson 20 - Optimization

Main idea:
Optimization means finding the best input value that makes a function as small or as large as possible.

## Core Problem

In machine learning, training usually means minimizing a loss function.

Example:

f(x) = x^2

The minimum happens at:

x = 0

because:

f(0) = 0

## Key Formula

Gradient descent:

x_new = x - eta * f'(x)

Where:

- x is the current value.
- x_new is the updated value.
- eta is the learning rate.
- f'(x) is the derivative of the function.

## Numerical Example

Let:

f(x) = x^2

Then:

f'(x) = 2x

Start:

x = 4

Learning rate:

eta = 0.1

Step 1:

f'(4) = 8

x_new = 4 - 0.1 * 8 = 3.2

Step 2:

f'(3.2) = 6.4

x_new = 3.2 - 0.1 * 6.4 = 2.56

The value moves toward 0.

## Algebraic View

x* = argmin_x f(x)

This means: find the input x that produces the smallest value of f(x).

## Taylor Series Connection

First-order Taylor approximation:

f(x + delta_x) approximately equals f(x) + f'(x) * delta_x

Gradient descent chooses a delta_x in the opposite direction of the derivative, so the function value decreases.

## Machine Learning Connection

For a model with weights w and loss L(w):

w_new = w - eta * gradient L(w)

This is the foundation of training many machine learning models, including linear regression, neural networks, deep learning models, and large language models.

## Practical Warning

- If the learning rate is too large, optimization may jump around and fail to converge.
- If the learning rate is too small, optimization may be very slow.
- Good optimization needs a balanced learning rate.