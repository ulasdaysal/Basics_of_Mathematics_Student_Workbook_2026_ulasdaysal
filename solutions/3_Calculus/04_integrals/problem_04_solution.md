# Exercise 4. Substitution as Reversing the Chain Rule

## The question

Compute

$$\int 2x(x^2+1)^4\,dx.$$

Before calculating, identify a candidate for the new variable $u$ and show that its derivative appears in the integral. Finally, verify the result by differentiation.

## Before calculating: what idea do we need?

When we differentiate a composite function $G(g(x))$, the **chain rule** multiplies the outer derivative by the inner derivative:

$$\frac{d}{dx}\Bigl[G(g(x))\Bigr]=G'(g(x))\cdot g'(x).$$

Integration by **substitution** is simply the chain rule read backwards:

$$\int g'(x)\,f(g(x))\,dx = \int f(u)\,du,\qquad \text{where }u=g(x)\text{ and }du=g'(x)\,dx.$$

Instead of expanding $(x^2+1)^4$ into a long polynomial, we look for an **inner function** $u=g(x)$ whose derivative $g'(x)$ is sitting right outside as a factor multiplying $dx$.

## 1. Identifying the inner function $u$ and its derivative

In the integrand $2x(x^2+1)^4$:

- The expression inside the fourth power is $u=x^2+1$.
- Its derivative is $\dfrac{du}{dx}=2x$, so in differential form:
  $$du=2x\,dx.$$

Notice that the remaining factors in the integral, $2x\,dx$, match $du$ **exactly**.

## 2. Rewriting the integral in terms of $u$

Substituting $x^2+1=u$ and $2x\,dx=du$ transforms the integral into a simple power rule in $u$:

$$\int \underbrace{(x^2+1)^4}_{u^4}\underbrace{2x\,dx}_{du}=\int u^4\,du.$$

## 3. Integrating with respect to $u$ and substituting back

Applying the power rule to $u^4$:

$$\int u^4\,du = \frac{u^5}{5}+C.$$

Finally, we replace $u$ with the original expression $x^2+1$:

$$\int 2x(x^2+1)^4\,dx = \frac{(x^2+1)^5}{5}+C.$$

## Quick verification

We differentiate $F(x)=\dfrac{1}{5}(x^2+1)^5+C$ using the chain rule:

$$F'(x)=\frac{1}{5}\cdot 5(x^2+1)^4\cdot\frac{d}{dx}(x^2+1)+0=(x^2+1)^4\cdot 2x=2x(x^2+1)^4.$$

The chain rule produces the outer power $(x^2+1)^4$ and the inner derivative $2x$, recovering the exact integrand. ✓

## A concrete example

We could also have computed this integral by expanding $(x^2+1)^4=x^8+4x^6+6x^4+4x^2+1$, multiplying by $2x$, and integrating term by term:

$$\int\left(2x^9+8x^7+12x^5+8x^3+2x\right)\,dx = \frac{1}{5}x^{10}+x^8+2x^6+2x^4+x^2+\tilde{C}.$$

Notice that expanding our substitution answer gives:

$$\frac{(x^2+1)^5}{5}=\frac{x^{10}+5x^8+10x^6+10x^4+5x^2+1}{5}=\frac{1}{5}x^{10}+x^8+2x^6+2x^4+x^2+\frac{1}{5},$$

which is the exact same family of antiderivatives (with $\tilde{C}=C+\tfrac{1}{5}$), obtained in two lines instead of a five-term binomial expansion!

## How I would explain this in class

> When I look at $\int 2x(x^2+1)^4\,dx$, I see an inside function $x^2+1$ raised to the $4$th power, and right next to it is $2x$, which is the exact derivative of $x^2+1$. That tells me this product came from the chain rule. Setting $u=x^2+1$ gives $du=2x\,dx$, turning the whole integral into $\int u^4\,du = \frac{u^5}{5}+C$. Plugging $u=x^2+1$ back in gives $\frac{(x^2+1)^5}{5}+C$, and differentiating by the chain rule immediately confirms it.

## Related workbook topics

- [Exercise 5: The Same Substitution in a Different Context](problem_05_solution.md)
- [Exercise 6: When Does a Logarithm Appear from an Integral?](problem_06_solution.md)
