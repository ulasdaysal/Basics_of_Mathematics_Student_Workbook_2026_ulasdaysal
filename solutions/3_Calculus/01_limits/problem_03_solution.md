# Exercise 3. A Square Root and Removing an Indeterminate Form

## The question

Compute

$$\lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right).$$

Use the conjugate expression and explain why this transformation removes the difficulty.

## Before calculating: what idea do we need?

As $n\to\infty$, both $\sqrt{n^2+5n}$ and $n$ grow to $+\infty$, so their difference has the indeterminate form $\infty-\infty$. We cannot simply drop $5n$ inside the square root and say $\sqrt{n^2+5n}\approx n$, because the leading $n$'s cancel out in subtraction, making the next correction term the star of the show!

To eliminate the square root from the subtraction, we multiply and divide by the **conjugate expression** $\sqrt{n^2+5n}+n$ and apply the difference-of-squares identity $(A-B)(A+B)=A^2-B^2$.

## 1. Multiply and divide by the conjugate

Write the sequence as a fraction with denominator $1$ and multiply top and bottom by $\sqrt{n^2+5n}+n$:

$$\sqrt{n^2+5n}-n = \frac{\left(\sqrt{n^2+5n}-n\right)\left(\sqrt{n^2+5n}+n\right)}{\sqrt{n^2+5n}+n}.$$

## 2. Simplify the numerator using $(A-B)(A+B)=A^2-B^2$

Expanding the numerator clears the square root:

$$\left(\sqrt{n^2+5n}\right)^2 - n^2 = (n^2+5n)-n^2 = 5n.$$

Thus our sequence becomes:

$$\sqrt{n^2+5n}-n = \frac{5n}{\sqrt{n^2+5n}+n}.$$

## 3. Factor out the dominant term $n$ and take the limit

Since $n>0$, we have $\sqrt{n^2}=n$, so we can factor $n$ out of the square root:

$$\sqrt{n^2+5n} = \sqrt{n^2\left(1+\frac{5}{n}\right)} = n\sqrt{1+\frac{5}{n}}.$$

Substituting this into the denominator and canceling $n$ gives:

$$\frac{5n}{n\sqrt{1+\dfrac{5}{n}}+n} = \frac{5}{\sqrt{1+\dfrac{5}{n}}+1}.$$

As $n\to\infty$, $\dfrac{5}{n}\to0$, so $\sqrt{1+5/n}\to\sqrt{1}=1$. Hence:

$$\lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right) = \frac{5}{\sqrt{1+0}+1} = \frac{5}{1+1} = \frac{5}{2}.$$

## 4. Why conjugation removes the difficulty

In the original expression $\sqrt{n^2+5n}-n$, two nearly equal large quantities are subtracted ($\infty-\infty$), so their leading $n$ terms cancel implicitly in a way hidden inside the radical. Multiplying by the conjugate:

1. **In the numerator**, squares the radical so the cancelling $n^2$ terms are exposed explicitly: $(n^2+5n)-n^2=5n$.
2. **In the denominator**, replaces subtraction with addition ($\sqrt{n^2+5n}+n$), where the leading terms *reinforce* each other ($n+n=2n$) instead of canceling.

This converts an unstable $\infty-\infty$ difference into a standard $\dfrac{\infty}{\infty}$ quotient of degree $1$ over degree $1$.

## Quick verification

Complete the square inside the radical:

$$n^2+5n = \left(n+\frac{5}{2}\right)^2 - \frac{25}{4}.$$

For large $n$, the constant $-\dfrac{25}{4}$ is negligible compared to $\left(n+\dfrac{5}{2}\right)^2$, so $\sqrt{n^2+5n}$ is just slightly less than $n+\dfrac{5}{2}$. Subtracting $n$ leaves $\dfrac{5}{2}$. ✓

## A concrete example

Let us check the terms of the sequence for $n=10$ and $n=100$:

- For $n=10$: $\sqrt{100+50}-10 = \sqrt{150}-10 \approx 12.2474 - 10 = 2.2474$.
- For $n=100$: $\sqrt{10000+500}-100 = \sqrt{10500}-100 \approx 102.4695 - 100 = 2.4695$.
- For $n=1000$: $\sqrt{1005000}-1000 \approx 1002.4969 - 1000 = 2.4969$.

The values steadily approach $\dfrac{5}{2}=2.5$ from below.

## How I would explain this in class

> We have $\infty-\infty$, and we can't just ignore the $5n$ because the $n^2$ under the root cancels against the $-n$ outside. By multiplying top and bottom by the conjugate $\sqrt{n^2+5n}+n$, the top becomes $(n^2+5n)-n^2=5n$, and the bottom behaves like $n+n=2n$. Dividing top and bottom by $n$ gives $\dfrac{5}{1+1}=\dfrac{5}{2}$.

## Related workbook topics

- [Exercise 1: Dominant terms in a sequence](problem_01_solution.md)
- [Exercise 8: A square root in a function limit](problem_08_solution.md)
