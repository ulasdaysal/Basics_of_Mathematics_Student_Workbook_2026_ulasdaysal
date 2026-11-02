# Exercise 11. An n-th Root

## The question

Compute

$$\lim_{n\to\infty}\sqrt[n]{5^n+2^n}.$$

Explain which term dominates and why the transformation looks different from the case of a quotient of polynomials.

## Before calculating: what idea do we need?

Inside the $n$-th root we have the sum of two exponential terms, $5^n$ and $2^n$. Which one dominates? Because the base $5$ is larger than the base $2$, $5^n$ grows vastly faster than $2^n$.

Just as we factored out the highest power of $n$ in Exercise 1, here we factor out the **exponential with the largest base**, $5^n$, from under the $n$-th root—or equivalently bound the expression from below and above using the Squeeze Theorem.

## 1. Factor out the dominant term $5^n$

Factor $5^n$ out of the sum inside the radical:

$$5^n+2^n = 5^n\left(1+\frac{2^n}{5^n}\right) = 5^n\left(1+\left(\frac{2}{5}\right)^n\right).$$

Taking the $n$-th root and using $\sqrt[n]{5^n}=5$:

$$\sqrt[n]{5^n+2^n} = \sqrt[n]{5^n\left(1+\left(\frac{2}{5}\right)^n\right)} = 5\,\sqrt[n]{1+\left(\frac{2}{5}\right)^n}.$$

## 2. Evaluate the limit

As $n\to\infty$, since $0<\dfrac{2}{5}<1$, we know from Exercise 4 that $\left(\dfrac{2}{5}\right)^n\to0$. Moreover, for every $n\ge1$:

$$1 < 1+\left(\frac{2}{5}\right)^n < 2 \implies 1 < \sqrt[n]{1+\left(\frac{2}{5}\right)^n} < \sqrt[n]{2}.$$

Since $\lim_{n\to\infty}\sqrt[n]{2}=1$, the Squeeze Theorem gives $\lim_{n\to\infty}\sqrt[n]{1+(2/5)^n}=1$, and therefore:

$$\lim_{n\to\infty}\sqrt[n]{5^n+2^n} = 5\cdot 1 = 5.$$

## 3. Which term dominates?

The term **$5^n$ dominates** because for exponential sequences $a^n$, the growth rate is governed by the **base $a$**. Their ratio is

$$\frac{2^n}{5^n} = \left(\frac{2}{5}\right)^n = 0.4^n \xrightarrow[n\to\infty]{} 0,$$

which decays to zero exponentially fast.

## 4. Why the transformation differs from a quotient of polynomials

- **In a quotient of polynomials** (like $\dfrac{4n^2-3n+1}{2n^2+5n-7}$), the exponent is fixed ($2$, $1$, $0$) and the base $n$ grows. We factor out the highest power $n^2$ and **cancel** $n^2$ between numerator and denominator.
- **In an $n$-th root of exponentials** ($\sqrt[n]{5^n+2^n}$), the bases ($5$ and $2$) are fixed while the exponent $n$ grows, and there is no denominator to cancel against. Instead, we factor out the largest-base exponential $5^n$, and the **outer $n$-th root $\sqrt[n]{\,\cdot\,}$ undoes the $n$-th power**, turning $\sqrt[n]{5^n}$ into the constant $5$.

## Quick verification

We can apply the **Squeeze Theorem** directly to $5^n+2^n$:

$$5^n < 5^n+2^n < 5^n+5^n = 2\cdot 5^n.$$

Taking the $n$-th root across the inequality gives:

$$5 = \sqrt[n]{5^n} < \sqrt[n]{5^n+2^n} < \sqrt[n]{2\cdot 5^n} = 5\sqrt[n]{2}.$$

Since $\lim_{n\to\infty}\sqrt[n]{2}=2^{1/n}=2^0=1$, both outer bounds converge to $5$, forcing $\lim_{n\to\infty}\sqrt[n]{5^n+2^n}=5$. ✓

## A concrete example

Notice how fast $\sqrt[n]{5^n+2^n}$ approaches $5$ even for small $n$:

- $n=1$: $\sqrt[1]{5^1+2^1} = 7$.
- $n=2$: $\sqrt{25+4} = \sqrt{29} \approx 5.3852$.
- $n=5$: $\sqrt[5]{3125+32} = \sqrt[5]{3157} \approx 5.0102$.
- $n=10$: $\sqrt[10]{9\,765\,625 + 1024} = \sqrt[10]{9\,766\,649} \approx 5.000052$.

Already at $n=10$, $2^{10}=1024$ is ten thousand times smaller than $5^{10}=9\,765\,625$!

## How I would explain this in class

> Between $5^n$ and $2^n$, $5^n$ completely dominates because its base is larger. Instead of canceling a power of $n$ between top and bottom like we do for polynomials, we factor $5^n$ out from under the $n$-th root: $\sqrt[n]{5^n(1+(2/5)^n)} = 5\sqrt[n]{1+(2/5)^n}$. Or even faster: sandwich $5^n+2^n$ between $5^n$ and $2\cdot 5^n$, take the $n$-th root to get $5 < \sqrt[n]{5^n+2^n} < 5\sqrt[n]{2}$, and since $\sqrt[n]{2}\to 1$, the limit is $5$.

## Related workbook topics

- [Exercise 1: Dominant terms in a sequence](problem_01_solution.md)
- [Exercise 4: Powers and oscillation](problem_04_solution.md)
