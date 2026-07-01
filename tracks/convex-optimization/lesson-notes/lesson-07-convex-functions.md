# Lesson 7 - Convex Functions

Date: 2026-07-01

## Goal

Understand what a convex function is and why convex functions are central to convex optimization.

## Simple real-life problem

Imagine walking across a valley.

If you draw a straight line between two points on the valley, the valley curve stays below that straight line.

This is the basic shape of a convex function.

Convex functions are useful because they make minimization problems easier and more reliable.

## Concrete numerical example

Let:

f(x) = x^2

Choose two points:

x = 0
y = 2

theta = 0.5

First calculate the mixed input:

theta x + (1 - theta)y = 0.5 * 0 + 0.5 * 2 = 1

Now evaluate the function at the mixed input:

f(1) = 1^2 = 1

Now calculate the mixed function values:

theta f(x) + (1 - theta)f(y) = 0.5 * f(0) + 0.5 * f(2)

f(0) = 0
f(2) = 4

So:

0.5 * 0 + 0.5 * 4 = 2

Compare:

f(1) = 1 <= 2

The function value at the middle input is below the straight line between the two endpoint values.

This is the key idea of convex functions.

## Key technical terms (English + Chinese)

- Convex Function: 凸函数
- Convex Set: 凸集
- Domain: 定义域
- Epigraph: 上图集
- Chord: 弦
- Weighted Average: 加权平均
- Convex Combination: 凸组合
- Jensen's Inequality: 詹森不等式
- Local Minimum: 局部最小值
- Global Minimum: 全局最小值
- Objective Function: 目标函数

## Symbol explanation

A function f is convex if:

f(theta x + (1 - theta)y) <= theta f(x) + (1 - theta)f(y)

for all x and y in the domain of f, and all theta in [0, 1].

Meaning:

- f is the function.
- x and y are two input points.
- theta is a weight between 0 and 1.
- theta x + (1 - theta)y is a point between x and y.
- f(theta x + (1 - theta)y) is the function value at that middle point.
- theta f(x) + (1 - theta)f(y) is the weighted average of the two endpoint function values.

## Formula explanation

The formula answers this question:

Does the function graph always stay below the straight line connecting any two points on the graph?

If yes, the function is convex.

In simple words:

A convex function is shaped like a bowl or valley.

## Step-by-step calculation

Let:

f(x) = x^2
x = 1
y = 3
theta = 0.25

Step 1: calculate the mixed input.

0.25 * 1 + 0.75 * 3 = 0.25 + 2.25 = 2.5

Step 2: evaluate f at the mixed input.

f(2.5) = 2.5^2 = 6.25

Step 3: evaluate the endpoints.

f(1) = 1
f(3) = 9

Step 4: calculate the weighted average of endpoint values.

0.25 * 1 + 0.75 * 9 = 0.25 + 6.75 = 7

Step 5: compare.

6.25 <= 7

The inequality holds, so this example supports that f(x) = x^2 is convex.

## Relationship to convex sets

A convex set checks whether the point between two allowed points stays inside the set.

A convex function checks whether the function value at the point between two inputs stays below the line between the endpoint function values.

Both ideas use the same convex combination:

theta x + (1 - theta)y

## Connection to applications

- Machine learning: least-squares loss is convex, which makes optimization easier.
- Finance: many portfolio risk measures are convex, helping find optimal portfolios reliably.
- Engineering: cost, energy, or error functions are often modeled as convex functions.
- Optimization practice: minimizing a convex function over a convex set gives strong theoretical guarantees.

## Practical tips

- Convex set means the allowed region is convex.
- Convex function means the objective landscape is convex.
- Convex functions look like bowls when minimizing.
- For minimization, convexity is useful because local minima are also global minima.
- Remember the picture: the graph stays below its chords.

## Tiny practice questions

1. For f(x) = x^2, what is f(2)?
2. For x = 0, y = 4, and theta = 0.5, what is the mixed input?
3. Why do convex functions make optimization easier?

## Answers and explanations

1. f(2) = 2^2 = 4.
2. 0.5 * 0 + 0.5 * 4 = 2.
3. Convex functions make optimization easier because a local minimum is also a global minimum, so algorithms are less likely to get trapped in a bad local solution.
