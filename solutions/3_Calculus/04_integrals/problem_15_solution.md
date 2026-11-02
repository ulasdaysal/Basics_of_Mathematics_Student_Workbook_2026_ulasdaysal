# Exercise 15. Recovering a Function from Its Derivative and a Condition

## The question

The function $F$ satisfies

$$F'(x)=2xe^{x^2}\qquad\text{and}\qquad F(0)=3.$$

1. Recognize the method needed to find the function $F$.
2. Determine the entire family of functions with the given derivative.
3. Use the condition $F(0)=3$ to determine the correct constant.
4. Verify the final result by differentiation and substitution of $x=0$.

## Before calculating: what idea do we need?

Knowing the derivative $F'(x)$ of a function tells us its **slope everywhere**, which determines the function up to an unknown vertical shift $+C$:

$$F(x)=\int F'(x)\,dx.$$

To single out **one specific function** from this infinite family of parallel curves, we need one piece of pinpoint information—an **initial condition** $F(x_0)=y_0$ that tells us one point $(x_0,y_0)$ through which the graph must pass.

## 1. Recognizing the method to find $F$

We need to integrate $F'(x)=2xe^{x^2}$:

$$F(x)=\int 2xe^{x^2}\,dx.$$

Looking at the structure of $2xe^{x^2}$, we see an inner function $u=x^2$ inside the exponential $e^u$, multiplied outside by its exact derivative $u'=2x$. Therefore, the appropriate method is **substitution** (reversing the chain rule) with $u=x^2$.

## 2. Determining the entire family of antiderivatives

Set $u=x^2$, so that $du=2x\,dx$. Substituting into the integral gives:

$$F(x)=\int e^{x^2}\,(2x\,dx) = \int e^u\,du = e^u + C = e^{x^2} + C,\qquad C\in\mathbb{R}.$$

This is the entire family of functions whose derivative is $2xe^{x^2}$.

## 3. Using the condition $F(0)=3$ to find the constant $C$

We substitute $x=0$ into $F(x)=e^{x^2}+C$ and set the result equal to $3$:

$$F(0)=e^{0^2}+C=3.$$

Since $e^0=1$ (a very important detail—$e^0$ is $1$, not $0$!), this gives:

$$1+C=3 \implies C=2.$$

Therefore, the unique function satisfying both conditions is:

$$F(x)=e^{x^2}+2.$$

## 4. Quick verification

We check both conditions independently:

1. **Differentiation check:** Using the chain rule on $F(x)=e^{x^2}+2$:
   $$F'(x)=\frac{d}{dx}\left(e^{x^2}\right)+\frac{d}{dx}(2)=e^{x^2}\cdot(2x)+0=2xe^{x^2}.\quad\checkmark$$
2. **Initial condition check at $x=0$:**
   $$F(0)=e^{0^2}+2=1+2=3.\quad\checkmark$$

Both requirements of the problem are satisfied. ✓

## A concrete example

A frequent trap in initial-value problems involving exponentials or cosines is assuming that plugging in $x=0$ makes the function part vanish so that $C=F(0)$. Here:
- Had the function been a polynomial with no constant term, like $G(x)=x^3+C$, then $G(0)=3$ would indeed give $0+C=3 \implies C=3$.
- For $F(x)=e^{x^2}+C$, however, the base function already has height $e^0=1$ at $x=0$. To reach a total height of $F(0)=3$, we only need to shift the curve up by $C=3-1=2$.

## How I would explain this in class

> To recover $F(x)$ from $F'(x)=2xe^{x^2}$, I first integrate to get the family of antiderivatives. Since $2x$ is the exact derivative of the exponent $x^2$, substituting $u=x^2$ gives $\int e^u\,du = e^{x^2}+C$. That $+C$ represents a whole vertical family of curves. To pick out the one curve passing through $(0,3)$, I plug $x=0$ into $F(0)=e^0+C=3$. Since $e^0=1$, we get $1+C=3$, so $C=2$ and $F(x)=e^{x^2}+2$. Differentiating gives $2xe^{x^2}$ and plugging in $0$ gives $1+2=3$.

## Related workbook topics

- [Exercise 1: Antiderivative and Verification](problem_01_solution.md)
- [Exercise 5: The Same Substitution in a Different Context](problem_05_solution.md)
