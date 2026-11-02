# Exercise 6. When Does a Logarithm Appear from an Integral?

## The question

Compute

$$\int\frac{2x}{x^2+5}\,dx.$$

Identify the denominator as a candidate for substitution, compare the numerator with its derivative, and explain the source of the logarithm in the result.

## Before calculating: what idea do we need?

The power rule $\int u^n\,du=\dfrac{u^{n+1}}{n+1}+C$ works for every exponent **except $n=-1$** (where dividing by $n+1=0$ is impossible). That missing case is filled by the natural logarithm:

$$\frac{d}{du}\bigl(\ln|u|\bigr)=\frac{1}{u} \implies \int\frac{1}{u}\,du=\ln|u|+C.$$

When we combine this with the chain rule for $u=g(x)$, we get a famous pattern:

$$\frac{d}{dx}\Bigl(\ln|g(x)|\Bigr)=\frac{g'(x)}{g(x)} \implies \int\frac{g'(x)}{g(x)}\,dx=\ln|g(x)|+C.$$

Whenever a fraction has the **derivative of the denominator sitting in the numerator**, the integral is the natural logarithm of the denominator.

## 1. Comparing the denominator and numerator

In the fraction $\dfrac{2x}{x^2+5}$:

- The denominator is $u=x^2+5$.
- Its derivative with respect to $x$ is $\dfrac{du}{dx}=2x$, which is **identical to the numerator**.

Thus, the differential is:

$$du=2x\,dx.$$

## 2. Applying the substitution

Replacing $x^2+5$ by $u$ and $2x\,dx$ by $du$ transforms the integral into:

$$\int\frac{2x\,dx}{x^2+5}=\int\frac{1}{u}\,du.$$

## 3. Integrating and explaining the logarithm

Integrating $\dfrac{1}{u}$ with respect to $u$ gives the natural logarithm:

$$\int\frac{1}{u}\,du=\ln|u|+C.$$

Substituting $u=x^2+5$ back in:

$$\int\frac{2x}{x^2+5}\,dx=\ln|x^2+5|+C=\ln(x^2+5)+C.$$

- **Why the logarithm appears:** Because the denominator $u=x^2+5$ is to the first power in the denominator ($u^{-1}$), and $\ln|u|$ is the unique elementary function whose derivative is $u^{-1}$.
- **Why we can drop the absolute value bars here:** For every real number $x$, $x^2\ge 0$, so $x^2+5\ge 5>0$. Since the argument is strictly positive everywhere, $|x^2+5|=x^2+5$.

## Quick verification

We differentiate $F(x)=\ln(x^2+5)+C$ using the chain rule:

$$F'(x)=\frac{1}{x^2+5}\cdot\frac{d}{dx}(x^2+5)+0=\frac{1}{x^2+5}\cdot 2x=\frac{2x}{x^2+5}.$$

The outer derivative of $\ln u$ puts $x^2+5$ in the denominator, and the inner derivative puts $2x$ in the numerator. ✓

## A concrete example

Compare two slightly different denominators with the same numerator $2x$:
1. **First power in denominator (Problem 6):**
   $$\int\frac{2x}{x^2+5}\,dx=\int u^{-1}\,du=\ln(x^2+5)+C\quad\text{(logarithm)}.$$
2. **Square Root or Higher Power in denominator (like Problem 11.3):**
   $$\int\frac{2x}{(x^2+5)^2}\,dx=\int u^{-2}\,du=-u^{-1}+C=-\frac{1}{x^2+5}+C\quad\text{(power rule, no logarithm!)}.$$

A logarithm appears **only** when the whole denominator has exponent $1$ (so $u^{-1}$).

## How I would explain this in class

> Whenever I see a fraction in an integral, the first question I ask is: *"Is the numerator the derivative of the denominator?"* Here the denominator is $u=x^2+5$ and its derivative is $2x$, which is the exact numerator. Setting $u=x^2+5$ turns the integral into $\int\frac{1}{u}\,du = \ln|u|+C$. That's why a logarithm appears: $\frac{1}{u}$ is the $n=-1$ gap in the power rule. Since $x^2+5$ is always positive, we can write the final answer cleanly as $\ln(x^2+5)+C$.

## Related workbook topics

- [Exercise 4: Substitution as Reversing the Chain Rule](problem_04_solution.md)
- [Exercise 11: Choose the Method First](problem_11_solution.md)
