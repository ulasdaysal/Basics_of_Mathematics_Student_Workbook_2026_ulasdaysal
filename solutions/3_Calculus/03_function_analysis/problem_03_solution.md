# Exercise 3. A Rational Function

## The question

Analyze the domain, zeros, asymptotes, and monotonicity of

$$f(x)=\frac{x+1}{x-2}.$$

Finally, sketch a graph consistent with all the information obtained.

## Before calculating: what idea do we need?

A linear fractional function (homographic function) $f(x) = \frac{ax+b}{cx+d}$ splits its domain at the point where the denominator vanishes. Before differentiating, rewriting the numerator in terms of the denominator separates $f(x)$ into a constant plus a simple reciprocal $\frac{k}{x-2}$. That single algebraic step makes the asymptotes and derivative completely transparent.

## 1. Domain and zeros

- **Domain:** The denominator cannot be zero: $x - 2 \neq 0 \implies x \neq 2$. Thus
  $$D = \mathbb{R} \setminus \{2\} = (-\infty, 2) \cup (2, \infty).$$
- **Zero ($x$-intercept):** A fraction equals zero when its numerator is zero and its denominator is non-zero:
  $$x + 1 = 0 \implies x = -1 \in D.$$
- **$y$-intercept:** $f(0) = \frac{0+1}{0-2} = -\frac{1}{2}$.

## 2. Asymptotes

Rewrite the formula by splitting off the constant part:

$$f(x) = \frac{(x - 2) + 3}{x - 2} = 1 + \frac{3}{x - 2}.$$

- **Vertical asymptote at $x = 2$:**
  - As $x \to 2^-$, $x - 2 \to 0^-$, so $\frac{3}{x-2} \to -\infty \implies \lim_{x \to 2^-} f(x) = -\infty$.
  - As $x \to 2^+$, $x - 2 \to 0^+$, so $\frac{3}{x-2} \to +\infty \implies \lim_{x \to 2^+} f(x) = +\infty$.
  Hence $x = 2$ is a two-sided vertical asymptote.
- **Horizontal asymptote at $y = 1$:**
  $$\lim_{x \to \pm\infty} \left(1 + \frac{3}{x - 2}\right) = 1 + 0 = 1.$$
  Hence $y = 1$ is the horizontal asymptote at both $-\infty$ and $+\infty$ (and there are no oblique asymptotes).

## 3. Derivative and monotonicity

Differentiate either by the quotient rule or directly from $f(x) = 1 + 3(x-2)^{-1}$:

$$f'(x) = \frac{1\cdot(x-2) - (x+1)\cdot 1}{(x-2)^2} = \frac{-3}{(x-2)^2}.$$

Since $(x - 2)^2 > 0$ for every $x \neq 2$ and the numerator is $-3 < 0$, we have $f'(x) < 0$ everywhere on the domain:

| Interval | $(-\infty, 2)$ | $x = 2$ | $(2, \infty)$ |
| :--- | :---: | :---: | :---: |
| Sign of $f'(x)$ | $-$ | undefined | $-$ |
| Behavior of $f(x)$ | $\searrow$ from $1$ to $-\infty$ | Vertical asymptote | $\searrow$ from $+\infty$ to $1$ |

- $f$ is **strictly decreasing on $(-\infty, 2)$** and **strictly decreasing on $(2, \infty)$**.
- Note: We do **not** say $f$ is decreasing on the union $(-\infty, 2) \cup (2, \infty)$, because for $0 < 3$ we have $f(0) = -\frac{1}{2} < f(3) = 4$.
- There are **no local extrema** ($f'(x)$ never vanishes).

## 4. Sketching the graph

Draw dashed guide lines for the vertical asymptote $x = 2$ and the horizontal asymptote $y = 1$:

- **Left branch ($x < 2$):** Starts just below the horizontal line $y = 1$ as $x \to -\infty$, decreases smoothly through $(-1, 0)$ and $(0, -\frac{1}{2})$, and plunges toward $-\infty$ alongside the left side of $x = 2$.
- **Right branch ($x > 2$):** Drops down from $+\infty$ alongside the right side of $x = 2$, passes through $(3, 4)$ and $(5, 2)$, and flattens out from above toward the horizontal line $y = 1$ as $x \to +\infty$.

## Quick verification

Check points on both sides of $x = 2$ using both forms $f(x) = \frac{x+1}{x-2}$ and $1 + \frac{3}{x-2}$:

- At $x = -1$: $\frac{-1+1}{-1-2} = 0$ and $1 + \frac{3}{-3} = 0$. ✓
- At $x = 1$: $f(1) = -2 < f(0) = -0.5 < f(-1) = 0$ (decreasing on the left branch). ✓
- At $x = 3, 5$: $f(3) = 4 > f(5) = 2 > 1$ (decreasing on the right branch and staying above $y = 1$). ✓

## A concrete example

For very large inputs such as $x = 102$ and $x = -98$:

$$f(102) = 1 + \frac{3}{100} = 1.03, \qquad f(-98) = 1 + \frac{3}{-100} = 0.97.$$

You can see immediately why $y = 1$ is the horizontal asymptote: the term $\frac{3}{x-2}$ is positive on the right (holding the graph slightly above $1$) and negative on the left (holding the graph slightly below $1$).

## How I would explain this in class

> Rewrite $\frac{x+1}{x-2}$ as $1 + \frac{3}{x-2}$. That shows the graph is just the hyperbola $y = \frac{3}{x}$ shifted $2$ units right and $1$ unit up. Its asymptotes are $x = 2$ and $y = 1$, its zero is at $x = -1$, and its derivative $f'(x) = \frac{-3}{(x-2)^2}$ is always negative, so each of the two hyperbola branches decreases across its entire interval.

## Related workbook topics

- [Exercise 4: A Function with Two Vertical Asymptotes](problem_04_solution.md)
- [Exercise 9: An Oblique Asymptote](problem_09_solution.md)
