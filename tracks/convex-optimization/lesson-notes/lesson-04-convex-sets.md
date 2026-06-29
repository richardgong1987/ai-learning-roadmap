# Lesson 4 - Convex Sets

Date: 2026-06-29

## Goal

Understand what a convex set is and why convex sets are important in convex optimization.

## Simple real-life problem

Imagine a park with two points inside it: point A and point B. If you walk in a straight line from A to B and every point on that straight line is still inside the park, then the park shape behaves like a convex set.

If the straight path goes outside the park, then the park is not convex.

## Concrete numerical example

Consider the interval:

S = [0, 10]

Choose two points:

x = 2, y = 8

Choose a mixing weight:

theta = 0.25

Now calculate the point between x and y:

theta x + (1 - theta)y = 0.25 * 2 + 0.75 * 8 = 0.5 + 6 = 6.5

Because 6.5 is still inside [0, 10], this example satisfies the convex-set condition.

## Key technical terms (English + Chinese)

- Convex Set: 凸集
- Set: 集合
- Point: 点
- Line Segment: 线段
- Weighted Average: 加权平均
- Convex Combination: 凸组合
- Feasible Region: 可行域
- Constraint: 约束

## Symbol explanation

The convex set formula is:

For any x, y in S and any theta in [0, 1],

theta x + (1 - theta)y must also be in S.

Meaning:

- S is the set we are checking.
- x and y are two points in S.
- theta is a number between 0 and 1.
- theta x + (1 - theta)y is a point on the straight line segment between x and y.
- If every such point stays inside S, then S is convex.

## Formula explanation

The formula solves this question:

If I pick two allowed points, is every point between them also allowed?

If yes, the set is convex.

## Step-by-step calculation

Example:

S = [0, 10]
x = 2
y = 8
theta = 0.25

Step 1:

1 - theta = 1 - 0.25 = 0.75

Step 2:

theta x = 0.25 * 2 = 0.5

Step 3:

(1 - theta)y = 0.75 * 8 = 6

Step 4:

theta x + (1 - theta)y = 0.5 + 6 = 6.5

Step 5:

6.5 is inside [0, 10], so this particular test passes.

Because any two points in an interval have all points between them inside the interval, [0, 10] is convex.

## Abstract form

A set S is convex if:

x, y in S, theta in [0, 1] => theta x + (1 - theta)y in S

In plain words:

A set is convex if it contains the whole straight line segment between any two of its points.

## Connection to applications

- Machine learning: Many training problems require the feasible parameter space to be convex so optimization is easier and more reliable.
- Finance: Portfolio weights often form a convex set, such as weights that are non-negative and sum to 1.
- Engineering: Design constraints such as maximum force, power, or capacity can create feasible regions. If the feasible region is convex, optimization is easier.
- Optimization practice: Convex feasible regions help avoid disconnected search spaces and make global solutions easier to reason about.

## Practical tips

- A convex set is about the shape of allowed points, not about a function curve.
- Do not confuse convex set with convex function.
- To test convexity, always ask: if I choose two allowed points, is the whole straight line between them still allowed?
- Intervals like [0, 10] are convex.
- A set like {0, 10} is not convex because the middle points, such as 5, are missing.

## Tiny practice questions

1. Is S = [3, 7] convex?
2. Is S = {3, 7} convex?
3. Let S = [0, 10], x = 4, y = 10, theta = 0.5. Calculate theta x + (1 - theta)y. Is it inside S?

## Answers and explanations

1. Yes. Any two points inside [3, 7] have all points between them still inside [3, 7].
2. No. The point 5 is between 3 and 7, but 5 is not in {3, 7}.
3. 0.5 * 4 + 0.5 * 10 = 2 + 5 = 7. Yes, 7 is inside [0, 10].
