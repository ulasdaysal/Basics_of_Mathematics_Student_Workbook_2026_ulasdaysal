# Exercise 12. Exponential Function Limit

## The question

Compute

$$\lim_{x\to0}(1+3x)^{1/x}.$$

Connect the result with the limit from Exercise 5 and show the appropriate transformation.

## Before calculating: what idea do we need?

As $x\to0$, the base $1+3x\to 1$ while the exponent $\dfrac{1}{x}\to\pm\infty$, giving the indeterminate form $1^\infty$—the exact same type we saw in Exercise 5!

The continuous version of Euler's limit states that whenever a quantity $u\to0$,

$$\lim_{u\to0}(1+u)^{1/u} = e\qquad \left(\text{equivalently, setting } t=\frac{1}{u},\; \lim_{t\to\pm\infty}\left(1+\frac{1}{t}\right)^t = e\right).$$

To match this pattern, the exponent must be the exact **reciprocal** of the small term added to $1$. Since our base has $+3x$, we need $\dfrac{1}{3x}$ in the exponent.

## 1. Rewrite the exponent to match the inner term $3x$

Inside the parentheses we have $1+3x$. To create the matching exponent $\dfrac{1}{3x}$, we multiply and divide the exponent $\dfrac{1}{x}$ by $3$:

$$\frac{1}{x} = \frac{3}{3x} = \frac{1}{3x}\cdot 3.$$

Using the exponent law $a^{bc}=\left(a^b\right)^c$:

$$(1+3x)^{1/x} = (1+3x)^{\frac{1}{3x}\cdot 3} = \left[(1+3x)^{\frac{1}{3x}}\right]^3.$$

## 2. Substitute and apply the fundamental limit for $e$

Let $u=3x$ (or $t=\dfrac{1}{3x}$). As $x\to0$, we have $u=3x\to0$ (and $t\to\pm\infty$). Therefore, the expression inside the brackets reduces to the classical limit for $e$:

$$\lim_{x\to0}(1+3x)^{\frac{1}{3x}} = \lim_{u\to0}(1+u)^{1/u} = \lim_{t\to\pm\infty}\left(1+\frac{1}{t}\right)^t = e.$$

## 3. Raise to the outer power $3$

Because the cubing function $z\mapsto z^3$ is continuous everywhere, we can pass the limit inside the outer exponent:

$$\lim_{x\to0}(1+3x)^{1/x} = \left(\lim_{x\to0}(1+3x)^{\frac{1}{3x}}\right)^3 = e^3.$$

## 4. Connection with Exercise 5

In Exercise 5, we studied $\lim_{n\to\infty}\left(1+\dfrac{1}{n}\right)^n=e$. If we set $x=\dfrac{1}{3n}$, then as $n\to\infty$ we have $x\to0^+$ and $\dfrac{1}{x}=3n$, turning our expression into:

$$(1+3x)^{1/x} = \left(1+\frac{1}{n}\right)^{3n} = \left[\left(1+\frac{1}{n}\right)^n\right]^3 \xrightarrow[n\to\infty]{} e^3.$$

More generally, for any constant $k\in\mathbb{R}$, $\lim_{x\to0}(1+kx)^{1/x} = e^k$.

## Quick verification

We can also verify the limit using the natural logarithm and exponential $(1+3x)^{1/x} = e^{\frac{\ln(1+3x)}{x}}$:

$$\lim_{x\to0}\frac{\ln(1+3x)}{x} = 3\lim_{x\to0}\frac{\ln(1+3x)}{3x} = 3\cdot 1 = 3.$$

By continuity of the exponential function, $\lim_{x\to0}(1+3x)^{1/x} = e^3$. ✓

## A concrete example

Let us compare $(1+3x)^{1/x}$ for small $x$ around $0$ with $e^3\approx 20.0855$:

- For $x=0.01$: $(1+0.03)^{100} = (1.03)^{100} \approx 19.2186$.
- For $x=0.001$: $(1+0.003)^{1000} = (1.003)^{1000} \approx 19.9955$.
- For $x=-0.001$: $(1-0.003)^{-1000} = (0.997)^{-1000} \approx 20.1763$.

Both from the left and from the right, the values squeeze toward $e^3\approx 20.0855$.

## How I would explain this in class

> As $x\to0$, $(1+3x)^{1/x}$ has the form $1^\infty$, which is the signature of the number $e$. To use the fundamental limit $\lim_{u\to0}(1+u)^{1/u}=e$, the exponent needs to be the reciprocal of $3x$, namely $\dfrac{1}{3x}$. So I rewrite the exponent $\dfrac{1}{x}$ as $\dfrac{1}{3x}\cdot 3$: then $\left[(1+3x)^{1/(3x)}\right]^3$ has an inside that goes to $e$, and the outer power $3$ gives $e^3$.

## Related workbook topics

- [Exercise 5: The classical limit leading to the number e](problem_05_solution.md)
- [Exercise 13: Fundamental trigonometric limit](problem_13_solution.md)
