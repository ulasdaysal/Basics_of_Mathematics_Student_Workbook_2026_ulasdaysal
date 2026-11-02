# Exercise 2. A Parabola from the Perspective of the Derivative

## The question

For $f(x)=x^2-4x+1$, find the minimum using the derivative. Compare the result with the vertex form and explain why both approaches lead to the same point.

## Before calculating: what idea do we need?

We have two complementary lenses for finding the lowest point of an upward-opening parabola:

- **The calculus lens (derivative):** At the bottom of the valley, the tangent line is horizontal, so the instantaneous rate of change is zero ($f'(x) = 0$).
- **The algebraic lens (vertex form):** Completing the square writes $f(x) = (x - p)^2 + q$. Since a square $(x - p)^2$ is never negative, the smallest value occurs precisely when the squared term vanishes ($x = p$).

## 1. Finding the minimum using the derivative

The domain of $f(x) = x^2 - 4x + 1$ is $\mathbb{R}$. Differentiating gives

$$f'(x) = 2x - 4 = 2(x - 2).$$

Setting $f'(x) = 0$ gives the single critical point $x = 2$:

| Interval / Point | $(-\infty, 2)$ | $x = 2$ | $(2, \infty)$ |
| :--- | :---: | :---: | :---: |
| Sign of $f'(x)$ | $-$ | $0$ | $+$ |
| Behavior of $f(x)$ | $\searrow$ decreasing | **Global min** ($-3$) | $\nearrow$ increasing |

Because $f'(x)$ changes sign from negative to positive at $x = 2$, $f$ has a global minimum at $x = 2$ with value

$$f(2) = 2^2 - 4(2) + 1 = 4 - 8 + 1 = -3.$$

## 2. Finding the minimum using the vertex form

Complete the square for $x^2 - 4x + 1$:

$$f(x) = (x^2 - 4x + 4) - 4 + 1 = (x - 2)^2 - 3.$$

Since $(x - 2)^2 \ge 0$ for every $x \in \mathbb{R}$, we have

$$f(x) = (x - 2)^2 - 3 \ge -3,$$

with equality if and only if $x - 2 = 0$, that is, $x = 2$. Thus the vertex is $(2, -3)$.

## 3. Why both approaches lead to the same point

If we differentiate the vertex form $f(x) = (x - p)^2 + q$ directly by the chain rule, we get

$$f'(x) = 2(x - p).$$

The condition $f'(x) = 0$ is literally $2(x - p) = 0$, which forces $x = p$ — the exact same condition that makes the non-negative square $(x - p)^2$ vanish! Geometrically, the parabola is symmetric across the vertical line $x = p$. Any non-zero slope at the vertex would break left-right symmetry, so the unique lowest point of a smooth symmetric curve must have slope zero.

## Quick verification

Check the vertex formula for $ax^2 + bx + c$ with $a = 1, b = -4, c = 1$:

$$p = -\frac{b}{2a} = -\frac{-4}{2(1)} = 2, \qquad q = f(2) = -3. \quad \checkmark$$

Also $f''(x) = 2 > 0$ everywhere, confirming strict convexity and a unique global minimum. ✓

## A concrete example

Step $h = 1$ unit to the left and right of $x = 2$:

$$f(1) = (1 - 2)^2 - 3 = 1 - 3 = -2, \qquad f(3) = (3 - 2)^2 - 3 = 1 - 3 = -2.$$

The slopes at these symmetric points are equal in magnitude and opposite in sign:

$$f'(1) = 2(1 - 2) = -2, \qquad f'(3) = 2(3 - 2) = +2.$$

Halfway between slope $-2$ and slope $+2$ sits the vertex $x = 2$ with slope $0$ and value $-3$.

## How I would explain this in class

> With derivatives, we set $f'(x) = 2x - 4 = 0$ to find where the tangent is flat, giving $x = 2$ and $f(2) = -3$. With algebra, completing the square gives $f(x) = (x-2)^2 - 3$, which is smallest when the square $(x-2)^2$ is zero, again at $x = 2$. Both give the exact same point because differentiating $(x-p)^2 + q$ produces $2(x-p)$, so zero slope and zero squared-distance from the axis of symmetry are the same equation.

## Related workbook topics

- [Exercise 1: A Cubic Polynomial](problem_01_solution.md)
- [Exercise 8: The Second Derivative](problem_08_solution.md)
