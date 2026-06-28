# Lesson 3 - What Makes Optimization Convex

## Lesson goal

Understand what makes an optimization problem convex and why convex problems are easier and safer to solve than general optimization problems.

## Core idea

An optimization problem is convex when it has two main properties:

1. The feasible region has no holes, gaps, or disconnected parts.
2. The objective function has no hidden local traps.

In a convex minimization problem, any local minimum is also a global minimum. This is the main reason convex optimization is powerful.

## Simple real-life example

Imagine walking down into a smooth bowl. Wherever you start, if you keep walking downhill, you will eventually reach the bottom. There is only one best low area.

Now imagine walking in mountains with many valleys. You may walk downhill and stop in a small valley, but another deeper valley may exist far away. That is a local minimum, not the global minimum.

Convex optimization is like the smooth bowl. Non-convex optimization is like the mountain landscape.

## Concrete numerical example

Consider minimizing:

f(x) = (x - 3)^2

Try three values:

- x = 1: f(1) = (1 - 3)^2 = 4
- x = 2: f(2) = (2 - 3)^2 = 1
- x = 3: f(3) = (3 - 3)^2 = 0

The best value is x = 3. The graph is a U-shaped bowl. Moving toward x = 3 always improves the objective.

Now consider:

f(x) = x^4 - 4x^2

This function can have more than one valley. A search method may fall into one valley and miss another. This is why non-convex problems are harder.

## Key technical terms (English + Chinese)

- Convex Optimization: 凸优化
- Convex Problem: 凸问题
- Convex Set: 凸集
- Convex Function: 凸函数
- Feasible Region: 可行域
- Objective Function: 目标函数
- Local Minimum: 局部最小值
- Global Minimum: 全局最小值
- Line Segment: 线段
- Bowl Shape: 碗形
- Non-convex Problem: 非凸问题

## Symbol explanation

A standard optimization problem is written as:

minimize f(x)
subject to x in C

Symbols:

- x: decision variable, the thing we can choose
- f(x): objective function, the score or cost we want to minimize
- C: feasible set, all allowed choices
- x in C: x must obey the constraints

For the problem to be convex:

1. C must be a convex set.
2. f must be a convex function.

## Convex set formula

A set C is convex if, for any two points x and y in C, every point on the straight line between them is also in C:

θx + (1 - θ)y in C, where 0 <= θ <= 1

### What problem this formula solves

It checks whether the allowed region has gaps or holes. If two allowed points are inside the region, the straight path between them must also stay inside.

### Numerical example

Let C = [0, 10]. Choose:

- x = 2
- y = 8
- θ = 0.25

Compute:

θx + (1 - θ)y
= 0.25 × 2 + 0.75 × 8
= 0.5 + 6
= 6.5

Since 6.5 is still inside [0, 10], this example supports that [0, 10] is convex.

## Convex function formula

A function f is convex if:

f(θx + (1 - θ)y) <= θf(x) + (1 - θ)f(y), where 0 <= θ <= 1

### What problem this formula solves

It checks whether the function bends upward like a bowl. The value at the middle should not be higher than the straight-line average of the two endpoint values.

### Numerical example

Let:

f(x) = x^2
x = 2
y = 4
θ = 0.5

Middle point:

θx + (1 - θ)y = 0.5 × 2 + 0.5 × 4 = 3

Left side:

f(3) = 3^2 = 9

Right side:

0.5f(2) + 0.5f(4)
= 0.5 × 4 + 0.5 × 16
= 2 + 8
= 10

So:

9 <= 10

This supports that f(x) = x^2 is convex.

## Why convexity matters

Convexity matters because it gives a strong guarantee:

For convex minimization problems, a local minimum is also a global minimum.

This means if an algorithm finds a point where it cannot improve locally, that point is not merely a small local valley. It is globally best.

## Connection to applications

### Machine learning

Many loss functions are designed to be convex or approximately convex because convex problems are easier to train and analyze. Linear regression with squared error is a classic convex problem.

### Finance

Portfolio optimization often uses convex ideas. For example, minimizing portfolio risk under budget and exposure constraints can become a convex optimization problem.

### Engineering

Engineering design problems often involve minimizing cost, energy, error, or weight under physical constraints. If the model is convex, engineers can solve it more reliably.

### Optimization practice

Convexity helps answer the practical question: if the solver returns a solution, can we trust it as globally best? For convex problems, the answer is much stronger than for non-convex problems.

## Practical tips

- When reading an optimization problem, first ask: is the feasible region convex?
- Then ask: is the objective function convex for minimization?
- Linear functions are both convex and concave.
- Quadratic functions like x^2 are convex.
- Non-convex problems may still be useful, but they are harder because local search can get trapped.

## Tiny practice questions

### Question 1

Is the interval [1, 5] a convex set?

Answer: Yes.

Explanation: Pick any two points inside [1, 5]. The straight line between them is also inside [1, 5].

### Question 2

For f(x) = x^2, calculate whether the convexity inequality holds for x = 0, y = 4, θ = 0.5.

Answer:

Middle point:

0.5 × 0 + 0.5 × 4 = 2

Left side:

f(2) = 4

Right side:

0.5f(0) + 0.5f(4) = 0.5 × 0 + 0.5 × 16 = 8

Since 4 <= 8, the inequality holds.

### Question 3

Why is a convex minimization problem easier than a non-convex one?

Answer: Because in a convex minimization problem, a local minimum is also a global minimum. The solver is not trapped in a fake valley.

## Lesson completion summary

Lesson 3 explained that convex optimization problems are special because the feasible region has no broken parts and the objective has no hidden local traps. The key guarantee is that local optimality implies global optimality for convex minimization problems.
