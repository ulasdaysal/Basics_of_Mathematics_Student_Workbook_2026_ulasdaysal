# Exercise 10. Complete Function Analysis

## The question

Perform a complete analysis of

$$f(x)=\frac{x}{x^2+1}.$$

Include the domain, symmetry, zeros, limits, monotonicity, extrema, and convexity. Finally, produce a sketch based only on this information.

## Before calculating: what idea do we need?

A complete function analysis follows a systematic checklist so no geometric detail is missed:

1. **Algebraic structure** (domain, symmetry, zeros, sign) gives the global frame.
2. **Limits and asymptotes** show what happens at the edges of the domain.
3. **First derivative $f'(x)$** determines rising/falling intervals and peaks/valleys.
4. **Second derivative $f''(x)$** determines how the curve bends and where its curvature switches.

## 1. Domain, symmetry, zeros, and limits

- **Domain:** Since $x^2 + 1 \ge 1 > 0$ for all $x \in \mathbb{R}$, the denominator never vanishes: $D = \mathbb{R}$ (no vertical asymptotes).
- **Symmetry:** $f(-x) = \frac{-x}{(-x)^2 + 1} = -\frac{x}{x^2 + 1} = -f(x)$, so $f$ is an **odd function** (symmetric with respect to the origin $(0,0)$).
- **Zero and sign:** $f(x) = 0 \iff x = 0$. Since $x^2 + 1 > 0$, $f(x) > 0$ on $(0, \infty)$ and $f(x) < 0$ on $(-\infty, 0)$.
- **Limits at infinity and horizontal asymptote:**
  $$\lim_{x\to \pm\infty} \frac{x}{x^2 + 1} = \lim_{x\to \pm\infty} \frac{\frac{1}{x}}{1 + \frac{1}{x^2}} = 0.$$
  Thus **$y = 0$ is a two-sided horizontal asymptote** (approached from above as $x \to +\infty$ and from below as $x \to -\infty$).

## 2. First derivative, monotonicity, and extrema

Using the quotient rule:

$$f'(x) = \frac{1\cdot(x^2 + 1) - x\cdot(2x)}{(x^2 + 1)^2} = \frac{1 - x^2}{(x^2 + 1)^2} = \frac{(1 - x)(1 + x)}{(x^2 + 1)^2}.$$

Since $(x^2 + 1)^2 > 0$ everywhere, the sign of $f'(x)$ matches the sign of $1 - x^2$:

