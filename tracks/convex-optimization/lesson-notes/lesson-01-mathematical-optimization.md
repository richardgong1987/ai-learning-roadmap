# Lesson 1 - Mathematical Optimization

Date: 2026-06-28

## Lesson goal

Understand what a mathematical optimization problem is: choosing the best possible decision from many possible decisions, according to a clear objective and constraints.

## Main idea

Mathematical optimization is a formal way to answer this question:

> Among all possible choices, which one is best?

A problem usually has:

1. Decision variables: the things we can choose.
2. Objective function: the thing we want to minimize or maximize.
3. Constraints: the rules we must obey.
4. Feasible set: all choices that obey the constraints.
5. Optimal solution: the best feasible choice.

## Simple example

A worker wants to choose how many hours to spend on two tasks:

- Task A earns 10 dollars per hour.
- Task B earns 20 dollars per hour.
- Total available time is 5 hours.
- The worker wants to earn as much money as possible.

Let:

- x = hours spent on Task A
- y = hours spent on Task B

Objective:

maximize 10x + 20y

Constraints:

x + y <= 5
x >= 0
y >= 0

Because Task B earns more money per hour, the best choice is:

x = 0, y = 5

Maximum earning:

10 * 0 + 20 * 5 = 100

## Key technical terms

- Mathematical Optimization: 数学优化
- Decision Variable: 决策变量
- Objective Function: 目标函数
- Constraint: 约束
- Feasible Set: 可行域 / 可行集合
- Feasible Solution: 可行解
- Optimal Solution: 最优解
- Maximization Problem: 最大化问题
- Minimization Problem: 最小化问题

## Abstract form

A common minimization form is:

minimize f0(x)
subject to fi(x) <= 0, i = 1, ..., m
hi(x) = 0, i = 1, ..., p

Where:

- x is the decision variable vector.
- f0(x) is the objective function.
- fi(x) <= 0 are inequality constraints.
- hi(x) = 0 are equality constraints.
- The goal is to find x that satisfies the constraints and gives the smallest objective value.

## Application connections

Machine learning:

Training a model often means minimizing a loss function, such as prediction error.

Finance:

Portfolio optimization means choosing asset weights to balance return and risk.

Engineering:

Design optimization means choosing parameters that reduce cost, weight, or energy use while satisfying safety constraints.

Software engineering:

Systems often optimize latency, memory, throughput, or cost under resource constraints.

## Practical tips

1. Always identify the decision variables first.
2. Then write the objective.
3. Then list the constraints.
4. Check whether a solution is feasible before asking whether it is optimal.
5. Do not confuse the objective with the constraints.

## Tiny practice questions

1. You have 8 hours. Study earns 5 points per hour. Coding earns 10 points per hour. If you only want maximum points, how many hours should go to coding?
2. In the expression minimize (x - 3)^2, what is the decision variable?
3. If a rule says x <= 10, is x = 12 feasible?

## Answers

1. 8 hours should go to coding, because coding gives more points per hour.
2. x is the decision variable.
3. No. x = 12 violates the constraint x <= 10.

## Completion status

Completed. Progress should continue to Lesson 2: Least Squares and Linear Programming.
