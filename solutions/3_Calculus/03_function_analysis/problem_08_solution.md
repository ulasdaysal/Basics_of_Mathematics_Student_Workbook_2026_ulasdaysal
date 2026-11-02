# Exercise 8. The Second Derivative

## The question

For

$$f(x)=x^4-4x^2$$

find the local extrema, intervals of convexity and concavity, and inflection points. Sketch the graph and mark all the identified features on it.

## Before calculating: what idea do we need?

While the **first derivative** $f'(x)$ tells us whether the graph is rising or falling, the **second derivative** $f''(x) = (f'(x))'$ tells us how the slope itself is changing — that is, how the graph bends:

- $f''(x) > 0$: the slope is increasing, so the graph bends upward (**convex** / $\cup$-shaped),
- $f''(x) < 0$: the slope is decreasing, so the graph bends downward (**concave** / $\cap$-shaped),
- $f''(x) = 0$ with a sign change: the graph switches curvature at an **inflection point**.

## 1. Domain, symmetry, and zeros

- **Domain:** $D = \mathbb{R}$.
- **Symmetry:** $f(-x) = (-x)^4 - 4(-x)^2 = f(x)$, so $f$ is an **even function** (symmetric across the $y$-axis).
- **Zeros:** $x^4 - 4x^2 = x^2(x - 2)(x + 2) = 0 \implies x = -2, \, 0, \, 2$.

## 2. First derivative and local extrema

Differentiate $f(x)$ and factor:

$$f'(x) = 4x^3 - 8x = 4x(x^2 - 2) = 4x(x - \sqrt{2})(x + \sqrt{2}).$$

The critical points are $x = -\sqrt{2}$, $x = 0$, and $x = \sqrt{2}$:

| Interval / Point | $(-\infty, -\sqrt{2})$ | $x = -\sqrt{2}$ | $(-\sqrt{2}, 0)$ | $x = 0$ | $(0, \sqrt{2})$ | $x = \sqrt{2}$ | $(\sqrt{2}, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $f'(x)$ | $-$ | $0$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| Behavior of $f(x)$ | $\searrow$ | **Min** ($-4$) | $\nearrow$ | **Max** ($0$) | $\searrow$ | **Min** ($-4$) | $\nearrow$ |

- **Local (and global) minima** at $x = -\sqrt{2}$ and $x = \sqrt{2}$, with value $f(\pm\sqrt{2}) = (\pm\sqrt{2})^4 - 4(\pm\sqrt{2})^2 = 4 - 8 = -4$.
- **Local maximum** at $x = 0$, with value $f(0) = 0$.

## 3. Second derivative, convexity, and inflection points

Differentiate $f'(x) = 4x^3 - 8x$:

$$f''(x) = 12x^2 - 8 = 4(3x^2 - 2).$$

Set $f''(x) = 0$:

$$3x^2 - 2 = 0 \implies x^2 = \frac{2}{3} \implies x = -\sqrt{\frac{2}{3}} = -\frac{\sqrt{6}}{3} \approx -0.816 \quad \text{or} \quad x = \sqrt{\frac{2}{3}} = \frac{\sqrt{6}}{3} \approx 0.816.$$

| Interval / Point | $(-\infty, -\sqrt{\frac{2}{3}})$ | $x = -\sqrt{\frac{2}{3}}$ | $(-\sqrt{\frac{2}{3}}, \sqrt{\frac{2}{3}})$ | $x = \sqrt{\frac{2}{3}}$ | $(\sqrt{\frac{2}{3}}, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Sign of $f''(x)$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| Curvature of $f(x)$ | $\cup$ convex | **Inflection** ($-\frac{20}{9}$) | $\cap$ concave | **Inflection** ($-\frac{20}{9}$) | $\cup$ convex |

Evaluate $f$ at $x = \pm\sqrt{\frac{2}{3}}$:

$$f\left(\pm\sqrt{\frac{2}{3}}\right) = \left(\frac{2}{3}\right)^2 - 4\left(\frac{2}{3}\right) = \frac{4}{9} - \frac{24}{9} = -\frac{20}{9} \approx -2.222.$$

- **Convex ($\cup$)** on $\left(-\infty, -\sqrt{\frac{2}{3}}\right]$ and $\left[\sqrt{\frac{2}{3}}, \infty\right)$.
- **Concave ($\cap$)** on $\left[-\sqrt{\frac{2}{3}}, \sqrt{\frac{2}{3}}\right]$.
- **Inflection points** at $\left(-\sqrt{\frac{2}{3}}, -\frac{20}{9}\right)$ and $\left(\sqrt{\frac{2}{3}}, -\frac{20}{9}\right)$.

## 4. Sketching the graph

The graph has a classic symmetric **"W" shape**:

1. It descends from $+\infty$ in the second quadrant, crosses the $x$-axis at $(-2, 0)$, and reaches the left valley bottom at $(-\sqrt{2}, -4) \approx (-1.41, -4)$ while remaining convex ($\cup$).
2. Rising from $(-\sqrt{2}, -4)$, it passes through the left inflection point $(-\sqrt{\frac{2}{3}}, -\frac{20}{9}) \approx (-0.82, -2.22)$, where it switches to concave ($\cap$) and arches up to touch the origin $(0, 0)$ as a local maximum.
3. By even symmetry, it arches back down through the right inflection point $(\sqrt{\frac{2}{3}}, -\frac{20}{9})$ (switching back to convex $\cup$), hits the right valley bottom at $(\sqrt{2}, -4)$, crosses $(2, 0)$, and climbs to $+\infty$.

## Quick verification

- Second derivative test at the three critical points:
  - $f''(0) = -8 < 0 \implies$ local maximum lies inside the concave region. ✓
  - $f''(\pm\sqrt{2}) = 12(2) - 8 = 16 > 0 \implies$ both local minima lie inside the convex regions. ✓
- Complete the square in $u = x^2$: $f(x) = (x^2 - 2)^2 - 4 \ge -4$, with equality at $x^2 = 2 \iff x = \pm\sqrt{2}$. ✓

## A concrete example

Notice where the inflection points sit relative to the extrema:

- Horizontal position: $0 < \sqrt{\frac{2}{3}} \approx 0.82 < \sqrt{2} \approx 1.41$,
- Vertical height: $f(0) = 0 > f\left(\sqrt{\frac{2}{3}}\right) = -\frac{20}{9} \approx -2.22 > f(\sqrt{2}) = -4$.

Every smooth transition from a local maximum ($\cap$) to a local minimum ($\cup$) must pass through an inflection point in between!

## How I would explain this in class

> For $f(x) = x^4 - 4x^2$, the first derivative $f'(x) = 4x(x^2-2)$ gives a W-shaped graph with two symmetric minima at $(\pm\sqrt{2}, -4)$ and a central local maximum at $(0, 0)$. The second derivative $f''(x) = 4(3x^2-2)$ tells us how the W bends: it is concave ($\cap$) on the middle arch between $x = -\sqrt{2/3}$ and $x = \sqrt{2/3}$, convex ($\cup$) outside that interval, and changes curvature at the two inflection points $(\pm\sqrt{2/3}, -20/9)$.

## Related workbook topics

- [Exercise 1: A Cubic Polynomial](problem_01_solution.md)
- [Exercise 10: Complete Function Analysis](problem_10_solution.md)
