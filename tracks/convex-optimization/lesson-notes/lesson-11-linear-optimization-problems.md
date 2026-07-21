# Lesson 11 — Linear Optimization Problems

Date completed: 2026-07-21

## Learning objective

Understand how a linear optimization problem chooses decision variables to optimize a linear objective while satisfying linear equality and inequality constraints.

## Core model

A linear optimization problem can be written as:

\[
\begin{aligned}
\text{minimize}\quad & c^T x+d\\
\text{subject to}\quad & Gx\preceq h\\
& Ax=b
\end{aligned}
\]

- `x`: decision-variable vector
- `c`: objective coefficients
- `Gx \preceq h`: linear inequality constraints
- `Ax=b`: linear equality constraints

A maximization problem can be converted into minimization by negating the objective.

## Numerical bakery example

Let:

- `x` = number of breads
- `y` = number of cakes

Profit and resource limits:

\[
\begin{aligned}
\text{maximize}\quad & 300x+500y\\
\text{subject to}\quad & 2x+y\leq8\\
& x+2y\leq8\\
& x\geq0,\ y\geq0
\end{aligned}
\]

The feasible vertices are:

- `(0,0)`, profit `0`
- `(4,0)`, profit `1200`
- `(0,4)`, profit `2000`
- `(8/3,8/3)`, profit `6400/3 ≈ 2133.33`

Therefore:

\[
x^*=\frac83,\qquad y^*=\frac83,\qquad p^*=\frac{6400}{3}
\]

## Why linear programs are convex

- A linear objective is convex.
- A linear inequality defines a halfspace, which is convex.
- A linear equality defines a hyperplane, which is convex.
- The intersection of convex sets is convex.

Therefore, every linear program is a convex optimization problem. A local optimum is also a global optimum.

## Geometric insight

For a bounded feasible polyhedron, if a finite optimum exists, at least one optimal solution occurs at an extreme point (vertex). If the objective is parallel to a boundary edge, an entire edge can be optimal.

## Possible outcomes

1. **Optimal** — a finite best feasible value exists.
2. **Infeasible** — no point satisfies all constraints.
3. **Unbounded** — the objective can improve without limit.

## Key technical terms (English + Chinese)

- Linear Optimization Problem: 线性优化问题
- Linear Programming (LP): 线性规划
- Decision Variable: 决策变量
- Objective Function: 目标函数
- Constraint: 约束
- Feasible Point: 可行点
- Feasible Set: 可行集
- Optimal Point: 最优点
- Optimal Value: 最优值
- Halfspace: 半空间
- Polyhedron: 多面体
- Extreme Point / Vertex: 极点 / 顶点
- Infeasible: 不可行
- Unbounded: 无界

## Applications

- Finance: portfolio allocation, exposure limits, transaction-cost models
- Machine learning: L1 fitting, optimal transport, robust and piecewise-linear formulations
- Engineering: resource and energy allocation
- Operations: scheduling, transportation, blending, and supply-chain planning

## Practical checklist

1. Identify the decision variables.
2. Write the objective in words before symbols.
3. Convert each limited resource into a constraint.
4. Check that units are consistent.
5. Verify that every objective and constraint expression is linear.
6. Check whether the model is feasible, bounded, and correctly signed.

## Practice reviewed

- Form an objective from per-unit profits.
- Form a resource constraint from per-unit usage.
- Recognize an unbounded maximization problem.
