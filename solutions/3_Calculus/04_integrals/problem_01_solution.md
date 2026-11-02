# Exercise 1. Antiderivative and Verification

## The question

For

$$f(x)=3x^2-4x+5$$

find one antiderivative $F(x)$. Write the entire family of antiderivatives, verify the result by differentiation, and explain the meaning of the constant $C$.

## Before calculating: what idea do we need?

Integration is the **inverse operation to differentiation**. Looking for an antiderivative $F(x)$ of $f(x)$ means asking: *"Which function has derivative $f(x)$?"*

For power terms $x^n$ (with $n\neq -1$), differentiating brings the exponent down and reduces it by $1$:

$$\frac{d}{dx}\left(x^{n+1}\right)=(n+1)x^n.$$

Reversing this process gives the **power rule for antiderivatives**: raise the exponent by $1$ and divide by the new exponent:

$$\int x^n\,dx=\frac{x^{n+1}}{n+1}+C.$$

Because the derivative of any constant $C$ is zero, adding a constant does not change the derivative. Therefore, a function does not have just one antiderivative, but an entire vertical family of them.

## 1. Finding one antiderivative $F(x)$

We integrate $f(x)=3x^2-4x+5$ term by term by reversing the power rule:

- For $3x^2$: raise the power from $2$ to $3$ and divide by $3$:
  $$3\cdot\frac{x^3}{3}=x^3.$$
- For $-4x$: raise the power from $1$ to $2$ and divide by $2$:
  $$-4\cdot\frac{x^2}{2}=-2x^2.$$
- For $5$: a constant $5=5x^0$ comes from differentiating a linear term:
  $$5x.$$

Choosing the simplest case (with constant $0$), one particular antiderivative is:

$$F_0(x)=x^3-2x^2+5x.$$

## 2. Writing the entire family of antiderivatives

Since any two antiderivatives of the same function on an interval differ only by a constant, the complete family of antiderivatives (the indefinite integral) is:

$$\int (3x^2-4x+5)\,dx = x^3-2x^2+5x+C,\qquad C\in\mathbb{R}.$$

## 3. Meaning of the constant $C$

- **Analytically:** Differentiation measures the rate of change, so any constant term $C$ disappears when we differentiate ($\frac{d}{dx}(C)=0$). When we reverse differentiation, we cannot know which constant was originally present without extra information (such as an initial condition).
- **Geometrically:** Changing $C$ shifts the graph of $F_0(x)=x^3-2x^2+5x$ **vertically up or down**. At every given $x$, all curves in the family $F(x)=x^3-2x^2+5x+C$ have the exact same slope $f(x)=3x^2-4x+5$.

## Quick verification

We differentiate the entire family $F(x)=x^3-2x^2+5x+C$ with respect to $x$:

$$F'(x)=\frac{d}{dx}\left(x^3-2x^2+5x+C\right)=3x^2-2(2x)+5+0=3x^2-4x+5=f(x).$$

The derivative matches the original integrand for every real value of $C$. ✓

## A concrete example

Consider two specific members of the family:

$$F_1(x)=x^3-2x^2+5x+1\qquad\text{and}\qquad F_2(x)=x^3-2x^2+5x-4.$$

At $x=2$:
- Their values are different: $F_1(2)=8-8+10+1=11$, whereas $F_2(2)=8-8+10-4=6$ (shifted vertically by $5$ units).
- Their slopes at $x=2$ are identical:
  $$F_1'(2)=F_2'(2)=f(2)=3(2)^2-4(2)+5=12-8+5=9.$$

If we additionally require the curve to pass through $(2,11)$, only $C=1$ works.

## How I would explain this in class

> To find an antiderivative of $3x^2-4x+5$, I reverse the power rule term by term: $3x^2$ comes from $x^3$, $-4x$ comes from $-2x^2$, and $5$ comes from $5x$. That gives one antiderivative $x^3-2x^2+5x$. Because the derivative of any constant is zero, adding $+C$ gives the whole family $x^3-2x^2+5x+C$. Geometrically, $+C$ shifts the graph up or down without changing its slope at any $x$. Differentiating brings us right back to $3x^2-4x+5$.

## Related workbook topics

- [Exercise 2: Powers, Roots, and the Domain](problem_02_solution.md)
- [Exercise 15: Recovering a Function from Its Derivative and a Condition](problem_15_solution.md)
