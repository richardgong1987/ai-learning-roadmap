# Lesson 12 — Quadratic Optimization Problems

Date completed: 2026-07-21

## Learning objective

Understand how quadratic optimization models curved objectives involving squared terms, cross terms, risk, error, distance, and energy, and recognize when a quadratic program is convex.

## Core model

A quadratic program can be written as:

\[
\begin{aligned}
\text{minimize}\quad & \frac12x^TPx+q^Tx+r\\
\text{subject to}\quad & Gx\leq h\\
& Ax=b
\end{aligned}
\]

- `x`: decision-variable vector
- `P`: matrix controlling curvature
- `q`: linear objective coefficients
- `r`: constant term
- `Gx \leq h`: linear inequality constraints
- `Ax=b`: linear equality constraints

## One-variable numerical example

For:

\[
f(x)=x^2-8x
\]

complete the square:

\[
f(x)=(x-4)^2-16
\]

Therefore:

\[
x^*=4,\qquad f^*=-16
\]

The same result follows from:

\[
x^*=-\frac{b}{2a}
\]

with `a=1` and `b=-8`.

## Constrained example

For:

\[
\begin{aligned}
\text{minimize}\quad & x^2-8x\\
\text{subject to}\quad & 0\leq x\leq3
\end{aligned}
\]

The unconstrained minimizer `x=4` is infeasible, so the constrained optimum occurs at the boundary:

\[
x^*=3
\]

## Two-variable example

For:

\[
f(x,y)=x^2+y^2-6x-4y
\]

rewrite:

\[
f(x,y)=(x-3)^2+(y-2)^2-13
\]

Therefore:

\[
(x^*,y^*)=(3,2),\qquad f^*=-13
\]

## Matrix representation

Let:

\[
z=\begin{bmatrix}x\\y\end{bmatrix},\quad
P=\begin{bmatrix}2&0\\0&2\end{bmatrix},\quad
q=\begin{bmatrix}-6\\-4\end{bmatrix}
\]

Then:

\[
\frac12z^TPz+q^Tz=x^2+y^2-6x-4y
\]

Off-diagonal entries in `P` generate cross terms such as `xy`.

## Convexity condition

The quadratic objective is convex when:

\[
P\succeq0
\]

meaning:

\[
z^TPz\geq0
\]

for every vector `z`.

If:

\[
P\succ0
\]

the function is strictly convex and, on a convex feasible set, has at most one optimal point.

## Gradient and Hessian

For symmetric `P`:

\[
\nabla f(x)=Px+q
\]

and:

\[
\nabla^2f(x)=P
\]

An unconstrained minimizer satisfies:

\[
Px^*+q=0
\]

If `P` is invertible:

\[
x^*=-P^{-1}q
\]

## Finance application

Mean-variance portfolio optimization uses:

\[
\min_w \left(\frac12w^T\Sigma w-\lambda\mu^Tw\right)
\]

where:

- `w`: portfolio weights
- `\Sigma`: covariance matrix
- `w^T\Sigma w`: portfolio variance
- `\mu`: expected-return vector
- `\lambda`: preference for return relative to risk

## Machine-learning application

Least squares minimizes:

\[
\|Xw-y\|_2^2
\]

which expands into a quadratic function of `w`.

## Key technical terms (English + Chinese)

- Quadratic Optimization Problem: 二次优化问题
- Quadratic Programming (QP): 二次规划
- Quadratic Function: 二次函数
- Positive Semidefinite Matrix: 半正定矩阵
- Positive Definite Matrix: 正定矩阵
- Gradient: 梯度
- Hessian Matrix: 海森矩阵
- Portfolio Variance: 投资组合方差
- Least Squares: 最小二乘法
- Unique Minimum: 唯一最小值

## Practical checklist

1. Identify squared terms, cross terms, or matrix forms such as `x^TPx`.
2. Check whether `P` is positive semidefinite before calling the problem convex.
3. Solve the unconstrained problem first for intuition.
4. Verify whether the unconstrained solution satisfies all constraints.
5. Remember that constraints may move the optimum to a boundary.
6. Use positive definiteness to reason about uniqueness.

## Practice reviewed

- Solve one-variable quadratic minimization using `-b/(2a)`.
- Recognize upward-opening versus downward-opening quadratic functions.
- Connect covariance and squared error to quadratic optimization.