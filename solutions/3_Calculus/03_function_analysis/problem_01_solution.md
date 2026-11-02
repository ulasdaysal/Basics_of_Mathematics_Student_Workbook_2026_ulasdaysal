# Exercise 1. A Cubic Polynomial

## The question

Analyze the monotonicity and extrema of

$$f(x)=x^3-3x^2+2.$$

Sketch the graph based on the results and mark the critical points.

## Before calculating: what idea do we need?

The first derivative $f'(x)$ gives the slope of the tangent line at each point:

- $f'(x) > 0$: the function is **strictly increasing** (rising from left to right),
- $f'(x) < 0$: the function is **strictly decreasing** (falling from left to right),
- $f'(x) = 0$: the tangent is horizontal — a **critical point** and candidate for a local extremum.

When $f'(x)$ changes sign across a critical point, the graph turns around and forms a local maximum ($+$ to $-$) or a local minimum ($-$ to $+$).

## 1. Domain and derivative

Because $f$ is a polynomial, its domain is all real numbers: $D = \mathbb{R}$.

Differentiating term by term and factoring gives

$$f'(x) = 3x^2 - 6x = 3x(x - 2).$$

## 2. Critical points and sign of the derivative

Solving $f'(x) = 0$:

$$3x(x - 2) = 0 \implies x = 0 \quad \text{or} \quad x = 2.$$

Since $f'(x) = 3x(x-2)$ is a quadratic with positive leading coefficient ($a = 3 > 0$), its parabola opens upward: it is positive outside the roots and negative between them.

| Interval / Point | $(-\infty, 0)$ | $x = 0$ | $(0, 2)$ | $x = 2$ | $(2, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| Behavior of $f(x)$ | $\nearrow$ increasing | **Local max** ($2$) | $\searrow$ decreasing | **Local min** ($-2$) | $\nearrow$ increasing |

## 3. Monotonicity and extrema

Evaluate $f$ at the critical points:

$$f(0) = 0^3 - 3\cdot 0^2 + 2 = 2,$$

$$f(2) = 2^3 - 3\cdot 2^2 + 2 = 8 - 12 + 2 = -2.$$

- **Increasing** on $(-\infty, 0]$ and $[2, \infty)$.
- **Decreasing** on $[0, 2]$.
- **Local maximum** at $x = 0$ with value $f(0) = 2$ (where $f'$ changes from $+$ to $-$).
- **Local minimum** at $x = 2$ with value $f(2) = -2$ (where $f'$ changes from $-$ to $+$).

## 4. Sketching the graph

To anchor the sketch, note the limits at infinity and the zeros:

- $\lim_{x\to-\infty} f(x) = -\infty$ and $\lim_{x\to\infty} f(x) = +\infty$.
- By inspection, $f(1) = 1 - 3 + 2 = 0$, and factoring gives $x^3 - 3x^2 + 2 = (x-1)(x^2 - 2x - 2) = 0$, so the $x$-intercepts are $x = 1$ and $x = 1 \pm \sqrt{3} \approx -0.73, \, 2.73$.

**Graph description:** Starting from $-\infty$ in the third quadrant, the curve rises through $(-0.73, 0)$ to a rounded peak at the critical point $(0, 2)$ on the $y$-axis. It then falls through $(1, 0)$ (which is also its inflection point) down to a trough at the critical point $(2, -2)$, before turning upward through $(2.73, 0)$ and climbing toward $+\infty$.

## Quick verification

Using the second derivative test with $f''(x) = 6x - 6$:

- At $x = 0$: $f''(0) = -6 < 0 \implies$ local maximum. ✓
- At $x = 2$: $f''(2) = 6 > 0 \implies$ local minimum. ✓
- Midpoint check: at $x = 1 \in (0, 2)$, $f(1) = 0$, which lies strictly between $f(0) = 2$ and $f(2) = -2$, confirming the downward transition. ✓

## A concrete example

Compare the slopes just before, between, and after the critical points:

- At $x = -1$: $f'(-1) = 3(-1)(-3) = 9 > 0$ (steeply rising).
- At $x = 1$: $f'(1) = 3(1)(-1) = -3 < 0$ (falling).
- At $x = 3$: $f'(3) = 3(3)(1) = 9 > 0$ (steeply rising again).

Also notice the symmetry around the inflection point $(1, 0)$: moving $1$ unit left to $x=0$ raises $y$ by $2$, while moving $1$ unit right to $x=2$ lowers $y$ by $2$.

## How I would explain this in class

> To sketch $f(x) = x^3 - 3x^2 + 2$, we first differentiate to get $f'(x) = 3x(x-2)$. The slope is zero at $x = 0$ and $x = 2$. Because $f'(x)$ is an upward-opening parabola, the derivative is positive outside $[0, 2]$ and negative inside it. That tells us the cubic climbs to a local maximum at $(0, 2)$, drops to a local minimum at $(2, -2)$, and then climbs forever.

## Related workbook topics

- [Exercise 8: The Second Derivative](problem_08_solution.md)
- [Exercise 15: Find the Error in the Monotonicity Analysis](problem_15_solution.md)
