# Lesson 8: Operations That Preserve Function Convexity

Date: 2026-07-07

## Main idea

Convex function preservation rules are reusable building blocks. They let us construct larger convex functions from smaller convex functions without proving convexity from zero every time.

## Simple real-life problem

Suppose each bowl of noodles costs according to a simple convex cost curve because extra toppings become more expensive as quantity grows:

f(x) = x^2

If one bowl has 2 topping units, the cost score is:

f(2) = 2^2 = 4

If we add a fixed service fee of 3, the new function is:

g(x) = f(x) + 3 = x^2 + 3

The shape is still convex. Adding a flat fee only moves the curve upward; it does not bend the bowl shape downward.

## Concrete numerical example

Let:

f(x) = x^2

Choose two points:

x1 = 0, x2 = 4, theta = 0.5

Middle input:

0.5 x1 + 0.5 x2 = 2

Function value at the middle:

f(2) = 4

Average of endpoint values:

0.5 f(0) + 0.5 f(4) = 0.5 * 0 + 0.5 * 16 = 8

Because:

4 <= 8

f is convex for this test.

Now define:

g(x) = 2f(x) + 5 = 2x^2 + 5

Check the same points:

g(2) = 2 * 4 + 5 = 13

0.5g(0) + 0.5g(4) = 0.5 * 5 + 0.5 * 37 = 21

Because:

13 <= 21

g is still convex.

## Key technical terms (English + Chinese)

- Convex Function: 凸函数
- Nonnegative Weighted Sum: 非负加权和
- Affine Composition: 仿射复合
- Pointwise Maximum: 逐点最大值
- Composition Rule: 复合规则
- Monotone Function: 单调函数
- Epigraph: 上图集
- Perspective Function: 透视函数
- Partial Minimization: 部分最小化

## Symbol explanation

Convexity condition:

f(theta x + (1 - theta)y) <= theta f(x) + (1 - theta)f(y)

Symbols:

- f: the function
- x, y: two input points
- theta: a mixing weight between 0 and 1
- theta x + (1 - theta)y: a point between x and y
- <=: the function value at the middle is no higher than the straight-line average

## Important preservation rules

### 1. Nonnegative weighted sum

If f1, f2, ..., fm are convex and weights w1, ..., wm are nonnegative, then:

g(x) = w1 f1(x) + w2 f2(x) + ... + wm fm(x)

is convex.

Example:

f1(x) = x^2, f2(x) = |x|, w1 = 2, w2 = 3

g(x) = 2x^2 + 3|x|

This is convex because it is built from convex functions with nonnegative weights.

Important warning:

Negative weights can destroy convexity. For example:

-x^2

is concave, not convex.

### 2. Affine composition

If f is convex, then:

g(x) = f(Ax + b)

is convex.

In one dimension:

f(u) = u^2

g(x) = f(3x + 1) = (3x + 1)^2

This is still convex because affine transformation only stretches, shifts, or rotates the input before applying f.

### 3. Pointwise maximum

If f1 and f2 are convex, then:

g(x) = max(f1(x), f2(x))

is convex.

Example:

f1(x) = x^2
f2(x) = x + 1

g(x) = max(x^2, x + 1)

At each x, choose the larger value. The result is still convex.

### 4. Composition rule

If h is convex and nondecreasing, and g is convex, then:

f(x) = h(g(x))

is convex.

Example:

g(x) = x^2
h(u) = exp(u)

Then:

f(x) = exp(x^2)

is convex because exp is convex and increasing, and x^2 is convex.

Warning:

Composition is not always safe. You must check monotonicity and convexity conditions.

## Step-by-step calculation

Take:

f1(x) = x^2
f2(x) = |x|
g(x) = 2f1(x) + 3f2(x)

At x = -2:

f1(-2) = (-2)^2 = 4
f2(-2) = |-2| = 2

g(-2) = 2 * 4 + 3 * 2 = 8 + 6 = 14

At x = 4:

f1(4) = 16
f2(4) = 4

g(4) = 2 * 16 + 3 * 4 = 32 + 12 = 44

Middle point with theta = 0.5:

x_mid = 0.5(-2) + 0.5(4) = 1

g(1) = 2 * 1^2 + 3 * |1| = 2 + 3 = 5

Average endpoint value:

0.5g(-2) + 0.5g(4) = 0.5 * 14 + 0.5 * 44 = 29

Because:

5 <= 29

this numerical check supports convexity.

## Connection to applications

Machine learning:

Regularized loss functions often combine a convex loss and a convex penalty:

loss + lambda * regularization

For example:

squared error + lambda * L1 penalty

Finance:

Portfolio risk models often combine convex risk terms and convex transaction cost terms.

Engineering:

Design problems often combine energy cost, safety penalty, and material cost. If each part is convex and combined with nonnegative weights, the whole objective can stay convex.

Optimization practice:

Preservation rules help you recognize whether a problem can be solved reliably by convex optimization methods.

## Practical tips

1. First identify simple convex building blocks: x^2, |x|, exp(x), norm(x), max terms.
2. Check whether weights are nonnegative.
3. Check whether input transformations are affine.
4. For composition, always check monotonicity.
5. When unsure, do not guess. Test using known rules or go back to the definition.

## Tiny practice questions

### Question 1

Is this function convex?

f(x) = 3x^2 + 2|x|

### Question 2

Is this function convex?

f(x) = -2x^2 + 5

### Question 3

If f(x) = x^2, is g(x) = f(4x - 1) convex?

## Answers and explanations

### Answer 1

Yes. x^2 is convex and |x| is convex. The weights 3 and 2 are nonnegative, so the nonnegative weighted sum is convex.

### Answer 2

No. x^2 is convex, but multiplying it by -2 turns it upside down. The result is concave, not convex.

### Answer 3

Yes. g(x) = (4x - 1)^2. This is affine composition of a convex function, so it is convex.

## Completion status

Lesson 8 is completed. Progress should continue to Lesson 9: Conjugate Functions.
