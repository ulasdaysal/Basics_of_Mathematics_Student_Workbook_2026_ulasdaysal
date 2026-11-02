# Exercise 2. Powers, Roots, and the Domain

## The question

For

$$f(x)=2\sqrt{x}-\frac{3}{x^2}+x^{3/2}$$

1. rewrite the function using powers,
2. determine the domain,
3. compute the derivative,
4. compare the domain of the function with the domain of its derivative.

## Before calculating: what idea do we need?

The general power rule

$$\frac{d}{dx}\left(x^p\right)=px^{p-1}$$

works not only for positive integers $p$, but for **any real exponent** $p\in\mathbb{R}$ (on the domain where $x^p$ is differentiable). Radicals and fractions with $x^n$ in the denominator look like separate rules until we rewrite them using fractional and negative exponents:

$$\sqrt{x}=x^{1/2},\qquad \frac{1}{x^n}=x^{-n},\qquad x^{m/n}=\sqrt[n]{x^m}.$$

Before differentiating, we must always check the **domain** — a derivative can only exist at interior points of the function's domain where the resulting formula is also defined.

## 1. Rewrite the function using powers

Convert each radical and reciprocal into power form $x^p$:

- $2\sqrt{x} = 2x^{1/2}$,
- $-\dfrac{3}{x^2} = -3x^{-2}$,
- $x^{3/2}$ is already in power form.

Thus,

$$f(x)=2x^{1/2}-3x^{-2}+x^{3/2}.$$

## 2. Determine the domain of $f$

Look at the restrictions imposed by each term:

- $\sqrt{x}=x^{1/2}$ and $x^{3/2}=(\sqrt{x})^3$ require $x\ge0$ (for real values),
- $\dfrac{3}{x^2}$ requires $x\neq0$ so that we do not divide by zero.

Combining $x\ge0$ and $x\neq0$ gives the domain of $f$:

$$D_f=(0,\infty).$$

## 3. Compute the derivative

Apply the power rule $\dfrac{d}{dx}(x^p)=px^{p-1}$ term by term for $x>0$:

- $\dfrac{d}{dx}\left(2x^{1/2}\right) = 2\cdot\frac{1}{2}x^{1/2-1} = x^{-1/2} = \frac{1}{\sqrt{x}}$,
- $\dfrac{d}{dx}\left(-3x^{-2}\right) = -3\cdot(-2)x^{-2-1} = 6x^{-3} = \frac{6}{x^3}$,
- $\dfrac{d}{dx}\left(x^{3/2}\right) = \frac{3}{2}x^{3/2-1} = \frac{3}{2}x^{1/2} = \frac{3}{2}\sqrt{x}$.

Combining the three terms:

$$f'(x)=x^{-1/2}+6x^{-3}+\frac{3}{2}x^{1/2}=\frac{1}{\sqrt{x}}+\frac{6}{x^3}+\frac{3}{2}\sqrt{x}.$$

## 4. Compare the domains of $f$ and $f'$

In $f'(x)=\dfrac{1}{\sqrt{x}}+\dfrac{6}{x^3}+\dfrac{3}{2}\sqrt{x}$:

- $\sqrt{x}$ requires $x\ge0$,
- $\dfrac{1}{\sqrt{x}}$ and $\dfrac{6}{x^3}$ require $x\neq0$.

Therefore, the domain of the derivative is also

$$D_{f'}=(0,\infty)=D_f.$$

Note that if the term $-\dfrac{3}{x^2}$ had not been present, $2\sqrt{x}+x^{3/2}$ would have had domain $[0,\infty)$, while its derivative $\dfrac{1}{\sqrt{x}}+\dfrac{3}{2}\sqrt{x}$ would have lost the endpoint $x=0$ because $\sqrt{x}$ has a vertical tangent at $x=0^+$. Here, $x=0$ was already excluded from $D_f$ by the $-\dfrac{3}{x^2}$ term, so the two domains match: $D_{f'}=D_f=(0,\infty)$.

## Quick verification

Let us evaluate both formulas at $x=1$ and check with a small increment:

- Using our formula: $f'(1) = 1 + 6 + \dfrac{3}{2} = 8.5$.
- At $x=1$, $f(1) = 2(1) - 3(1) + 1 = 0$.
- At $x=1.0001$, $f(1.0001) = 2\sqrt{1.0001} - \dfrac{3}{(1.0001)^2} + (1.0001)^{3/2} \approx 0.000849911$.
- Difference quotient: $\dfrac{f(1.0001)-f(1)}{0.0001} \approx 8.499 \approx 8.5 = f'(1)$. ✓

## A concrete example

At $x=4\in(0,\infty)$:

$$f(4)=2\sqrt{4}-\frac{3}{4^2}+4^{3/2}=4-\frac{3}{16}+8=11.8125,$$

and the rate of change at $x=4$ is

$$f'(4)=\frac{1}{\sqrt{4}}+\frac{6}{4^3}+\frac{3}{2}\sqrt{4}=\frac{1}{2}+\frac{6}{64}+3=3.59375.$$

Every term of $f'(x)$ is positive for $x>0$, so $f(x)$ is strictly increasing on all of $(0,\infty)$.

## How I would explain this in class

> Instead of using the quotient rule on $\frac{3}{x^2}$ or memorizing separate root rules, rewrite everything as powers: $f(x)=2x^{1/2}-3x^{-2}+x^{3/2}$. Since square roots need $x\ge0$ and dividing by $x^2$ forbids $x=0$, the domain is $(0,\infty)$. Then the power rule gives $f'(x)=x^{-1/2}+6x^{-3}+\frac{3}{2}x^{1/2}=\frac{1}{\sqrt{x}}+\frac{6}{x^3}+\frac{3}{2}\sqrt{x}$, which has the exact same domain $(0,\infty)$.

## Related workbook topics

- [Exercise 1: Derivative of a Polynomial and the Slope of a Tangent Line](problem_01_solution.md)
- [Exercise 4: A Quotient and Domain Control](problem_04_solution.md)
