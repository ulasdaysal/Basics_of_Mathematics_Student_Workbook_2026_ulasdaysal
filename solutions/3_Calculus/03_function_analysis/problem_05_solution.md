# Exercise 5. An Exponential Function with a Maximum

## The question

Analyze the monotonicity and extrema of

$$f(x)=xe^{-x}.$$

Also examine the behavior as $x\to\infty$ and explain how the limit affects the shape of the graph on the right-hand side.

## Before calculating: what idea do we need?

The function $f(x) = xe^{-x} = \frac{x}{e^x}$ is a tug-of-war between two factors: the linear factor $x$ wants to grow, while the exponential decay factor $e^{-x}$ pulls the product toward zero. Near $x = 0$, linear growth wins and the function rises; for larger $x$, exponential decay overwhelms any polynomial, creating a peak and then pulling the graph back down toward the horizontal axis.

## 1. Domain and derivative

The domain is $D = \mathbb{R}$, and the only zero is $x = 0$ (since $e^{-x} > 0$ for all $x$).

Using the product rule with $(e^{-x})' = -e^{-x}$:

$$f'(x) = 1\cdot e^{-x} + x(-e^{-x}) = (1 - x)e^{-x}.$$

## 2. Monotonicity and extrema

Because $e^{-x} > 0$ for every $x \in \mathbb{R}$, the sign of $f'(x)$ is determined entirely by the linear factor $1 - x$:

- $f'(x) = 0 \iff 1 - x = 0 \iff x = 1$,
- $f'(x) > 0 \iff x < 1$,
- $f'(x) < 0 \iff x > 1$.

| Interval / Point | $(-\infty, 1)$ | $x = 1$ | $(1, \infty)$ |
| :--- | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+$ | $0$ | $-$ |
| Behavior of $f(x)$ | $\nearrow$ increasing | **Global max** ($e^{-1}$) | $\searrow$ decreasing |

- **Strictly increasing** on $(-\infty, 1]$.
- **Strictly decreasing** on $[1, \infty)$.
- **Local and global maximum** at $x = 1$ with value $f(1) = 1\cdot e^{-1} = \frac{1}{e} \approx 0.368$.

## 3. Behavior as $x \to \infty$ (and $x \to -\infty$)

Rewrite $f(x) = \frac{x}{e^x}$ for $x \to \infty$ (an $\frac{\infty}{\infty}$ indeterminate form) and apply L'Hôpital's rule (or standard growth hierarchy):

$$\lim_{x\to\infty} xe^{-x} = \lim_{x\to\infty} \frac{x}{e^x} \stackrel{\text{H}}{=} \lim_{x\to\infty} \frac{1}{e^x} = 0.$$

Thus $y = 0$ is a **right horizontal asymptote** (approached from above, since $f(x) > 0$ for $x > 0$).

On the left, as $x \to -\infty$, we have $x \to -\infty$ and $e^{-x} \to +\infty$, so $\lim_{x\to-\infty} xe^{-x} = -\infty$ (no asymptote on the left).

## 4. How the limit affects the shape of the graph on the right-hand side

After reaching its peak at $(1, \frac{1}{e})$, the function is strictly decreasing ($f'(x) < 0$) on $[1, \infty)$, yet it remains strictly positive ($f(x) > 0$) and approaches $0$. To decrease forever while never crossing $y = 0$, the graph cannot keep curving downward — it must **flatten out**, switching from concave (cupping downward near the peak) to convex (cupping upward) at an inflection point ($x = 2$, where $f''(x) = (x-2)e^{-x} = 0$) and skimming asymptotically along the top of the positive $x$-axis.

## Quick verification

- Check $f''(x) = (x - 2)e^{-x}$: at $x = 1$, $f''(1) = -e^{-1} < 0$ (confirms the maximum), and for $x > 2$, $f''(x) > 0$ (confirms the convex tail approaching $y = 0$). ✓
- Compare values around $x = 1$: $f(0) = 0 < f(1) \approx 0.368 > f(2) = \frac{2}{e^2} \approx 0.271 > 0$. ✓

## A concrete example

Watch how quickly $e^x$ overtakes $x$ as $x$ grows:

- $x = 1$: $f(1) = \frac{1}{e} \approx 0.3679$ (peak),
- $x = 2$: $f(2) = \frac{2}{e^2} \approx 0.2707$ (inflection point),
- $x = 5$: $f(5) = \frac{5}{e^5} \approx 0.0337$,
- $x = 10$: $f(10) = \frac{10}{e^{10}} \approx 0.00045$.

By $x = 10$, the graph is less than half a thousandth of a unit above the $x$-axis.

## How I would explain this in class

> Differentiating $f(x) = xe^{-x}$ gives $f'(x) = (1-x)e^{-x}$. Since $e^{-x}$ is always positive, the sign of the derivative comes purely from $1-x$: positive before $1$ and negative after $1$. So the function climbs from $-\infty$ through the origin to a single maximum of $\frac{1}{e}$ at $x = 1$. After $x = 1$, $e^{-x}$ dominates $x$, pulling the graph back down toward $\lim_{x\to\infty} xe^{-x} = 0$, which forces the right tail to bend smoothly and hug the positive $x$-axis from above.

## Related workbook topics

- [Exercise 6: A Logarithmic Function](problem_06_solution.md)
- [Exercise 13: A Logarithm and an Asymptote](problem_13_solution.md)