| Interval / Point | $(-\infty, -1)$ | $x = -1$ | $(-1, 1)$ | $x = 1$ | $(1, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Sign of $f'(x)$ | $-$ | $0$ | $+$ | $0$ | $-$ |
| Behavior of $f(x)$ | $\searrow$ ($0$ to $-\frac{1}{2}$) | **Min** ($-\frac{1}{2}$) | $\nearrow$ ($-\frac{1}{2}$ to $\frac{1}{2}$) | **Max** ($\frac{1}{2}$) | $\searrow$ ($\frac{1}{2}$ to $0$) |

- **Strictly increasing** on $[-1, 1]$.
- **Strictly decreasing** on $(-\infty, -1]$ and $[1, \infty)$.
- **Local and global minimum** at $x = -1$ with value $f(-1) = -\frac{1}{2}$.
- **Local and global maximum** at $x = 1$ with value $f(1) = \frac{1}{2}$.

## 3. Second derivative, convexity, and inflection points

Differentiate $f'(x) = (1 - x^2)(x^2 + 1)^{-2}$:

$$f''(x) = \frac{-2x(x^2 + 1)^2 - (1 - x^2)\cdot 2(x^2 + 1)(2x)}{(x^2 + 1)^4} = \frac{2x\bigl(-(x^2 + 1) - 2(1 - x^2)\bigr)}{(x^2 + 1)^3} = \frac{2x(x^2 - 3)}{(x^2 + 1)^3}.$$

Factoring the numerator gives $2x(x - \sqrt{3})(x + \sqrt{3}) = 0$, so $f''(x) = 0$ at $x = -\sqrt{3}, \, 0, \, \sqrt{3}$:

| Interval / Point | $(-\infty, -\sqrt{3})$ | $x = -\sqrt{3}$ | $(-\sqrt{3}, 0)$ | $x = 0$ | $(0, \sqrt{3})$ | $x = \sqrt{3}$ | $(\sqrt{3}, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $f''(x)$ | $-$ | $0$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| Curvature of $f(x)$ | $\cap$ concave | **Infl.** ($-\frac{\sqrt{3}}{4}$) | $\cup$ convex | **Infl.** ($0$) | $\cap$ concave | **Infl.** ($\frac{\sqrt{3}}{4}$) | $\cup$ convex |

- **Convex ($\cup$)** on $[-\sqrt{3}, 0]$ and $[\sqrt{3}, \infty)$.
- **Concave ($\cap$)** on $(-\infty, -\sqrt{3}]$ and $[0, \sqrt{3}]$.
- **Three inflection points:** $\left(-\sqrt{3}, -\frac{\sqrt{3}}{4}\right) \approx (-1.73, -0.43)$, $(0, 0)$, and $\left(\sqrt{3}, \frac{\sqrt{3}}{4}\right) \approx (1.73, 0.43)$.

## 4. Sketching the graph

1. Moving from $-\infty$, the graph starts just below the $x$-axis ($y = 0$), decreasing and concave ($\cap$) until the left inflection point $(-\sqrt{3}, -\frac{\sqrt{3}}{4})$.
2. It switches to convex ($\cup$), reaches its global minimum at $(-1, -\frac{1}{2})$, and turns upward toward the origin $(0, 0)$ (where it crosses with slope $f'(0) = 1$).
3. Passing through the inflection point $(0, 0)$, it becomes concave ($\cap$), climbs to its global maximum at $(1, \frac{1}{2})$, and begins descending.
4. At the right inflection point $(\sqrt{3}, \frac{\sqrt{3}}{4})$, it switches back to convex ($\cup$) so it can flatten out smoothly and approach $y = 0$ from above as $x \to +\infty$.

## Quick verification

- Algebraic bound: since $(x \mp 1)^2 \ge 0 \implies x^2 + 1 \ge \pm 2x$, dividing by $2(x^2 + 1) > 0$ directly proves $-\frac{1}{2} \le \frac{x}{x^2+1} \le \frac{1}{2}$, with equality only at $x = \pm 1$. ✓
- Odd symmetry check: if $f(x)$ is odd, $f'(x)$ must be even ($f'(-x) = f'(x)$) and $f''(x)$ must be odd ($f''(-x) = -f''(x)$), which matches $f'(x) = \frac{1-x^2}{(x^2+1)^2}$ and $f''(x) = \frac{2x(x^2-3)}{(x^2+1)^3}$. ✓

## A concrete example

Evaluating $f$ at $x = 0, \frac{1}{2}, 1, 2, 3$ shows the rise to $x = 1$ and the gentle decay afterward:

$$f(0) = 0, \quad f\left(\frac{1}{2}\right) = \frac{2}{5} = 0.4, \quad f(1) = \frac{1}{2} = 0.5, \quad f(2) = \frac{2}{5} = 0.4, \quad f(3) = \frac{3}{10} = 0.3.$$

Notice that $f(2) = f\left(\frac{1}{2}\right) = 0.4$ because $f\left(\frac{1}{x}\right) = \frac{1/x}{1/x^2 + 1} = \frac{x}{1 + x^2} = f(x)$!

## How I would explain this in class

> The function $f(x) = \frac{x}{x^2+1}$ is defined everywhere, odd, and approaches $y = 0$ at $\pm\infty$. Its first derivative $f'(x) = \frac{1-x^2}{(x^2+1)^2}$ shows that $f$ increases on $[-1, 1]$ from its minimum $( -1, -\frac{1}{2} )$ through the origin to its maximum $(1, \frac{1}{2})$, and decreases back toward zero outside $[-1, 1]$. The second derivative $f''(x) = \frac{2x(x^2-3)}{(x^2+1)^3}$ pinpoints the three inflection points at $x = 0$ and $x = \pm\sqrt{3}$ where the S-wave flips curvature.

## Related workbook topics

- [Exercise 4: A Function with Two Vertical Asymptotes](problem_04_solution.md)
- [Exercise 8: The Second Derivative](problem_08_solution.md)
