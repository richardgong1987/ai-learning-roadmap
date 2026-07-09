# Lesson 10: Convex Optimization Problems

Date: 2026-07-09

## Main idea

A convex optimization problem is an optimization problem with a special safe structure:

- the objective function is convex,
- inequality constraints are convex,
- equality constraints are affine.

This structure matters because local improvement leads reliably toward the global optimum.

## Simple real-life problem

Suppose you want to buy a laptop.

| Store | Price |
|---|---:|
| A | 1200 |
| B | 1100 |
| C | 1150 |

Your goal is:

minimize price

Now suppose your budget is 1150. Then you must also obey:

price <= 1150

This already shows the two main parts of an optimization problem:

1. objective: what you want to minimize or maximize,
2. constraints: rules you must obey.

## Concrete numerical example

Consider:

minimize f(x) = x^2

subject to:

x >= 1

Rewrite the constraint into standard form:

1 - x <= 0

Here:

g(x) = 1 - x

This function is affine, so it is also convex.

Check feasible values:

| x | f(x) = x^2 |
|---|---:|
| 1 | 1 |
| 2 | 4 |
| 3 | 9 |
| 4 | 16 |

The smallest feasible value happens at:

x* = 1

The optimal value is:

f(x*) = 1

## Key technical terms (English + Chinese)

- Optimization Problem: 优化问题
- Convex Optimization Problem: 凸优化问题
- Objective Function: 目标函数
- Decision Variable: 决策变量
- Constraint: 约束
- Feasible Set: 可行域
- Feasible Point: 可行点
- Inequality Constraint: 不等式约束
- Equality Constraint: 等式约束
- Affine Function: 仿射函数
- Optimal Solution: 最优解
- Optimal Value: 最优值
- Global Optimum: 全局最优
- Local Optimum: 局部最优

## Symbol explanation

A standard optimization problem is written as:

minimize f(x)

subject to:

g_i(x) <= 0

h_j(x) = 0

Symbols:

- x: decision variable, the thing we can choose
- f(x): objective function, the thing we want to minimize
- g_i(x) <= 0: inequality constraints
- h_j(x) = 0: equality constraints
- i: index for different inequality constraints
- j: index for different equality constraints

## Formula explanation

A convex optimization problem has this form:

minimize f0(x)

subject to:

fi(x) <= 0, i = 1, ..., m

Ax = b

It is convex when:

1. f0 is convex,
2. each fi is convex,
3. equality constraints are affine, usually written as Ax = b.

Why equality constraints must be affine:

An equality such as x + y = 5 gives a flat line. This keeps the feasible set convex.

But an equality such as x^2 + y = 5 can create a curved feasible set that may break convexity.

## Step-by-step calculation

Problem:

minimize x^2

subject to:

x >= 2

Step 1: Identify the decision variable.

x is the decision variable.

Step 2: Identify the objective.

f(x) = x^2

This is convex.

Step 3: Rewrite the constraint.

x >= 2

is the same as:

2 - x <= 0

Step 4: Check the constraint function.

g(x) = 2 - x

This is affine, therefore convex.

Step 5: Find the smallest feasible x.

The feasible region is:

x >= 2

Since x^2 is smallest near zero, but zero is not feasible, the best feasible point is the closest feasible point to zero:

x* = 2

Step 6: Compute the optimal value.

f(2) = 2^2 = 4

So:

optimal solution = 2

optimal value = 4

## Connection to applications

### Machine learning

Many training problems are optimization problems. For example, linear regression minimizes prediction error. When the loss and regularizer are convex, training is more reliable.

### Finance

Portfolio optimization often minimizes risk subject to constraints such as total budget, no short selling, sector exposure, and target return.

### Engineering

Engineering design often minimizes cost, weight, or energy subject to safety and performance constraints.

### Optimization practice

Convex optimization is powerful because it avoids many traps of non-convex optimization. Under the right conditions, local optima are global optima.

## Practical tips

1. Always identify the decision variable first.
2. Then identify the objective function.
3. Then list all constraints.
4. Check whether the objective is convex.
5. Check whether every inequality constraint is convex.
6. Check whether every equality constraint is affine.
7. If any equality constraint is nonlinear, be careful: the problem may not be convex.

## Tiny practice questions

### Question 1

Consider:

minimize x^2

subject to:

x >= 2

What is the optimal solution?

### Question 2

Which equality constraint is affine?

A. x + y = 5

B. x^2 + y = 5

### Question 3

Which statement is true?

A. Every optimization problem is convex.

B. Every convex optimization problem has a convex objective function.

C. Equality constraints in convex optimization can be any nonlinear function.

## Answers and explanations

### Answer 1

The optimal solution is:

x* = 2

The optimal value is:

f(2) = 4

Because x^2 is smallest near zero, but the constraint x >= 2 forces x to be at least 2.

### Answer 2

A is affine:

x + y = 5

B is not affine because it contains x^2.

### Answer 3

B is true.

Every convex optimization problem has a convex objective function.

## Completion status

Lesson 10 is completed. Progress should continue to Lesson 11: Linear Optimization Problems.
