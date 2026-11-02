# Exercise 15. Find the Error in the Monotonicity Analysis

## The question

For the function $f(x)=x^3-3x$, the derivative was correctly computed as

$$f'(x)=3(x-1)(x+1).$$

However, a student wrote the following conclusion:

> The derivative is positive between its zeros and negative outside them. Therefore, the function is decreasing on $(-\infty,-1)\cup(1,\infty)$, increasing on $(-1,1)$, has a local minimum at $x=-1$, and a local maximum at $x=1$.

1. Without differentiating again, explain why merely identifying the zeros of the derivative does not justify the stated sign chart, and find the error in the student's reasoning.
2. Construct the correct sign chart for $f'(x)$.
3. Give the correct intervals of monotonicity and the character of the extrema.
4. In each of the three intervals, choose one simple test point and show that the sign of the derivative confirms your classification.

## Before calculating: what idea do we need?

Knowing the roots of a factored polynomial $f'(x) = a(x - x_1)(x - x_2)$ only tells us **where the sign can change**; it does not tell us **which intervals are positive and which are negative** until we check the leading coefficient $a$ (or evaluate test points). Even worse, two functions with the exact same roots — such as $+3(x-1)(x+1)$ and $-3(x-1)(x+1)$ — have completely opposite signs everywhere else!

## 1. Finding the error in the student's reasoning

- **Why the zeros alone do not determine the sign chart:** The roots $x = -1$ and $x = 1$ only partition the real line into the three intervals $(-\infty, -1)$, $(-1, 1)$, and $(1, \infty)$. Both $3(x-1)(x+1)$ and $-3(x-1)(x+1)$ share the exact same zeros, yet their signs are opposite on every interval.
- **The student's specific error:** In $f'(x) = 3(x-1)(x+1) = 3x^2 - 3$, the leading coefficient is **$a = +3 > 0$**, so the parabola of $f'(x)$ opens **upward** ($\cup$). An upward-opening parabola is **negative between its roots and positive outside them** — the exact opposite of what the student wrote! (Moreover, as a secondary notation error, monotonicity intervals should be listed separately as $(-\infty, -1]$ and $[1, \infty)$ rather than joined with a union symbol $\cup$.)

## 2. Correct sign chart for $f'(x) = 3(x - 1)(x + 1)$

Track the sign of each factor across $x = -1$ and $x = 1$:

| Interval / Point | $(-\infty, -1)$ | $x = -1$ | $(-1, 1)$ | $x = 1$ | $(1, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Factor $3$ | $+$ | $+$ | $+$ | $+$ | $+$ |
| Factor $x + 1$ | $-$ | $0$ | $+$ | $+$ | $+$ |
| Factor $x - 1$ | $-$ | $-$ | $-$ | $0$ | $+$ |
| **Sign of $f'(x)$** | $+$ | $0$ | $-$ | $0$ | $+$ |
| **Behavior of $f(x)$** | $\nearrow$ increasing | **Local max** ($2$) | $\searrow$ decreasing | **Local min** ($-2$) | $\nearrow$ increasing |

## 3. Correct intervals of monotonicity and character of the extrema

- **Strictly increasing** on $(-\infty, -1]$ and on $[1, \infty)$.
- **Strictly decreasing** on $[-1, 1]$.
- **Local maximum** at $x = -1$, because $f'(x)$ changes sign from $+$ to $-$, with value
  $$f(-1) = (-1)^3 - 3(-1) = -1 + 3 = 2.$$
- **Local minimum** at $x = 1$, because $f'(x)$ changes sign from $-$ to $+$, with value
  $$f(1) = 1^3 - 3(1) = 1 - 3 = -2.$$

## 4. Confirming with a simple test point in each of the three intervals

- **Interval $(-\infty, -1)$ — test point $x = -2$:**
  $$f'(-2) = 3(-2 - 1)(-2 + 1) = 3(-3)(-1) = +9 > 0 \implies f \text{ is increasing on } (-\infty, -1).$$
- **Interval $(-1, 1)$ — test point $x = 0$:**
  $$f'(0) = 3(0 - 1)(0 + 1) = 3(-1)(1) = -3 < 0 \implies f \text{ is decreasing on } (-1, 1).$$
- **Interval $(1, \infty)$ — test point $x = 2$:**
  $$f'(2) = 3(2 - 1)(2 + 1) = 3(1)(3) = +9 > 0 \implies f \text{ is increasing on } (1, \infty).$$

## Quick verification

Compare the actual function values at the critical points:

$$f(-1) = 2 \quad \text{and} \quad f(1) = -2.$$

In the student's flawed conclusion, the function was supposedly *increasing* on $(-1, 1)$ from a "local minimum" of $f(-1) = 2$ up to a "local maximum" of $f(1) = -2$ — which is impossible because $2 > -2$! Checking $f(-1)$ and $f(1)$ immediately catches the reversed signs. ✓

## A concrete example

Evaluate $f(x) = x^3 - 3x$ at $x = -2, -1, 0, 1, 2$ to watch the true trajectory of the function:

| $x$ | $-2$ | $-1$ | $0$ | $1$ | $2$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| $f(x) = x^3 - 3x$ | $-2$ | $2$ (Max) | $0$ | $-2$ (Min) | $2$ |

Going from left to right, the heights follow $-2 \nearrow 2 \searrow 0 \searrow -2 \nearrow 2$, matching our corrected table at every step.

## How I would explain this in class

> The student found the right roots of $f'(x) = 3(x-1)(x+1)$ at $x = \pm 1$, but flipped the entire sign chart upside down. Since the leading coefficient $+3$ is positive, the parabola of $f'(x)$ opens upward, meaning $f'(x)$ is negative between $-1$ and $1$ and positive outside — as a quick check at $x = 0$ shows ($f'(0) = -3 < 0$). That reverses every conclusion: $f$ increases on $(-\infty, -1]$ to a local maximum of $2$ at $x = -1$, decreases on $[-1, 1]$ to a local minimum of $-2$ at $x = 1$, and increases on $[1, \infty)$.

## Related workbook topics

- [Exercise 1: A Cubic Polynomial](problem_01_solution.md)
- [Exercise 11: A Parameter and the Number of Extrema](problem_11_solution.md)
