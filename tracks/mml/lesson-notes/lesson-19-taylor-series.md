# Lesson 19 - Taylor Series

Main idea:
A Taylor Series approximates a difficult function using easier polynomial pieces.

Plain explanation:
If you know a function's value, slope, curvature, and higher-order change at one nearby point, you can build a polynomial that behaves like the original function near that point.

Core formula around a point a:

f(x) ≈ f(a) + f'(a)(x-a) + f''(a)(x-a)^2/2! + f'''(a)(x-a)^3/3! + ...

Meaning:
- f(a): starting value
- f'(a): slope correction
- f''(a): curvature correction
- f'''(a): changing-curvature correction
- (x-a): distance from the expansion point
- n!: factorial, used to scale higher-order terms

Concrete example:
Use e^x near x = 0.

Because e^0 = 1 and every derivative of e^x is still e^x, all derivatives at 0 equal 1.

So:

e^x ≈ 1 + x + x^2/2! + x^3/3! + ...

At x = 0.1:

1 + 0.1 + 0.01/2 + 0.001/6 = 1.105166...

This is close to e^0.1 ≈ 1.10517.

Machine Learning:
Taylor Series explains local approximation, gradient descent intuition, second-order optimization, and why small steps can use local derivative information.