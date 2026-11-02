# Exercise 9. One-Sided Limits and an Asymptote

## The question

Analyze the left-hand and right-hand limits of

$$f(x)=\frac1{x-2}$$

as $x\to2$. Does the two-sided limit exist? Interpret the result on a sketch of the graph and identify the vertical asymptote.

## Before calculating: what idea do we need?

When $x\to2$, the numerator of $f(x)=\dfrac{1}{x-2}$ is a nonzero constant ($1$) while the denominator $x-2$ approaches $0$. Dividing $1$ by a number tiny in magnitude produces a result huge in magnitude ($\left|\dfrac{1}{x-2}\right|\to+\infty$).

However, the **sign** of the result depends on whether $x$ approaches $2$ from the left ($x<2$, so $x-2<0$) or from the right ($x>2$, so $x-2>0$). That is why we must examine the two **one-sided limits** separately.

## 1. Left-hand limit ($x\to2^-$)

When $x$ approaches $2$ from the left, we have $x<2$, which means the denominator $x-2$ is a tiny **negative** number ($x-2\to0^-$). Dividing $+1$ by a tiny negative number gives a large negative number:

$$\lim_{x\to2^-}\frac{1}{x-2} = \left[\frac{1}{0^-}\right] = -\infty.$$

## 2. Right-hand limit ($x\to2^+$)

When $x$ approaches $2$ from the right, we have $x>2$, which means the denominator $x-2$ is a tiny **positive** number ($x-2\to0^+$). Dividing $+1$ by a tiny positive number gives a large positive number:

$$\lim_{x\to2^+}\frac{1}{x-2} = \left[\frac{1}{0^+}\right] = +\infty.$$

## 3. Does the two-sided limit exist?

A two-sided limit $\lim_{x\to2}f(x)$ exists only if the left-hand limit and the right-hand limit are **equal**. Here:

$$\lim_{x\to2^-}f(x) = -\infty \neq +\infty = \lim_{x\to2^+}f(x).$$

Therefore, the two-sided limit $\lim_{x\to2}\dfrac{1}{x-2}$ **does not exist** (not even as an improper limit $\pm\infty$).

## 4. Geometric interpretation and vertical asymptote

The graph of $f(x)=\dfrac{1}{x-2}$ is the standard hyperbola $y=\dfrac{1}{x}$ shifted $2$ units to the right:

```
        y
        |      :  |
        |      :  |  (right branch -> +infinity)
        |      :   \
--------+------2----+--------> x
        |    / :
        |   |  :
        |   |  :  (left branch -> -infinity)
            x = 2
```

- As $x$ nears $2$ from the left, the curve plunges straight down toward $-\infty$.
- As $x$ nears $2$ from the right, the curve shoots straight up toward $+\infty$.
- The vertical line **$x=2$ is a vertical asymptote** of the graph of $f$.

## Quick verification

Let us write $x=2+h$:

- From the left, $h=-10^{-k}$ ($k\in\mathbb{N}$): $f(2-10^{-k}) = \dfrac{1}{-10^{-k}} = -10^k \xrightarrow[k\to\infty]{} -\infty$. ✓
- From the right, $h=+10^{-k}$ ($k\in\mathbb{N}$): $f(2+10^{-k}) = \dfrac{1}{10^{-k}} = +10^k \xrightarrow[k\to\infty]{} +\infty$. ✓

## A concrete example

Let us compute $f(x)=\dfrac{1}{x-2}$ on both sides of $x=2$:

| Approaching from the left ($x<2$) | $f(x)$ | Approaching from the right ($x>2$) | $f(x)$ |
|---|---|---|---|
| $x=1.9$ | $-10$ | $x=2.1$ | $+10$ |
| $x=1.99$ | $-100$ | $x=2.01$ | $+100$ |
| $x=1.999$ | $-1000$ | $x=2.001$ | $+1000$ |

## How I would explain this in class

> When $x$ gets close to $2$, the bottom $x-2$ goes to $0$ while the top stays at $1$, so the fraction blows up in size. Which way it blows up depends on the sign of $x-2$: for $x<2$, $x-2$ is negative so the limit from the left is $-\infty$; for $x>2$, $x-2$ is positive so the limit from the right is $+\infty$. Because $-\infty\neq+\infty$, the two-sided limit does not exist, and the line $x=2$ is a vertical asymptote.

## Related workbook topics

- [Exercise 7: Limit at a point and canceling a factor](problem_07_solution.md)
- [Exercise 10: Continuity of a piecewise function](problem_10_solution.md)
