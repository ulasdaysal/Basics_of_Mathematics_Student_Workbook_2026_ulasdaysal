# Exercise 4. A Function with Two Vertical Asymptotes

## The question

Analyze

$$f(x)=\frac{1}{x^2-1}.$$

Determine the domain, asymptotes, sign, and monotonicity on the intervals of the domain. Explain why each interval must be analyzed separately.

## Before calculating: what idea do we need?

When the denominator vanishes at several points, those points slice the real line into disjoint open intervals. Across a vertical asymptote, a function can jump from $-\infty$ to $+\infty$ (or vice versa), so properties like sign and monotonicity only hold **within each connected component** of the domain, never across the breaks.

## 1. Domain, symmetry, and sign

Factor the denominator: $x^2 - 1 = (x - 1)(x + 1)$.

- **Domain:** $x^2 - 1 \neq 0 \implies x \neq -1$ and $x \neq 1$. Thus the domain consists of three disjoint intervals:
  $$D = (-\infty, -1) \cup (-1, 1) \cup (1, \infty).$$
- **Symmetry:** $f(-x) = \frac{1}{(-x)^2 - 1} = f(x)$, so $f$ is an **even function** (symmetric about the $y$-axis).
- **Zeros and sign:** The numerator is $1 \neq 0$, so $f$ has **no zeros**. Its sign is the sign of $x^2 - 1$:
  - $f(x) > 0$ on $(-\infty, -1)$ and $(1, \infty)$ (above the $x$-axis),
  - $f(x) < 0$ on $(-1, 1)$ (below the $x$-axis).

## 2. Asymptotes

- **Vertical asymptotes at $x = -1$ and $x = 1$:**
  $$\lim_{x\to -1^-} f(x) = +\infty, \qquad \lim_{x\to -1^+} f(x) = -\infty,$$
  $$\lim_{x\to 1^-} f(x) = -\infty, \qquad \lim_{x\to 1^+} f(x) = +\infty.$$
- **Horizontal asymptote at $y = 0$:**
  $$\lim_{x\to \pm\infty} \frac{1}{x^2 - 1} = 0.$$

## 3. Derivative and monotonicity on each interval

Differentiating $f(x) = (x^2 - 1)^{-1}$ by the chain rule:

$$f'(x) = -\frac{2x}{(x^2 - 1)^2}.$$

Since $(x^2 - 1)^2 > 0$ everywhere on $D$, the sign of $f'(x)$ is the sign of $-2x$:

| Interval / Point | $(-\infty, -1)$ | $x = -1$ | $(-1, 0)$ | $x = 0$ | $(0, 1)$ | $x = 1$ | $(1, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $f(x)$ | $+$ | undef. | $-$ | $-1$ | $-$ | undef. | $+$ |
| Sign of $f'(x)$ | $+$ | undef. | $+$ | $0$ | $-$ | undef. | $-$ |
| Behavior of $f(x)$ | $\nearrow$ ($0$ to $+\infty$) | V.A. | $\nearrow$ ($-\infty$ to $-1$) | **Local max** ($-1$) | $\searrow$ ($-1$ to $-\infty$) | V.A. | $\searrow$ ($+\infty$ to $0$) |

- **Strictly increasing** on $(-\infty, -1)$ and on $(-1, 0]$.
- **Strictly decreasing** on $[0, 1)$ and on $(1, \infty)$.
- **Local maximum** at $x = 0$ with value $f(0) = -1$.

## 4. Why each interval must be analyzed separately

The Mean Value Theorem guarantees that $f' > 0 \implies f$ is increasing **only on an interval** where $f$ is continuous and differentiable. Here, $f'(x) > 0$ on both $(-\infty, -1)$ and $(-1, 0)$, yet $f$ is **not** increasing on their union $(-\infty, -1) \cup (-1, 0)$: at the asymptote $x = -1$, the function blows up to $+\infty$ on the left and restarts at $-\infty$ on the right! Every break in the domain resets the function's values.

## Quick verification

- Even symmetry check: the increasing behavior on $(-\infty, -1)$ and $(-1, 0]$ mirrors the decreasing behavior on $[0, 1)$ and $(1, \infty)$. ✓
- Second derivative at $x = 0$: $f''(x) = \frac{6x^2 + 2}{(x^2-1)^3} \implies f''(0) = -2 < 0$, confirming a local maximum at $(0, -1)$. ✓

## A concrete example

Take $x_1 = -2 \in (-\infty, -1)$ and $x_2 = -0.5 \in (-1, 0)$. Even though $x_1 < x_2$ and $f'(x) > 0$ at both points, we get

$$f(-2) = \frac{1}{4 - 1} = \frac{1}{3} > 0, \qquad f(-0.5) = \frac{1}{0.25 - 1} = -\frac{4}{3} < 0.$$

So $f(-2) > f(-0.5)$ despite positive derivatives on both intervals — vivid proof that monotonicity cannot be merged across the vertical asymptote $x = -1$.

## How I would explain this in class

> The denominator $x^2 - 1$ is zero at $x = \pm 1$, splitting the domain into three separate intervals. On the outer intervals $f$ is positive; on the middle interval $(-1, 1)$ it is negative and forms an upside-down arch with a local maximum at $(0, -1)$. Because the graph jumps between $+\infty$ and $-\infty$ at $x = \pm 1$, we have to state monotonicity on each interval individually rather than gluing intervals together.

## Related workbook topics

- [Exercise 3: A Rational Function](problem_03_solution.md)
- [Exercise 10: Complete Function Analysis](problem_10_solution.md)
