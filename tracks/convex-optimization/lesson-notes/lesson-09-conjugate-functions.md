# Lesson 9: Conjugate Functions

Date: 2026-07-07

## Main idea

A conjugate function transforms a function into a new function that asks this question:

"If I draw a straight line with slope y, what is the largest vertical gap between that line and the original function?"

This is important because conjugate functions are the bridge to duality, Lagrange dual problems, support functions, and many optimization tricks.

## Simple real-life problem

Imagine a taxi cost curve:

f(x) = x^2

Here:

- x = distance level
- f(x) = cost score

Now suppose someone offers to pay you y dollars per distance level. Your revenue line is:

yx

Your profit is:

yx - f(x)

The conjugate function asks:

"For this payment rate y, what is the maximum profit I can get by choosing the best x?"

So the conjugate is:

f*(y) = max over x of (yx - f(x))

## Concrete numerical example

Let:

f(x) = x^2

Choose:

y = 4

Then:

f*(4) = max over x of (4x - x^2)

Test some values:

| x | 4x - x^2 |
|---|----------|
| 0 | 0        |
| 1 | 3        |
| 2 | 4        |
| 3 | 3        |
| 4 | 0        |

The largest value is 4, when x = 2.

So:

f*(4) = 4

This means: when the slope/payment rate is 4, the best possible gap between the line 4x and the curve x^2 is 4.

## Key technical terms (English + Chinese)

- Conjugate Function: 共轭函数
- Fenchel Conjugate: Fenchel 共轭
- Supremum: 上确界
- Maximum: 最大值
- Slope: 斜率
- Linear Function: 线性函数
- Affine Function: 仿射函数
- Gap: 差距
- Support Function: 支撑函数
- Duality: 对偶性
- Primal Problem: 原问题
- Dual Problem: 对偶问题

## Symbol explanation

The conjugate function is defined as:

f*(y) = sup_x (y^T x - f(x))

Symbols:

- f: the original function
- f*: the conjugate function of f
- x: the original input variable
- y: the slope-like variable in the conjugate space
- y^T x: inner product; in one dimension it is just yx
- f(x): original function value
- y^T x - f(x): vertical gap between the linear function and f
- sup_x: the largest upper value over all possible x

In one dimension:

f*(y) = sup_x (yx - f(x))

If the maximum is actually reached, we can write max instead of sup.

## Formula explanation

Important formula:

f*(y) = sup_x (y^T x - f(x))

### What problem does this formula solve?

It measures how much a linear function with slope y can exceed the original function f.

In simple words:

- Choose a slope y.
- Try every possible x.
- Compute line value minus function value.
- Keep the biggest gap.

### Plug in actual numbers

Let:

f(x) = x^2

y = 4

Then:

f*(4) = sup_x (4x - x^2)

The expression is:

4x - x^2

This is a concave quadratic, so it has a maximum.

Complete the square:

4x - x^2 = -(x^2 - 4x)

x^2 - 4x = (x - 2)^2 - 4

So:

4x - x^2 = -[(x - 2)^2 - 4]

= -(x - 2)^2 + 4

The largest value happens when:

(x - 2)^2 = 0

So:

x = 2

Then:

f*(4) = 4

## Step-by-step calculation for the general case

Let:

f(x) = x^2

The conjugate is:

f*(y) = sup_x (yx - x^2)

We want to maximize:

g(x) = yx - x^2

Differentiate with respect to x:

g'(x) = y - 2x

Set derivative equal to zero:

y - 2x = 0

So:

x = y / 2

Plug this back into the expression:

f*(y) = y(y / 2) - (y / 2)^2

= y^2 / 2 - y^2 / 4

= y^2 / 4

Therefore:

If f(x) = x^2, then f*(y) = y^2 / 4.

Check with y = 4:

f*(4) = 4^2 / 4 = 16 / 4 = 4

This matches the numerical example.

## Why conjugate functions matter

### Machine learning

Many ML loss functions and regularizers have useful conjugates. They help derive dual problems for support vector machines, logistic regression, and regularized optimization.

Example idea:

A difficult primal problem can sometimes become easier after converting part of it into its conjugate form.

### Finance

Conjugates appear in risk measures, robust optimization, and portfolio optimization. They help express worst-case cost, penalty, and support functions.

Simple intuition:

If f(x) is a cost curve, f*(y) tells us the best advantage a linear price y can get against that cost curve.

### Engineering

In control, signal processing, and resource allocation, conjugates help transform hard constraints or penalties into dual variables. This often makes computation easier.

### Optimization practice

Conjugates are the foundation for duality. The next big topic, convex optimization problems and later Lagrange duality, becomes much easier if this idea is clear.

## Practical tips

1. Do not memorize conjugates blindly at first. Start with the meaning: maximum gap between a line and a function.
2. For one-dimensional examples, write yx - f(x), then maximize over x.
3. If f is quadratic, use derivative or complete the square.
4. Remember: f* uses y as its input, not x.
5. Conjugate functions often turn minimization problems into dual maximization problems later.

## Tiny practice questions

### Question 1

Let:

f(x) = x^2

What is f*(2)?

### Question 2

For:

f(x) = x^2

What x gives the maximum gap when y = 6?

### Question 3

In plain English, what does f*(y) measure?

## Answers and explanations

### Answer 1

We know:

f*(y) = y^2 / 4

So:

f*(2) = 2^2 / 4 = 4 / 4 = 1

### Answer 2

For f(x) = x^2, the best x is:

x = y / 2

When y = 6:

x = 6 / 2 = 3

### Answer 3

f*(y) measures the largest gap between the straight line yx and the original function f(x), after trying all possible x values.

## Completion status

Lesson 9 is completed. Progress should continue to Lesson 10: Convex Optimization Problems.
