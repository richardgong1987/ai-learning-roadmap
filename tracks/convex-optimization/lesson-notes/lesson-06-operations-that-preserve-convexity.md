# Lesson 6 - Operations That Preserve Convexity

Date: 2026-06-30

## Goal

Understand how to build new convex sets from known convex sets without proving convexity from scratch every time.

## Simple real-life problem

Suppose you already know that a square is convex and a rectangle is convex.

Now you create a new allowed area by taking only the overlapping part of them.

The question is:

Do you need to prove from zero that the new area is convex?

No. If the operation preserves convexity, the new set is automatically convex.

## Concrete numerical example

Let:

A = [0, 10]
B = [4, 8]

Both A and B are convex intervals.

Their intersection is:

A intersect B = [4, 8]

The result is still convex.

This shows the rule:

The intersection of convex sets is convex.

## Key technical terms (English + Chinese)

- Convexity-preserving Operation: 保持凸性的运算
- Intersection: 交集
- Affine Transformation: 仿射变换
- Translation: 平移
- Scaling: 缩放
- Rotation: 旋转
- Projection: 投影
- Image: 像
- Preimage: 原像
- Feasible Region: 可行域
- Constraint: 约束

## Symbol explanation

### Intersection

If C1 and C2 are convex sets, then:

C1 intersect C2 is also convex.

Meaning:

- C1 is one convex set.
- C2 is another convex set.
- C1 intersect C2 means the points that belong to both sets.

### Affine transformation

An affine transformation has the form:

y = Ax + b

Meaning:

- x is the original point.
- A is a matrix that can scale, rotate, or shear the point.
- b is a vector that shifts the point.
- y is the transformed point.

## Formula explanation

### Formula 1: Intersection preserves convexity

If x and y are both in C1 intersect C2, then x and y are in C1 and also in C2.

Because C1 is convex, every point between x and y is in C1.

Because C2 is convex, every point between x and y is also in C2.

Therefore, every point between x and y is in both C1 and C2.

So C1 intersect C2 is convex.

### Formula 2: Affine transformation

y = Ax + b

This formula transforms every point in a set. Convexity is preserved because weighted averages still behave correctly after linear transformation and translation.

## Step-by-step calculation

Let:

x = [1, 2]

A = [[2, 0], [0, 2]]

b = [3, 1]

Use:

y = Ax + b

Step 1: multiply A and x.

Ax = [2, 4]

Step 2: add b.

Ax + b = [2, 4] + [3, 1] = [5, 5]

So the original point [1, 2] becomes [5, 5].

If the original set was convex, the transformed set is still convex.

## Important operations that preserve convexity

### 1. Intersection

The intersection of convex sets is convex.

This is the most important rule in practice because feasible regions are often created by many constraints.

### 2. Affine transformation

If a set is convex, then moving, scaling, rotating, or shearing it through an affine transformation keeps it convex.

### 3. Projection

Projection means ignoring some variables.

For example, if a convex set uses variables (x, y, z), projecting it onto (x, y) still gives a convex set.

### 4. Inverse image under affine mapping

If a convex set is pulled back through an affine function, the result is still convex.

This is useful when constraints are written as affine expressions.

## Connection to applications

- Machine learning: constraints on model parameters are often built by intersections of convex constraints.
- Finance: portfolio feasible regions are often intersections of budget, risk, and weight constraints.
- Engineering: design limits such as stress, power, and size can be combined through intersections.
- Optimization practice: recognizing convexity-preserving operations helps identify convex problems quickly.

## Practical tips

- Do not prove every feasible region from scratch.
- Look for known convex building blocks.
- Look for intersections of constraints.
- Look for affine transformations such as y = Ax + b.
- When a problem has many linear inequalities, the feasible region is usually a convex polyhedron.

## Tiny practice questions

1. If two rectangles are convex, is their intersection always convex?
2. Does moving a convex set 5 units to the right change its convexity?
3. Why is the feasible region x >= 0, y >= 0, x + y <= 5 convex?

## Answers and explanations

1. Yes. The intersection of convex sets is always convex.
2. No. Translation changes position, not convexity. The translated set is still convex.
3. Each inequality defines a convex halfspace, and the feasible region is the intersection of these halfspaces. Intersections preserve convexity, so the feasible region is convex.
