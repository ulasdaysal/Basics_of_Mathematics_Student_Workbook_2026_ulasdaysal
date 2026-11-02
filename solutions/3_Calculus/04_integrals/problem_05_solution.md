# Exercise 5. The Same Substitution in a Different Context

## The question

Compute

$$\int xe^{x^2}\,dx.$$

First compare the structure with Problem 4 and explain what is common despite the different appearance of the function.

## Before calculating: what idea do we need?

Substitution is recognized by **structural pattern**, not by whether the outer function is a power, an exponential, or a trigonometric function. Whenever an integral has the form

$$\int g'(x)\,f(g(x))\,dx,$$

the substitution $u=g(x)$ simplifies it to $\int f(u)\,du$.

Even if the outside factor differs from $g'(x)$ by a **constant multiplier** (for example, we have $x$ instead of $2x$), substitution still works easily because constants can be factored out of the integral.

## 1. Comparing the structure with Problem 4

Let us compare the two integrals side by side:

- **Problem 4:** $\displaystyle\int 2x\,(x^2+1)^4\,dx$ — an inner quadratic $x^2+1$ inside the outer power function $u^4$, multiplied outside by $2x$.
- **Problem 5:** $\displaystyle\int x\,e^{x^2}\,dx$ — an inner quadratic $x^2$ in the exponent of the outer function $e^u$, multiplied outside by $x$.

**What is common:** In both problems, the inner function is a quadratic expression in $x^2$, and the factor outside ($2x$ or $x$) is proportional to the derivative $\frac{d}{dx}(x^2)=2x$. Only the outer function changed (from $u^4$ to $e^u$) and a constant factor of $2$ is missing in front of $x$.

## 2. Setting up the substitution

Choose the inner function in the exponent as the new variable:

$$u=x^2.$$

Differentiating gives:

$$du=2x\,dx \implies x\,dx=\frac{1}{2}\,du.$$

## 3. Rewriting and computing the integral

Substitute $x^2=u$ and $x\,dx=\dfrac{1}{2}\,du$ into the integral:

$$\int e^{x^2}\,(x\,dx) = \int e^u\left(\frac{1}{2}\,du\right)=\frac{1}{2}\int e^u\,du.$$

Since the antiderivative of $e^u$ is $e^u$, we obtain:

$$\frac{1}{2}e^u+C.$$

Replacing $u$ back with $x^2$ gives the final family of antiderivatives:

$$\int xe^{x^2}\,dx = \frac{1}{2}e^{x^2}+C.$$

## Quick verification

We differentiate $F(x)=\dfrac{1}{2}e^{x^2}+C$ using the chain rule:

$$F'(x)=\frac{1}{2}\cdot\frac{d}{dx}\left(e^{x^2}\right)+0=\frac{1}{2}\cdot e^{x^2}\cdot\frac{d}{dx}(x^2)=\frac{1}{2}e^{x^2}\cdot(2x)=xe^{x^2}.$$

The factor $\frac{1}{2}$ cancels the $2$ produced by differentiating $x^2$, leaving $xe^{x^2}$. ✓

## A concrete example

Why is the factor $x$ in front of $e^{x^2}$ so important?
- **With $x$ in front:** $\int xe^{x^2}\,dx = \frac{1}{2}e^{x^2}+C$ is an elementary integral because $x$ supplies the chain-rule derivative of the inner function $x^2$.
- **Without $x$ in front:** $\int e^{x^2}\,dx$ cannot be written in terms of elementary functions at all! Without the outside factor $x$, setting $u=x^2$ leaves $dx=\frac{du}{2\sqrt{u}}$, which does not simplify.

## How I would explain this in class

> Even though $xe^{x^2}$ has an exponential instead of a power like in Problem 4, the underlying mechanism is identical: there is an inner $x^2$ and an outer $x\,dx$ that matches its derivative up to a constant factor. Setting $u=x^2$ gives $du=2x\,dx$, so $x\,dx=\frac{1}{2}\,du$. The integral immediately becomes $\frac{1}{2}\int e^u\,du = \frac{1}{2}e^{x^2}+C$. When we differentiate to check, the chain rule brings down $2x$, which cancels the $\frac{1}{2}$ and gives $xe^{x^2}$.

## Related workbook topics

- [Exercise 4: Substitution as Reversing the Chain Rule](problem_04_solution.md)
- [Exercise 15: Recovering a Function from Its Derivative and a Condition](problem_15_solution.md)
