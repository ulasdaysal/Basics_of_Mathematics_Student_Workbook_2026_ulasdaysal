# Exercise 2. Powers, Roots, and the Domain

## The question

Compute

$$\int\left(2\sqrt{x}+\frac{3}{x^2}-x^{1/3}\right)\,dx.$$

First rewrite the terms as powers, determine the domain of the original expression, and verify the result by differentiation.

## Before calculating: what idea do we need?

Roots and fractions with $x$ in the denominator do not need separate integration rules—they are simply **powers with fractional or negative exponents**:

$$\sqrt{x}=x^{1/2},\qquad \frac{1}{x^n}=x^{-n}.$$

Once every term is written in the standard power form $x^n$ (with $n\neq -1$), we apply the power rule:

$$\int x^n\,dx=\frac{x^{n+1}}{n+1}+C.$$

Before integrating, however, we must check **where the integrand is defined**, because the antiderivative is only valid on intervals where the original function exists.

## 1. Determining the domain of the integrand

Let $f(x)=2\sqrt{x}+\dfrac{3}{x^2}-x^{1/3}$. We check each term:

- $2\sqrt{x}$ requires $x\ge 0$ (in the real numbers, square roots of negative numbers are undefined).
- $\dfrac{3}{x^2}$ requires $x\neq 0$ (division by zero is undefined).
- $x^{1/3}=\sqrt[3]{x}$ is defined for all $x\in\mathbb{R}$.

Combining $x\ge 0$ and $x\neq 0$, the domain of the integrand is the open half-line:

$$D_f=(0,\infty)\quad\text{(that is, }x>0\text{)}.$$

## 2. Rewriting the integrand as powers of $x$

For $x>0$, we rewrite each term in the form $a\cdot x^n$:

$$2\sqrt{x}=2x^{1/2},\qquad \frac{3}{x^2}=3x^{-2},\qquad -x^{1/3}=-x^{1/3}.$$

So the integral becomes:

$$\int\left(2x^{1/2}+3x^{-2}-x^{1/3}\right)\,dx.$$

## 3. Integrating term by term

We apply $\int x^n\,dx=\dfrac{x^{n+1}}{n+1}$ to each term:

1. **First term ($n=\tfrac{1}{2}$):** the new exponent is $\tfrac{1}{2}+1=\tfrac{3}{2}$, and dividing by $\tfrac{3}{2}$ means multiplying by $\tfrac{2}{3}$:
   $$2\cdot\frac{x^{3/2}}{3/2}=2\cdot\frac{2}{3}x^{3/2}=\frac{4}{3}x^{3/2}.$$
2. **Second term ($n=-2$):** the new exponent is $-2+1=-1$:
   $$3\cdot\frac{x^{-1}}{-1}=-3x^{-1}=-\frac{3}{x}.$$
3. **Third term ($n=\tfrac{1}{3}$):** the new exponent is $\tfrac{1}{3}+1=\tfrac{4}{3}$, and dividing by $\tfrac{4}{3}$ means multiplying by $\tfrac{3}{4}$:
   $$-\frac{x^{4/3}}{4/3}=-\frac{3}{4}x^{4/3}.$$

## 4. Writing the final result

Combining all terms and converting back to radical/fraction notation (for $x>0$):

$$\int\left(2\sqrt{x}+\frac{3}{x^2}-x^{1/3}\right)\,dx=\frac{4}{3}x^{3/2}-\frac{3}{x}-\frac{3}{4}x^{4/3}+C=\frac{4}{3}x\sqrt{x}-\frac{3}{x}-\frac{3}{4}x\sqrt[3]{x}+C.$$

## Quick verification

Differentiate $F(x)=\dfrac{4}{3}x^{3/2}-3x^{-1}-\dfrac{3}{4}x^{4/3}+C$ using the power rule on $(0,\infty)$:

$$F'(x)=\frac{4}{3}\cdot\frac{3}{2}x^{3/2-1}-3(-1)x^{-1-1}-\frac{3}{4}\cdot\frac{4}{3}x^{4/3-1}+0=2x^{1/2}+3x^{-2}-x^{1/3}=2\sqrt{x}+\frac{3}{x^2}-x^{1/3}.$$

Every term matches the original integrand. ✓

## A concrete example

A very common mistake when integrating $\dfrac{3}{x^2}=3x^{-2}$ is to add $1$ in the wrong direction and write $-3$ instead of $-1$ as the new exponent. Checking at $x=1$ shows how our derivative test catches this immediately:
- For our term $-3x^{-1}$, the derivative is $(-3)(-1)x^{-2}=3x^{-2}$, which at $x=1$ equals $3$.
- Evaluating the rate of change of $F(x)$ at $x=1$ gives $F'(1)=2(1)+3(1)-1=4$, matching $f(1)=2\sqrt{1}+\frac{3}{1^2}-1^{1/3}=4$.

## How I would explain this in class

> Whenever I see roots or powers in the denominator, my first step is to rewrite them with fractional and negative exponents: $2x^{1/2}+3x^{-2}-x^{1/3}$. I also note that $\sqrt{x}$ needs $x\ge 0$ and $3/x^2$ forbids $x=0$, so the domain is $x>0$. Then I just add $1$ to each exponent and divide by the new exponent: $x^{1/2}$ goes to $\frac{2}{3}x^{3/2}$, $x^{-2}$ goes to $-x^{-1}$ (careful: $-2+1=-1$, not $-3$!), and $x^{1/3}$ goes to $\frac{3}{4}x^{4/3}$. Differentiating the power form confirms the answer immediately.

## Related workbook topics

- [Exercise 1: Antiderivative and Verification](problem_01_solution.md)
- [Exercise 3: Recognizing Basic Antiderivatives](problem_03_solution.md)
