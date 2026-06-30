# Lesson 5 - Important Convex Set Examples

Date: 2026-06-30

## Goal

Recognize common convex and non-convex sets quickly, using the line-segment test from Lesson 4.

## Simple real-life problem

Imagine a robot can move only inside an allowed area. If the robot can move in a straight line between any two allowed positions without leaving the area, the allowed area is convex.

Different shapes behave differently:

- A filled square is convex.
- A filled triangle is convex.
- A filled disk is convex.
- A hollow ring is not convex.
- A C-shaped region is not convex.

## Concrete numerical example

Consider the interval:

S = [2, 8]

Choose two points:

x = 3, y = 7

Choose a mixing weight:

theta = 0.4

Calculate:

theta x + (1 - theta)y = 0.4 * 3 + 0.6 * 7 = 1.2 + 4.2 = 5.4

Because 5.4 is still inside [2, 8], the line-segment test passes for this example.

Since any two points in an interval have all points between them inside the interval, [2, 8] is convex.

## Key technical terms (English + Chinese)

- Convex Set: 凸集
- Non-convex Set: 非凸集
- Interval: 区间
- Line Segment: 线段
- Disk: 圆盘
- Ball: 球
- Halfspace: 半空间
- Hyperplane: 超平面
- Polyhedron: 多面体
- Feasible Region: 可行域
- Constraint: 约束

## Important convex set examples

### 1. Interval

An interval such as [2, 8] is convex.

Reason: every number between two numbers in the interval is still inside the interval.

### 2. Line segment

A line segment is convex.

Reason: if two points are on the same segment, every point between them is also on the segment.

### 3. Filled disk

A filled disk is convex.

Reason: the straight line between any two points inside the disk stays inside the disk.

Important note: the boundary of a circle only is not convex, because the straight line between two boundary points usually passes through the interior, and the interior is missing.

### 4. Rectangle

A rectangle is convex.

Reason: any straight line connecting two points inside the rectangle remains inside the rectangle.

### 5. Triangle

A triangle is convex.

Reason: sharp corners do not matter. Convexity only checks whether the line segment between two points stays inside.

### 6. Halfspace

A halfspace is one side of a straight boundary.

Example:

x <= 5

This means all points on the left side of x = 5.

It is convex because mixing two points that both satisfy x <= 5 still gives a point satisfying x <= 5.

### 7. Hyperplane

A hyperplane is a flat equality boundary.

Example:

x + y = 10

It is convex because if two points satisfy the equality, any weighted average of them also satisfies the equality.

### 8. Polyhedron

A polyhedron is the intersection of multiple halfspaces and hyperplanes.

Example:

x >= 0

y >= 0

x + y <= 10

This forms a triangle-shaped feasible region, which is convex.

## Non-convex examples

### 1. Hollow ring

A hollow ring is not convex.

Reason: choosing points on opposite sides of the ring creates a line segment that passes through the missing hole.

### 2. C-shaped region

A C-shaped region is not convex.

Reason: the line between two points near the tips can pass through empty space outside the set.

### 3. Discrete set

A set such as {3, 7} is not convex.

Reason: the midpoint 5 is missing.

## Formula explanation

The convex-set test is:

For any x, y in S and any theta in [0, 1],

theta x + (1 - theta)y must also be in S.

This checks whether every point on the line segment between x and y stays inside S.

## Step-by-step calculation

Let:

S = [1, 9]
x = 2
y = 8
theta = 0.75

Step 1:

1 - theta = 1 - 0.75 = 0.25

Step 2:

theta x = 0.75 * 2 = 1.5

Step 3:

(1 - theta)y = 0.25 * 8 = 2

Step 4:

theta x + (1 - theta)y = 1.5 + 2 = 3.5

Step 5:

3.5 is inside [1, 9], so the result stays inside the set.

## Connection to applications

- Machine learning: parameter constraints and regularization regions are often convex sets.
- Finance: portfolio-weight constraints, such as non-negative weights that sum to 1, form a convex set.
- Engineering: safe design regions can often be written as convex feasible regions.
- Optimization practice: recognizing common convex sets helps identify convex optimization problems faster.

## Practical tips

- Filled shapes like disks, rectangles, and triangles are usually convex.
- Hollow shapes are often non-convex.
- A boundary-only circle is not convex.
- A finite set with isolated points is usually not convex unless it contains only one point.
- Many useful constraints in optimization are built from halfspaces and hyperplanes.

## Tiny practice questions

1. Is a filled square convex?
2. Is the boundary of a circle only convex?
3. Is the set {3, 7} convex?

## Answers and explanations

1. Yes. Any line segment between two points in the filled square remains inside the square.
2. No. The line between two boundary points usually passes through the interior, but the interior is not included.
3. No. The midpoint 5 is between 3 and 7, but 5 is not in {3, 7}.
