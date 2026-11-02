# Exercise 4. Powers and Oscillation

## The question

Analyze

$$\left(\frac23\right)^n,\qquad \left(\frac32\right)^n,\qquad (-1)^n,\qquad \frac{(-1)^n}{n}.$$

For each sequence, describe the type of behavior and justify your answer.

## Before calculating: what idea do we need?

A geometric sequence $q^n$ behaves in fundamentally different ways depending on the base $q$:

- If $|q|<1$, multiplying by $q$ repeatedly shrinks the magnitude toward $0$.
- If $q>1$, multiplying by $q$ repeatedly amplifies the value toward $+\infty$.
- If $q=-1$, the sign alternates forever without the magnitude shrinking, causing **undamped oscillation**.
- If an alternating factor $(-1)^n$ is divided by $n$, the sign still flips, but the amplitude $\dfrac{1}{n}$ shrinks to $0$, producing **damped oscillation** that converges to $0$.

## 1. First sequence: $a_n = \left(\dfrac{2}{3}\right)^n$

Here the base satisfies $0 < \dfrac{2}{3} < 1$. Each term is two-thirds of the previous term ($a_{n+1}=\dfrac{2}{3}a_n < a_n$), so the sequence is **strictly decreasing and positive**, converging to zero:

$$\lim_{n\to\infty}\left(\frac{2}{3}\right)^n = 0.$$

## 2. Second sequence: $b_n = \left(\dfrac{3}{2}\right)^n$

Here the base is $q = \dfrac{3}{2} = 1 + \frac{1}{2} > 1$. By Bernoulli's inequality,

$$\left(1+\frac{1}{2}\right)^n \ge 1 + \frac{n}{2} \xrightarrow[n\to\infty]{} +\infty.$$

Thus the sequence is **strictly increasing and diverges to $+\infty$**:

$$\lim_{n\to\infty}\left(\frac{3}{2}\right)^n = +\infty.$$

## 3. Third sequence: $c_n = (-1)^n$

For even indices $n=2k$, $c_{2k}=(-1)^{2k}=1$. For odd indices $n=2k-1$, $c_{2k-1}=(-1)^{2k-1}=-1$. Because the even-indexed subsequence converges to $1$ and the odd-indexed subsequence converges to $-1\neq 1$, the sequence **oscillates between $-1$ and $1$ and diverges** (has no limit).

## 4. Fourth sequence: $d_n = \dfrac{(-1)^n}{n}$

Here the sign alternates, so the sequence is neither increasing nor decreasing. However, its absolute value satisfies

$$-\frac{1}{n} \le \frac{(-1)^n}{n} \le \frac{1}{n}.$$

Since $\lim_{n\to\infty}\left(-\dfrac{1}{n}\right)=0$ and $\lim_{n\to\infty}\dfrac{1}{n}=0$, the **Squeeze Theorem** implies:

$$\lim_{n\to\infty}\frac{(-1)^n}{n} = 0.$$

This is **damped oscillation**: the sequence jumps back and forth across $0$, but the jumps shrink to zero.

## Quick verification

Let us compare the subsequences of even and odd indices for $c_n=(-1)^n$ and $d_n=\dfrac{(-1)^n}{n}$:

- For $c_n$: $c_{2k}=1\to 1$ and $c_{2k-1}=-1\to -1$. Different limits $\implies$ no limit exists. ✓
- For $d_n$: $d_{2k}=\dfrac{1}{2k}\to 0$ and $d_{2k-1}=-\dfrac{1}{2k-1}\to 0$. Both subsequences converge to the same number $0$ $\implies$ $\lim_{n\to\infty} d_n=0$. ✓

## A concrete example

Write out the first five terms ($n=1,2,3,4,5$) of each sequence:

- $\left(\dfrac{2}{3}\right)^n$: $\dfrac{2}{3}\approx 0.67,\; \dfrac{4}{9}\approx 0.44,\; \dfrac{8}{27}\approx 0.30,\; \dfrac{16}{81}\approx 0.20,\; \dfrac{32}{243}\approx 0.13 \to 0$.
- $\left(\dfrac{3}{2}\right)^n$: $1.5,\; 2.25,\; 3.375,\; 5.0625,\; 7.59375 \to +\infty$.
- $(-1)^n$: $-1,\; 1,\; -1,\; 1,\; -1$ (never settles down).
- $\dfrac{(-1)^n}{n}$: $-1,\; 0.5,\; -0.333\dots,\; 0.25,\; -0.2 \to 0$.

## How I would explain this in class

> Powers $(2/3)^n$ shrink to $0$ because the base is between $-1$ and $1$, while $(3/2)^n$ blows up to $+\infty$ because the base is greater than $1$. The sequence $(-1)^n$ bounces between $-1$ and $1$ forever, so it has no limit. But $\dfrac{(-1)^n}{n}$ is a great lesson: even though it oscillates in sign, its distance from $0$ is $\dfrac{1}{n}$, which shrinks to $0$, so the sequence still converges to $0$.

## Related workbook topics

- [Exercise 2: Different growth rates](problem_02_solution.md)
- [Exercise 11: An n-th root](problem_11_solution.md)
