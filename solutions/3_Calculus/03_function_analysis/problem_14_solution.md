# Exercise 14. Reconstructing Information from the Derivative

## The question

It is known that

$$f'(x)=(x-1)(x+2).$$

Determine the monotonicity and the locations of the extrema, and sketch a possible qualitative shape of the function. Then, for

$$g(x)=\frac{x^3}{3}+\frac{x^2}{2}-2x$$

verify that $g'(x)=(x-1)(x+2)$, and compare the specific graph with the earlier qualitative sketch.

## Before calculating: what idea do we need?

The derivative $f'(x)$ already contains the **complete recipe for the shape** of $f(x)$: where it rises, where it falls, where its peaks and valleys are located horizontally, and even where its inflection point sits (at the vertex of $f'(x)$). The only thing $f'(x)$ does not fix is the vertical height: adding a constant $C$ shifts the graph of $f(x)$ up or down without changing $f'(x)$ at all.

## 1. Monotonicity and locations of extrema from $f'(x)$

We are given $f'(x) = (x - 1)(x + 2)$ on $\mathbb{R}$.

- **Critical points ($f'(x) = 0$):** $x = -2$ and $x = 1$.
- **Sign of $f'(x)$:** Because $f'(x) = x^2 + x - 2$ is an upward-opening parabola (leading coefficient $+1 > 0$), it is positive outside its roots and negative between them:

| Interval / Point | $(-\infty, -2)$ | $x = -2$ | $(-2, 1)$ | $x = 1$ | $(1, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| Behavior of $f(x)$ | $\nearrow$ increasing | **Local max** | $\searrow$ decreasing | **Local min** | $\nearrow$ increasing |

- **Strictly increasing** on $(-\infty, -2]$ and $[1, \infty)$.
- **Strictly decreasing** on $[-2, 1]$.
- **Local maximum** at $x = -2$ ($f'$ changes from $+$ to $-$).
- **Local minimum** at $x = 1$ ($f'$ changes from $-$ to $+$).
- **Inflection point location:** Since $f''(x) = (x^2 + x - 2)' = 2x + 1 = 0$ at $x = -\frac{1}{2}$ (halfway between $-2$ and $1$), $f$ is concave ($\cap$) on $(-\infty, -\frac{1}{2}]$ and convex ($\cup$) on $[-\frac{1}{2}, \infty)$.

## 2. Qualitative sketch of $f(x)$

Without knowing the constant of integration $C$, any valid sketch of $f(x)$ is an S-shaped cubic curve that:
1. Rises from $-\infty$ on the left to a rounded peak on the vertical line $x = -2$,
2. Falls across the interval $[-2, 1]$, passing through an inflection point at $x = -\frac{1}{2}$,
3. Bottoms out at a rounded valley on the vertical line $x = 1$, and then rises to $+\infty$ on the right.

## 3. Verifying $g'(x)$ and comparing with the specific graph of $g(x)$

Differentiate $g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x$ term by term and factor:

$$g'(x) = \frac{3x^2}{3} + \frac{2x}{2} - 2 = x^2 + x - 2 = (x - 1)(x + 2).$$

Thus $g(x)$ is the specific antiderivative of $f'(x)$ satisfying $g(0) = 0$. Now we can pin down the exact vertical coordinates of the key points for $g(x)$:

- **Local maximum at $x = -2$:**
  $$g(-2) = \frac{(-2)^3}{3} + \frac{(-2)^2}{2} - 2(-2) = -\frac{8}{3} + 2 + 4 = \frac{10}{3} \approx 3.33.$$
- **Inflection point at $x = -\frac{1}{2}$:**
  $$g\left(-\frac{1}{2}\right) = \frac{-1/8}{3} + \frac{1/4}{2} - 2\left(-\frac{1}{2}\right) = -\frac{1}{24} + \frac{1}{8} + 1 = \frac{13}{12} \approx 1.08.$$
- **Origin ($y$-intercept):** $g(0) = 0$.
- **Local minimum at $x = 1$:**
  $$g(1) = \frac{1}{3} + \frac{1}{2} - 2 = -\frac{7}{6} \approx -1.17.$$

**Comparison:** The graph of $g(x)$ has the **exact same shape, monotonicity intervals, and horizontal extremum locations ($x = -2$ and $x = 1$)** as our qualitative sketch; specifying $g(x)$ simply fixes the vertical position so the curve passes through $(0, 0)$, placing the peak at $(-2, \frac{10}{3})$ and the trough at $(1, -\frac{7}{6})$.

## Quick verification

Notice that the vertical drop from the local maximum to the local minimum is

$$g(-2) - g(1) = \frac{10}{3} - \left(-\frac{7}{6}\right) = \frac{27}{6} = \frac{9}{2} = 4.5,$$

and the inflection point height is the exact midpoint of the extremum heights:

$$\frac{g(-2) + g(1)}{2} = \frac{\frac{10}{3} - \frac{7}{6}}{2} = \frac{\frac{13}{6}}{2} = \frac{13}{12} = g\left(-\frac{1}{2}\right). \quad \checkmark$$

## A concrete example

Compare $g(x)$ with $h(x) = g(x) + 5 = \frac{x^3}{3} + \frac{x^2}{2} - 2x + 5$:

- Both have the exact same derivative $h'(x) = g'(x) = (x - 1)(x + 2)$.
- Both have their local maximum at $x = -2$ and local minimum at $x = 1$.
- For $g(x)$, the extrema are $(-2, \frac{10}{3})$ and $(1, -\frac{7}{6})$ (one above and one below the $x$-axis, so $g$ has $3$ real zeros).
- For $h(x)$, the extrema are $(-2, \frac{25}{3})$ and $(1, \frac{23}{6})$ (both above the $x$-axis, so $h$ has only $1$ real zero!).

## How I would explain this in class

> From $f'(x) = (x-1)(x+2)$ alone, we know the derivative is an upward-opening parabola with roots at $x = -2$ and $x = 1$. So any function $f$ with this derivative increases up to a local maximum at $x = -2$, decreases on $[-2, 1]$, and increases from a local minimum at $x = 1$. Checking $g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x$ confirms $g'(x) = x^2 + x - 2 = (x-1)(x+2)$, which locks that qualitative cubic shape into place vertically with passing through $(0,0)$, peak $(-2, \frac{10}{3})$, and minimum $(1, -\frac{7}{6})$.

## Related workbook topics

- [Exercise 1: A Cubic Polynomial](problem_01_solution.md)
- [Exercise 15: Find the Error in the Monotonicity Analysis](problem_15_solution.md)
