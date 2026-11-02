# Exercise 6. From a Sequence to a Function — Limit at Infinity

## The question

Compute

$$\lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2}.$$

Compare the method with Exercise 1. Explain what changes when moving from $n$ to a real variable $x$, and what stays the same.

## Before calculating: what idea do we need?

A sequence $(a_n)$ is just a function whose domain is restricted to positive integers $n\in\{1,2,3,\dots\}$, whereas a function $f(x)$ takes all real values $x\in\mathbb{R}$ (outside the zeros of the denominator).

When $x\to\infty$, the algebraic behavior of polynomials in $x$ is identical to that of polynomials in $n$: the highest-degree term $x^2$ dominates, and lower-degree terms vanish after dividing by $x^2$.

## 1. Factor out and cancel the dominant power $x^2$

For $x>0$ (since $x\to+\infty$, we may assume $x>1$), $x^2\neq0$. Factoring $x^2$ out of the numerator and denominator:

$$\frac{3x^2-x+1}{5x^2+4x-2} = \frac{x^2\left(3-\dfrac{1}{x}+\dfrac{1}{x^2}\right)}{x^2\left(5+\dfrac{4}{x}-\dfrac{2}{x^2}\right)} = \frac{3-\dfrac{1}{x}+\dfrac{1}{x^2}}{5+\dfrac{4}{x}-\dfrac{2}{x^2}}.$$

## 2. Compute the limit as $x\to\infty$

Using the elementary limits $\lim_{x\to\infty}\dfrac{1}{x}=0$ and $\lim_{x\to\infty}\dfrac{1}{x^2}=0$, we obtain:

$$\lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2} = \frac{3-0+0}{5+0-0} = \frac{3}{5}.$$

## 3. What stays the same compared to Exercise 1

- **The indeterminate form** is still $\dfrac{\infty}{\infty}$.
- **The algebraic mechanism** is identical: identify the highest degree ($2$), factor out $x^2$, cancel it, and use the fact that reciprocals $\dfrac{1}{x^k}\to0$.
- **The shortcut rule** is identical: for equal degrees, the limit at infinity is the ratio of the leading coefficients, $\dfrac{3}{5}$.

## 4. What changes when moving from $n$ to a real variable $x$

1. **Continuous vs. discrete approach:** In Exercise 1, $n$ steps through isolated integers $1,2,3,\dots$, whereas here $x$ slides continuously through all large real numbers (e.g., $x=100.37$, $x=1000\pi$).
2. **Geometric interpretation:** On the graph of $y=f(x)$, $\lim_{x\to\infty}f(x)=\dfrac{3}{5}$ means the line $y=\dfrac{3}{5}$ is a **horizontal asymptote** of the curve as $x\to+\infty$ (and in fact also as $x\to-\infty$, a direction that does not exist for $n\in\mathbb{N}$).

## Quick verification

By polynomial division:

$$\frac{3x^2-x+1}{5x^2+4x-2} = \frac{3}{5} - \frac{\dfrac{17}{5}x-\dfrac{11}{5}}{5x^2+4x-2}.$$

As $x\to\infty$, the degree-$1$ over degree-$2$ remainder fraction goes to $0$ (by Exercise 2), leaving $\dfrac{3}{5} = 0.6$. ✓

## A concrete example

Because $x$ is a real variable, we can evaluate $f(x)$ at non-integer points as well as negative points:

- At $x=50.5$: $f(50.5)=\dfrac{3(50.5)^2-50.5+1}{5(50.5)^2+4(50.5)-2}=\dfrac{7601.25}{12951.25}\approx 0.5869$.
- At $x=1000$: $f(1000)=\dfrac{2\,999\,001}{5\,003\,998}\approx 0.59932$.
- At $x=-1000$: $f(-1000)=\dfrac{3\,001\,001}{4\,995\,998}\approx 0.60068$.

In both directions, the graph approaches the horizontal asymptote $y=0.6$.

## How I would explain this in class

> Algebraically, solving this limit is the exact same move as Exercise 1: divide top and bottom by $x^2$, watch $\dfrac{1}{x}$ and $\dfrac{1}{x^2}$ go to $0$, and get the leading-coefficient ratio $\dfrac{3}{5}$. What changes conceptually is that $x$ varies continuously over all real numbers instead of jumping across integers $n$, so the result $\dfrac{3}{5}$ represents a horizontal asymptote $y=\dfrac{3}{5}$ of a continuous curve.

## Related workbook topics

- [Exercise 1: Dominant terms in a sequence](problem_01_solution.md)
- [Exercise 2: Different growth rates](problem_02_solution.md)
