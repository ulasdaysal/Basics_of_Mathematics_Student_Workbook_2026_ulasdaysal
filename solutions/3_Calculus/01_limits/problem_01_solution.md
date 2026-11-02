# Exercise 1. Dominant Terms in a Sequence

## The question

Compute

$$\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7}.$$

Explain why the highest-degree terms determine the result.

## Before calculating: what idea do we need?

When $n\to\infty$, directly plugging in $\infty$ produces the indeterminate form $\dfrac{\infty}{\infty}$. To resolve it, we look at the **dominant term**—the highest power of $n$ appearing in the denominator (and numerator), which here is $n^2$.

Why does $n^2$ dominate? Because for very large $n$, $n^2$ grows much faster than $n$ or a constant. If we factor out $n^2$ from both the numerator and the denominator, the highest-degree terms become constants while every lower-degree term gets divided by $n$ or $n^2$ and shrinks to $0$.

## 1. Factor out the highest power of $n$

The highest power in both numerator and denominator is $n^2$. Factoring $n^2$ out of the numerator and denominator gives:

$$\frac{4n^2-3n+1}{2n^2+5n-7}=\frac{n^2\left(4-\dfrac{3}{n}+\dfrac{1}{n^2}\right)}{n^2\left(2+\dfrac{5}{n}-\dfrac{7}{n^2}\right)}.$$

## 2. Cancel $n^2$

Since $n\ge1$, $n^2\neq0$, so we can cancel the common factor $n^2$:

$$\frac{4n^2-3n+1}{2n^2+5n-7}=\frac{4-\dfrac{3}{n}+\dfrac{1}{n^2}}{2+\dfrac{5}{n}-\dfrac{7}{n^2}}.$$

## 3. Evaluate the limit of each piece

As $n\to\infty$, the elementary reciprocal sequences converge to zero:

$$\lim_{n\to\infty}\frac{1}{n}=0,\qquad \lim_{n\to\infty}\frac{1}{n^2}=0.$$

Applying the limit laws for sums and quotients:

$$\lim_{n\to\infty}\frac{4-\dfrac{3}{n}+\dfrac{1}{n^2}}{2+\dfrac{5}{n}-\dfrac{7}{n^2}}=\frac{4-3\cdot0+0}{2+5\cdot0-7\cdot0}=\frac{4}{2}=2.$$

## 4. Why the highest-degree terms determine the result

In $4n^2-3n+1$, the ratio of the lower-order terms to the leading term $4n^2$ is

$$\frac{-3n+1}{4n^2}=-\frac{3}{4n}+\frac{1}{4n^2}\xrightarrow[n\to\infty]{}0.$$

Relative to $n^2$, the linear term $-3n$ and the constant $1$ become negligible dust for large $n$. Thus, for large $n$, the numerator behaves like $4n^2$ and the denominator behaves like $2n^2$, so their quotient behaves like $\dfrac{4n^2}{2n^2}=2$.

## Quick verification

Let us split the fraction by polynomial division:

$$4n^2-3n+1 = 2(2n^2+5n-7) - 13n + 15.$$

Dividing by $2n^2+5n-7$ gives:

$$\frac{4n^2-3n+1}{2n^2+5n-7} = 2 - \frac{13n-15}{2n^2+5n-7}.$$

In the remainder fraction, the denominator grows like $n^2$ while the numerator grows only like $n$, so the remainder vanishes as $n\to\infty$, leaving $2-0=2$. ✓

## A concrete example

Let us evaluate the sequence at $n=10$, $n=100$, and $n=1000$:

- For $n=10$: $\dfrac{4(100)-30+1}{2(100)+50-7}=\dfrac{371}{243}\approx 1.5267$.
- For $n=100$: $\dfrac{40000-300+1}{20000+500-7}=\dfrac{39701}{20493}\approx 1.9373$.
- For $n=1000$: $\dfrac{4000000-3000+1}{2000000+5000-7}=\dfrac{3997001}{2004993}\approx 1.9935$.

At $n=1000$, the $n^2$ terms contribute $4\,000\,000$ and $2\,000\,000$, whereas the linear and constant terms only shift the totals by a few thousand—less than $0.35\%$ of the value.

## How I would explain this in class

> Both the top and the bottom are degree-2 polynomials in $n$. When $n$ is huge, $n^2$ completely dwarfs $n$ and the constants. To make that rigorous, I divide every term on top and bottom by $n^2$. All the fractions with $n$ or $n^2$ in the denominator go to $0$, leaving just the ratio of the leading coefficients, $\dfrac{4}{2}=2$.

## Related workbook topics

- [Exercise 2: Different growth rates](problem_02_solution.md)
- [Exercise 6: From a sequence to a function — limit at infinity](problem_06_solution.md)
