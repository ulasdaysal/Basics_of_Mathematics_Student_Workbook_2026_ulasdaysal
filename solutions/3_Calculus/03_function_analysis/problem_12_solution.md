# Exercise 12. A Function with an Absolute Value

## The question

Analyze

$$f(x)=|x^2-4|.$$

First sketch $x^2-4$, then explain the effect of the absolute value. Indicate the points where the derivative does not exist and justify the reason geometrically.

## Before calculating: what idea do we need?

For any function $g(x)$, taking the absolute value $f(x) = |g(x)|$ leaves the graph unchanged wherever $g(x) \ge 0$, and **reflects the negative parts across the $x$-axis** wherever $g(x) < 0$. Whenever the original graph $g(x)$ crosses the $x$-axis at a non-zero angle ($g(x_0) = 0$ with $g'(x_0) \neq 0$), reflecting that crossing creates a sharp corner (a V-shaped kink) where the left-hand and right-hand slopes are opposites, so the derivative fails to exist there.

## 1. Sketching $g(x) = x^2 - 4$ and applying the absolute value

- **The base parabola $g(x) = x^2 - 4$:** Its domain is $\mathbb{R}$, it is even, has vertex $(0, -4)$, and crosses the $x$-axis at $x = -2$ and $x = 2$.
  - $x^2 - 4 \ge 0$ on $(-\infty, -2] \cup [2, \infty)$,
  - $x^2 - 4 < 0$ on $(-2, 2)$.
- **Effect of the absolute value:** We write $f(x) = |x^2 - 4|$ piecewise:
  $$f(x) = \begin{cases} x^2 - 4, & \text{if } x \in (-\infty, -2] \cup [2, \infty), \\ 4 - x^2, & \text{if } x \in (-2, 2). \end{cases}$$
  Geometrically, the outer arms for $|x| \ge 2$ stay untouched, while the U-shaped dip between $x = -2$ and $x = 2$ (with vertex $(0, -4)$) is flipped upside down across the $x$-axis into a dome with peak $(0, 4)$.

## 2. Points where the derivative does not exist

On the open intervals away from $x = \pm 2$, we can differentiate each formula directly:

$$f'(x) = \begin{cases} 2x, & \text{if } x \in (-\infty, -2) \cup (2, \infty), \\ -2x, & \text{if } x \in (-2, 2). \end{cases}$$

At the junction points $x = -2$ and $x = 2$, compare the one-sided derivatives:

- **At $x = 2$:**
  $$f'_-(2) = \lim_{x\to 2^-} (-2x) = -4, \qquad f'_+(2) = \lim_{x\to 2^+} (2x) = +4.$$
  Since $-4 \neq +4$, **$f'(2)$ does not exist**.
- **At $x = -2$:**
  $$f'_-(-2) = \lim_{x\to -2^-} (2x) = -4, \qquad f'_+(-2) = \lim_{x\to -2^+} (-2x) = +4.$$
  Since $-4 \neq +4$, **$f'(-2)$ does not exist**.

**Geometric justification:** The parabola $y = x^2 - 4$ crosses the $x$-axis at $x = \pm 2$ with steep slopes $\pm 4$ rather than tangentially. Reflecting the underside across the $x$-axis folds the tangent line of slope $-4$ into a half-tangent of slope $+4$, producing two **sharp corners (cusps/kinks)** at $(-2, 0)$ and $(2, 0)$ where no single tangent line exists.

## 3. Complete monotonicity and extrema of $f(x) = |x^2 - 4|$

| Interval / Point | $(-\infty, -2)$ | $x = -2$ | $(-2, 0)$ | $x = 0$ | $(0, 2)$ | $x = 2$ | $(2, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| $f'(x)$ | $2x < 0$ | **DNE** (corner) | $-2x > 0$ | $0$ | $-2x < 0$ | **DNE** (corner) | $2x > 0$ |
| Behavior of $f(x)$ | $\searrow$ | **Min** ($0$) | $\nearrow$ | **Max** ($4$) | $\searrow$ | **Min** ($0$) | $\nearrow$ |

- **Strictly decreasing** on $(-\infty, -2]$ and $[0, 2]$.
- **Strictly increasing** on $[-2, 0]$ and $[2, \infty)$.
- **Local (and global) minima** at $x = -2$ and $x = 2$ with value $f(\pm 2) = 0$ — notice these occur at points where $f'(x)$ **does not exist**, not where $f'(x) = 0$!
- **Local maximum** at $x = 0$ with value $f(0) = 4$ (where $f'(0) = 0$).

## Quick verification

- Check non-negativity: since $|x^2 - 4| \ge 0$ for all $x \in \mathbb{R}$ and $f(\pm 2) = 0$, the points $x = \pm 2$ are guaranteed to be global minima even without derivatives. ✓
- Check difference quotient directly at $x = 2$:
  $$\lim_{h\to 0^+} \frac{|(2+h)^2 - 4| - 0}{h} = \lim_{h\to 0^+} \frac{4h + h^2}{h} = 4, \qquad \lim_{h\to 0^-} \frac{|(2+h)^2 - 4| - 0}{h} = \lim_{h\to 0^-} \frac{-(4h + h^2)}{h} = -4. \quad \checkmark$$

## A concrete example

Look at the secant slopes over a tiny step of $0.1$ on either side of $x = 2$:

- Just to the left ($x = 1.9$): $f(1.9) = |3.61 - 4| = 0.39$, so $\frac{f(2) - f(1.9)}{2 - 1.9} = \frac{0 - 0.39}{0.1} = -3.9 \approx -4$.
- Just to the right ($x = 2.1$): $f(2.1) = |4.41 - 4| = 0.41$, so $\frac{f(2.1) - f(2)}{2.1 - 2} = \frac{0.41 - 0}{0.1} = +4.1 \approx +4$.

The graph plunges into $(2, 0)$ with slope $-4$ and immediately bounces up with slope $+4$.

## How I would explain this in class

> To graph $f(x) = |x^2 - 4|$, start with the parabola $y = x^2 - 4$ and flip the part below the $x$-axis (on $(-2, 2)$) upward so the vertex $(0, -4)$ becomes a local maximum at $(0, 4)$. Because the original parabola crosses the $x$-axis at $x = \pm 2$ at a steep angle (slope $\pm 4$), folding the negative part up creates sharp V-shaped corners at $(-2, 0)$ and $(2, 0)$. At those two corners the left slope is $-4$ and the right slope is $+4$, so the derivative does not exist there — even though both points are global minima!

## Related workbook topics

- [Exercise 2: A Parabola from the Perspective of the Derivative](problem_02_solution.md)
- [Exercise 8: The Second Derivative](problem_08_solution.md)
