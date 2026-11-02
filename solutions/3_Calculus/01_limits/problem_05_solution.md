# Exercise 5. The Classical Limit Leading to the Number $e$

## The question

Compute

$$\lim_{n\to\infty}\left(1+\frac1n\right)^n.$$

Calculate several values for increasing $n$ and compare the observed behavior with the value of the limit. Explain why a few values do not constitute a proof.

## Before calculating: what idea do we need?

In the expression $a_n = \left(1+\dfrac{1}{n}\right)^n$, two competing forces act as $n\to\infty$:

- **Inside the parentheses**, $\dfrac{1}{n}\to 0$, so the base $1+\dfrac{1}{n}$ approaches $1$ (which tries to pull the result toward $1$).
- **In the exponent**, $n\to\infty$, so we multiply numbers slightly larger than $1$ an ever-growing number of times (which tries to push the result up).

This creates the indeterminate form $1^\infty$. The balance between the shrinking increment $\dfrac{1}{n}$ and the growing exponent $n$ defines Euler's number $e$.

## 1. Value of the fundamental limit

By a fundamental theorem of analysis (proved by showing that the sequence $a_n=\left(1+\dfrac{1}{n}\right)^n$ is strictly increasing and bounded above, for instance by $3$), this sequence converges to Euler's constant $e$:

$$\lim_{n\to\infty}\left(1+\frac{1}{n}\right)^n = e \approx 2.718281828\dots$$

## 2. Calculating values for increasing $n$

Let us compute $a_n = \left(1+\dfrac{1}{n}\right)^n$ for several values of $n$:

| $n$ | Formula | Value (to 5 decimal places) |
|---|---|---|
| $1$ | $(1+1)^1$ | $2.00000$ |
| $2$ | $(1+0.5)^2 = (1.5)^2$ | $2.25000$ |
| $5$ | $(1+0.2)^5 = (1.2)^5$ | $2.48832$ |
| $10$ | $(1.1)^{10}$ | $2.59374$ |
| $100$ | $(1.01)^{100}$ | $2.70481$ |
| $1000$ | $(1.001)^{1000}$ | $2.71692$ |
| $10000$ | $(1.0001)^{10000}$ | $2.71815$ |

## 3. Comparing observed values with the limit

Looking at the table, we observe two key properties:

1. As $n$ grows, $a_n$ **increases** at every step ($2 < 2.25 < 2.48832 < \dots$).
2. The growth slows down dramatically: jumping from $n=1$ to $n=10$ adds about $0.59$, whereas jumping from $n=1000$ to $n=10000$ adds only about $0.0012$, creeping closer and closer to $e\approx 2.71828$ from below.

## 4. Why a few values do not constitute a proof

Computing a finite table of values—even for $n=10^6$ or $n=10^{12}$—cannot prove that the limit is $e$, for three reasons:

1. **Unseen future behavior:** A sequence can grow very slowly and still diverge to $+\infty$ (for example, the harmonic sum $1+\frac12+\dots+\frac1n$ or $\ln(\ln n)$), or it could change behavior after $n=10^{100}$.
2. **Rounding vs. exactness:** Numerical evaluations have finite decimal precision and cannot distinguish between $e$ and a nearby number like $2.7182818$.
3. **What a proof actually requires:** To prove convergence rigorously, we must demonstrate for *all* $n\in\mathbb{N}$ that $a_n < a_{n+1}$ (monotonicity) and $a_n < 3$ (boundedness), using the binomial theorem.

## Quick verification

Using the Binomial Theorem for $a_n = \left(1+\dfrac{1}{n}\right)^n$:

$$a_n = 1 + \binom{n}{1}\frac{1}{n} + \binom{n}{2}\frac{1}{n^2} + \binom{n}{3}\frac{1}{n^3} + \dots = 1 + 1 + \frac{1}{2!}\left(1-\frac{1}{n}\right) + \frac{1}{3!}\left(1-\frac{1}{n}\right)\left(1-\frac{2}{n}\right) + \dots$$

As $n\to\infty$, each factor $\left(1-\dfrac{k}{n}\right)\to 1$ and increased $n$ adds more positive terms, converging to $1+1+\dfrac{1}{2!}+\dfrac{1}{3!}+\dots = e \approx 2.71828$ (already the first six terms sum to $1+1+0.5+0.1667+0.0417+0.0083 = 2.7167$). ✓

## A concrete example

In compound interest, if $\$1$ is invested at $100\%$ annual interest compounded $n$ times per year:

- Annually ($n=1$): you end the year with $\left(1+1\right)^1 = \$2.00$.
- Monthly ($n=12$): you end the year with $\left(1+\frac{1}{12}\right)^{12} \approx \$2.61$.
- Daily ($n=365$): you end the year with $\left(1+\frac{1}{365}\right)^{365} \approx \$2.7146$.
- Continuously ($n\to\infty$): you end the year with $\$e \approx \$2.7183$.

## How I would explain this in class

> You might be tempted to say $1+\frac{1}{n}\to 1$ and $1^n=1$, so the limit is $1$. That's a classic trap because the base isn't equal to $1$—it only approaches $1$ while the exponent goes to $\infty$. Plugging in $n=1, 10, 100, 1000$ shows the terms climbing past $2$, $2.59$, $2.70$, $2.716$ toward $e\approx 2.71828$. Still, a table only builds intuition; a real proof needs monotonicity and an upper bound for all $n$.

## Related workbook topics

- [Exercise 12: Exponential function limit](problem_12_solution.md)
- [Exercise 15: Observation versus proof](problem_15_solution.md)
