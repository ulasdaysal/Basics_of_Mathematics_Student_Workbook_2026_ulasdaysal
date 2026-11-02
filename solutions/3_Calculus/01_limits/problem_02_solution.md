# Exercise 2. Different Growth Rates

## The question

Compute

$$\lim_{n\to\infty}\frac{3n+1}{n^2+4},\qquad \lim_{n\to\infty}\frac{2n^3-n}{5n^2+1}.$$

Compare the two cases and formulate a general observation about the degrees of the polynomials in the numerator and denominator.

## Before calculating: what idea do we need?

When we take the limit as $n\to\infty$ of a rational expression $\dfrac{P(n)}{Q(n)}$, the result is a tug-of-war between the growth rate of the numerator $P(n)$ and the growth rate of the denominator $Q(n)$.

To compare them cleanly, we factor out the highest power of $n$ from the numerator and the highest power of $n$ from the denominator (or divide top and bottom by the highest power in the denominator) and see whether a power of $n$ remains in the numerator or in the denominator.

## 1. First limit: denominator has higher degree

In $\dfrac{3n+1}{n^2+4}$, the highest power of $n$ in the denominator is $n^2$. Dividing every term in the numerator and denominator by $n^2$ gives:

$$\frac{3n+1}{n^2+4}=\frac{\dfrac{3}{n}+\dfrac{1}{n^2}}{1+\dfrac{4}{n^2}}.$$

As $n\to\infty$, $\dfrac{3}{n}\to0$, $\dfrac{1}{n^2}\to0$, and $\dfrac{4}{n^2}\to0$. Therefore:

$$\lim_{n\to\infty}\frac{3n+1}{n^2+4}=\frac{0+0}{1+0}=0.$$

## 2. Second limit: numerator has higher degree

In $\dfrac{2n^3-n}{5n^2+1}$, the denominator has degree $2$ while the numerator has degree $3$. Dividing numerator and denominator by $n^2$ (the highest power in the denominator) gives:

$$\frac{2n^3-n}{5n^2+1}=\frac{2n-\dfrac{1}{n}}{5+\dfrac{1}{n^2}}=n\cdot\frac{2-\dfrac{1}{n^2}}{5+\dfrac{1}{n^2}}.$$

As $n\to\infty$, the fraction $\dfrac{2-1/n^2}{5+1/n^2}$ approaches $\dfrac{2}{5}>0$, while the factor $n$ grows to $+\infty$. Therefore:

$$\lim_{n\to\infty}\frac{2n^3-n}{5n^2+1}=+\infty.$$

## 3. Comparison of the two cases

- In the **first sequence**, the numerator grows linearly ($\sim 3n$) while the denominator grows quadratically ($\sim n^2$). After canceling one factor of $n$, we still have $\sim \dfrac{3}{n}$, so the denominator overwhelms the numerator and drives the quotient to $0$.
- In the **second sequence**, the numerator grows cubically ($\sim 2n^3$) while the denominator grows quadratically ($\sim 5n^2$). After canceling $n^2$, an uncompensated factor of $\sim \dfrac{2}{5}n$ remains in the numerator, which grows without bound.

## 4. General rule for degrees of polynomials

For two polynomials $P(n)=a_p n^p+\dots+a_0$ ($a_p\neq0$) and $Q(n)=b_q n^q+\dots+b_0$ ($b_q\neq0$) as $n\to\infty$:

1. **$\deg P < \deg Q$ ($p<q$):** the denominator grows faster, so $\lim_{n\to\infty}\dfrac{P(n)}{Q(n)}=0$.
2. **$\deg P = \deg Q$ ($p=q$):** both grow at the same rate, so $\lim_{n\to\infty}\dfrac{P(n)}{Q(n)}=\dfrac{a_p}{b_q}$ (as in Exercise 1).
3. **$\deg P > \deg Q$ ($p>q$):** the numerator grows faster, so $\lim_{n\to\infty}\dfrac{P(n)}{Q(n)}=+\infty$ (if $\dfrac{a_p}{b_q}>0$) or $-\infty$ (if $\dfrac{a_p}{b_q}<0$).

## Quick verification

We can bound both sequences for $n\ge1$:

- First sequence: $0 < \dfrac{3n+1}{n^2+4} \le \dfrac{3n+n}{n^2} = \dfrac{4}{n} \xrightarrow[n\to\infty]{} 0$. By the squeeze theorem, the limit is $0$. ✓
- Second sequence: for $n\ge1$, $2n^3-n \ge n^3$ and $5n^2+1 \le 6n^2$, so $\dfrac{2n^3-n}{5n^2+1} \ge \dfrac{n^3}{6n^2} = \dfrac{n}{6} \xrightarrow[n\to\infty]{} +\infty$. ✓

## A concrete example

At $n=100$:

- First sequence: $\dfrac{3(100)+1}{100^2+4}=\dfrac{301}{10004}\approx 0.0301$ (very close to $\dfrac{3}{100}=0.03$, heading to $0$).
- Second sequence: $\dfrac{2(100^3)-100}{5(100^2)+1}=\dfrac{1\,999\,900}{50\,001}\approx 39.997$ (very close to $\dfrac{2}{5}\cdot 100=40$, heading to $+\infty$).

## How I would explain this in class

> When you divide two polynomials at infinity, you just compare their degrees. In the first limit, degree $1$ divided by degree $2$ behaves like $\dfrac{3n}{n^2}=\dfrac{3}{n}$, which shrinks to $0$. In the second limit, degree $3$ divided by degree $2$ behaves like $\dfrac{2n^3}{5n^2}=\dfrac{2}{5}n$, which blows up to $+\infty$.

## Related workbook topics

- [Exercise 1: Dominant terms in a sequence](problem_01_solution.md)
- [Exercise 6: From a sequence to a function — limit at infinity](problem_06_solution.md)
