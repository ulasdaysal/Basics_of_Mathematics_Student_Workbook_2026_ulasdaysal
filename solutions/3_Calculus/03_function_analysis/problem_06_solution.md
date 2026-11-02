# Exercise 6. A Logarithmic Function

## The question

Analyze the domain, zero, and monotonicity of

$$f(x)=\ln x-x+1.$$

Explain why the analysis must begin with the domain.

## Before calculating: what idea do we need?

Derivative formulas are purely algebraic, so they often look valid on a wider set of inputs than the original function! For instance, the derivative of $\ln x$ is $\frac{1}{x}$, which makes sense for negative $x$ even though $\ln x$ does not exist for $x \le 0$. Starting with the domain keeps us from inventing phantom intervals or false critical points where the function itself is undefined.

## 1. Why we must begin with the domain

The natural logarithm $\ln x$ is defined only for strictly positive real numbers, whereas $-x + 1$ is defined on all of $\mathbb{R}$. Therefore, the domain of $f$ is

$$D = (0, \infty).$$

If we differentiated first without recording $D = (0, \infty)$, we would write $f'(x) = \frac{1}{x} - 1 = \frac{1-x}{x}$ and might mistakenly include the interval $(-\infty, 0)$ in our sign chart — an interval where $f(x)$ does not even exist.

## 2. Derivative and monotonicity

For $x \in (0, \infty)$, differentiate term by term:

$$f'(x) = \frac{1}{x} - 1 = \frac{1 - x}{x}.$$

Since $x > 0$ on the entire domain, the denominator is always positive, and the sign of $f'(x)$ is simply the sign of the numerator $1 - x$:

| Interval / Point | $(0, 1)$ | $x = 1$ | $(1, \infty)$ |
| :--- | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+$ | $0$ | $-$ |
| Behavior of $f(x)$ | $\nearrow$ increasing | **Global max** ($0$) | $\searrow$ decreasing |

- **Strictly increasing** on $(0, 1]$.
- **Strictly decreasing** on $[1, \infty)$.
- **Global maximum** at $x = 1$ with value $f(1) = \ln 1 - 1 + 1 = 0$.

## 3. Finding the zero of $f$

Notice what the global maximum tells us:

$$\max_{x \in (0, \infty)} f(x) = f(1) = 0.$$

Because $f$ strictly increases up to $f(1) = 0$ on $(0, 1]$ and strictly decreases away from $f(1) = 0$ on $[1, \infty)$, we have $f(x) < 0$ for every $x \neq 1$. Consequently, **$x = 1$ is the unique zero of $f(x)$** (the graph touches the $x$-axis at $(1, 0)$ from below and turns back down).

## 4. Boundary behavior and global picture

- As $x \to 0^+$, $\ln x \to -\infty$ and $-x + 1 \to 1$, so $\lim_{x\to 0^+} f(x) = -\infty$ (vertical asymptote $x = 0$).
- As $x \to \infty$, linear growth beats logarithmic growth, so $\lim_{x\to\infty} (\ln x - x + 1) = -\infty$.
- This proves the classical inequality $\ln x \le x - 1$ for all $x > 0$, with equality only at $x = 1$.

## Quick verification

- Check $f''(x) = -\frac{1}{x^2} < 0$ for all $x > 0$: the function is strictly concave on $(0, \infty)$, so its tangent line at $x = 1$ (which is $y = 0$) lies above the graph everywhere else. ✓
- Test points on either side of $x = 1$:
  $$f(e^{-1}) = -1 - e^{-1} + 1 = -e^{-1} \approx -0.368 < 0, \qquad f(e) = 1 - e + 1 = 2 - e \approx -0.718 < 0. \quad \checkmark$$

## A concrete example

At $x = 2$, $\ln 2 \approx 0.693$, so

$$f(2) = \ln 2 - 2 + 1 = \ln 2 - 1 \approx -0.307 < 0.$$

And if a student forgot the domain and plugged $x = -1$ into the derivative $f'(-1) = \frac{1}{ -1 } - 1 = -2$, they might claim "$f$ is decreasing at $x = -1$," even though $f(-1) = \ln(-1) + 2$ is undefined in $\mathbb{R}$.

## How I would explain this in class

> Always write down the domain $x > 0$ first, because $\ln x$ doesn't exist for $x \le 0$ even though its derivative formula $\frac{1}{x}$ does. For $x > 0$, $f'(x) = \frac{1-x}{x}$ has the same sign as $1-x$, so $f$ rises on $(0, 1]$ to a global maximum of $f(1) = 0$ and falls on $[1, \infty)$. Since the highest point on the entire graph is $y = 0$ at $x = 1$, $x = 1$ is the only zero of the function.

## Related workbook topics

- [Exercise 5: An Exponential Function with a Maximum](problem_05_solution.md)
- [Exercise 13: A Logarithm and an Asymptote](problem_13_solution.md)
