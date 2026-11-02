# Exercise 7. Limit at a Point and Canceling a Factor

## The question

Compute

$$\lim_{x\to3}\frac{x^2-4x+3}{x-3}.$$

Explain why the value of the function at $x=3$ is not needed to compute the limit.

## Before calculating: what idea do we need?

When we substitute $x=3$ into $f(x)=\dfrac{x^2-4x+3}{x-3}$, both the numerator $3^2-4(3)+3=0$ and the denominator $3-3=0$ vanish, giving the indeterminate form $\dfrac{0}{0}$.

By Bézout's theorem, the fact that the polynomial $x^2-4x+3$ equals $0$ at $x=3$ guarantees that $(x-3)$ is a factor of the numerator! Because the limit as $x\to3$ only examines points *near* $3$ with $x\neq3$, we have $x-3\neq0$ and can legally cancel the factor $(x-3)$.

## 1. Check the direct substitution and factor the numerator

At $x=3$, the numerator is $3^2-4(3)+3 = 9-12+3 = 0$ and the denominator is $3-3=0$ (type $\dfrac{0}{0}$). Factoring the quadratic numerator:

$$x^2-4x+3 = (x-1)(x-3).$$

## 2. Cancel the common factor for $x\neq3$

For every $x\neq3$, $x-3\neq0$, so we can divide numerator and denominator by $x-3$:

$$\frac{x^2-4x+3}{x-3} = \frac{(x-1)(x-3)}{x-3} = x-1\qquad (\text{for } x\neq3).$$

## 3. Compute the limit

Since $\dfrac{x^2-4x+3}{x-3}$ and $x-1$ are equal at every point $x\neq3$, they have the exact same limit as $x\to3$. Because $g(x)=x-1$ is a polynomial (hence continuous everywhere), we find the limit by substituting $x=3$ into the simplified expression:

$$\lim_{x\to3}\frac{x^2-4x+3}{x-3} = \lim_{x\to3}(x-1) = 3-1 = 2.$$

## 4. Why the value at $x=3$ is not needed

By definition, $\lim_{x\to3}f(x)$ describes what $f(x)$ approaches as $x$ gets arbitrarily close to $3$ **while satisfying $x\neq3$**.

- Here, $f(3)$ is not even defined ($3$ is outside the domain of $f$).
- Geometrically, the graph of $f(x)=\dfrac{x^2-4x+3}{x-3}$ is the straight line $y=x-1$ with a single **puncture (hole)** at the point $(3,2)$.
- Walking along the line toward $x=3$ from either side brings you right up to height $y=2$, regardless of whether the point at $x=3$ is missing or moved elsewhere.

## Quick verification

Substitute $x=3+h$ with a small nonzero increment $h\neq0$:

$$f(3+h) = \frac{(3+h)^2-4(3+h)+3}{(3+h)-3} = \frac{9+6h+h^2-12-4h+3}{h} = \frac{2h+h^2}{h} = 2+h.$$

As $h\to0$, $2+h\to2$. ✓

## A concrete example

Evaluate $f(x)=\dfrac{x^2-4x+3}{x-3}$ at points approaching $3$ from the left and right:

- $x=2.9$: $f(2.9) = \dfrac{(2.9)^2-4(2.9)+3}{2.9-3} = \dfrac{-0.19}{-0.1} = 1.9$.
- $x=2.99$: $f(2.99) = \dfrac{-0.0199}{-0.01} = 1.99$.
- $x=3.01$: $f(3.01) = \dfrac{0.0201}{0.01} = 2.01$.
- $x=3.1$: $f(3.1) = \dfrac{0.21}{0.1} = 2.1$.

From both sides, the values pinch toward $2$, even though $f(3)$ does not exist.

## How I would explain this in class

> Plugging in $x=3$ gives $0/0$, which tells us $(x-3)$ factors out of the top: $x^2-4x+3=(x-1)(x-3)$. Since a limit as $x\to3$ only cares about $x$ near $3$ and never uses $x=3$ itself, $x-3$ is nonzero and cancels out. That leaves $x-1$, which goes to $3-1=2$. The graph is just the line $y=x-1$ with a tiny hole at $(3,2)$.

## Related workbook topics

- [Exercise 8: A square root in a function limit](problem_08_solution.md)
- [Exercise 10: Continuity of a piecewise function](problem_10_solution.md)
