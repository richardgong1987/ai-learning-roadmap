# Lesson 2 - Least Squares and Linear Programming

Date: 2026-06-28

## Lesson goal

Understand two foundational optimization problem types:

1. Least squares: find the best approximate fit when exact matching is impossible.
2. Linear programming: find the best choice when the objective and constraints are linear.

## 1. Simple real-life problem

Imagine you are trying to estimate house prices.

You believe price depends mainly on house size:

- small house -> lower price
- large house -> higher price

But real data is messy. Two houses with the same size may not have exactly the same price because of location, age, condition, and many other factors.

So the question is not:

"Can we match every price perfectly?"

The better question is:

"Can we draw a line that is as close as possible to all observed prices?"

That is the basic idea of least squares.

Now imagine a factory.

It can produce Product A and Product B.

Each product earns profit, but each also uses limited labor and material.

The question is:

"How many units of A and B should we produce to get the maximum profit without breaking the resource limits?"

That is the basic idea of linear programming.

## 2. Concrete numerical example: least squares

Suppose we have three data points:

| House size x | Price y |
|---:|---:|
| 1 | 2 |
| 2 | 3 |
| 3 | 5 |

We try a simple model:

```text
predicted price = a * size
```

Use `a = 1.5`.

Predictions:

| x | actual y | predicted ax | error y - ax | squared error |
|---:|---:|---:|---:|---:|
| 1 | 2 | 1.5 | 0.5 | 0.25 |
| 2 | 3 | 3.0 | 0.0 | 0.00 |
| 3 | 5 | 4.5 | 0.5 | 0.25 |

Total squared error:

```text
0.25 + 0.00 + 0.25 = 0.50
```

Least squares chooses the value of `a` that makes this total squared error as small as possible.

## 3. Key technical terms (English + Chinese)

- Least Squares: 最小二乘法
- Residual: 残差
- Squared Error: 平方误差
- Objective Function: 目标函数
- Linear Programming: 线性规划
- Linear Objective: 线性目标函数
- Linear Constraint: 线性约束
- Feasible Region: 可行域
- Optimal Solution: 最优解
- Decision Variable: 决策变量

## 4. Symbol explanation

For least squares, the common formula is:

```text
minimize ||Ax - b||_2^2
```

Meaning:

- `x`: decision variable; the unknown values we want to choose.
- `A`: data matrix; it stores the input data.
- `b`: target vector; it stores the real observed answers.
- `Ax`: prediction made by the model.
- `Ax - b`: residual vector; the prediction errors.
- `||Ax - b||_2^2`: sum of squared errors.
- `minimize`: choose `x` to make the error as small as possible.

For linear programming, the common formula is:

```text
minimize c^T x
subject to Gx <= h
```

Meaning:

- `x`: decision variables.
- `c`: cost or profit coefficients.
- `c^T x`: linear objective.
- `Gx <= h`: linear inequality constraints.
- `subject to`: the rules that the solution must obey.

## 5. Formula explanation

### Least squares formula

```text
minimize ||Ax - b||_2^2
```

This formula solves the problem:

"When exact matching is impossible, choose the best approximate answer."

A tiny example:

```text
A = [1, 2, 3]^T
b = [2, 3, 5]^T
x = a
```

If `a = 1.5`, then:

```text
Ax = [1.5, 3.0, 4.5]^T
Ax - b = [-0.5, 0.0, -0.5]^T
```

Squared error:

```text
(-0.5)^2 + 0^2 + (-0.5)^2 = 0.5
```

### Linear programming formula

```text
maximize 3x + 2y
subject to
x + y <= 4
x <= 2
x >= 0, y >= 0
```

This formula solves the problem:

"Choose the best quantities while staying inside resource limits."

Here:

- `x`: units of Product A.
- `y`: units of Product B.
- `3x + 2y`: profit.
- `x + y <= 4`: total production limit.
- `x <= 2`: Product A limit.
- `x >= 0, y >= 0`: cannot produce negative products.

## 6. Step-by-step calculation

For the linear programming example:

Check possible corner points:

1. `(x, y) = (0, 0)`
   - Profit = `3*0 + 2*0 = 0`

2. `(x, y) = (2, 0)`
   - Profit = `3*2 + 2*0 = 6`

3. `(x, y) = (0, 4)`
   - Profit = `3*0 + 2*4 = 8`

4. `(x, y) = (2, 2)`
   - Profit = `3*2 + 2*2 = 10`

Best answer:

```text
x = 2, y = 2, maximum profit = 10
```

The important lesson: in linear programming, the best answer often happens at a corner of the feasible region.

## 7. Connection to applications

Least squares is used in:

- machine learning regression models
- curve fitting
- signal processing
- calibration
- forecasting
- finance factor models

Linear programming is used in:

- portfolio allocation with linear constraints
- production planning
- logistics and routing
- resource allocation
- scheduling
- supply-chain optimization

## 8. Practical tips

1. Least squares is about best fit.
2. Linear programming is about best feasible decision under linear rules.
3. Least squares usually minimizes error.
4. Linear programming usually minimizes cost or maximizes profit.
5. Always identify:
   - decision variables
   - objective function
   - constraints
   - feasible region

## 9. Tiny practice questions

### Question 1

If actual values are `[2, 4]` and predicted values are `[1, 5]`, what is the sum of squared errors?

### Question 2

For this linear program:

```text
maximize 5x + y
subject to x <= 3, y <= 2, x >= 0, y >= 0
```

Which point gives the maximum value?

### Question 3

In least squares, why do we square the errors?

## 10. Answers and explanations

### Answer 1

Errors:

```text
2 - 1 = 1
4 - 5 = -1
```

Squared errors:

```text
1^2 = 1
(-1)^2 = 1
```

Sum of squared errors:

```text
1 + 1 = 2
```

### Answer 2

Because both coefficients are positive, we want `x` and `y` as large as possible:

```text
x = 3, y = 2
```

Objective value:

```text
5*3 + 2 = 17
```

### Answer 3

We square errors because:

1. Positive and negative errors should not cancel each other.
2. Larger errors should be punished more strongly.
3. The formula becomes mathematically convenient for optimization.

## Completion status

Lesson 2 completed and repository updated on 2026-06-28.
