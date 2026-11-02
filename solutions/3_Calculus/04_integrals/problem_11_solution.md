# Exercise 11. Choose the Method First

## The question

For each integral, first write which method you choose and how you recognize it, and then compute:
1. $\displaystyle\int\sin(3x)\,dx$,
2. $\displaystyle\int x\ln x\,dx$,
3. $\displaystyle\int\frac{x}{\sqrt{x^2+1}}\,dx$.

## Before calculating: what idea do we need?

When facing an unfamiliar integral, we first inspect its **algebraic structure** before calculating:
1. **Composite function with a linear inner function** $f(ax+b)$: use **linear substitution** $u=ax+b$ (which simply divides the outer antiderivative by $a$).
2. **Product of two unrelated function types** (such as a power $x^n$ times a logarithm $\ln x$, where neither is the derivative of an inner function of the other): use **integration by parts** $\int u\,dv = uv - \int v\,du$.
3. **Composite function multiplied by the derivative of its inside** $g'(x)\,f(g(x))$: use **substitution** $u=g(x)$.

## 1. First integral: $\displaystyle\int\sin(3x)\,dx$

- **Method & how we recognize it:** **Linear substitution.** The integrand is a basic trigonometric function $\sin u$ composed with a linear inner function $u=3x$, whose derivative is the constant $3$.
- **Calculation:** Set $u=3x$, so $du=3\,dx \implies dx=\dfrac{1}{3}\,du$. Then:
  $$\int\sin(3x)\,dx = \int\sin u\left(\frac{1}{3}\,du\right) = \frac{1}{3}(-\cos u)+C = -\frac{1}{3}\cos(3x)+C.$$

## 2. Second integral: $\displaystyle\int x\ln x\,dx$ (for $x>0$)

- **Method & how we recognize it:** **Integration by parts.** This is a product of a polynomial ($x$) and a logarithm ($\ln x$). Substitution cannot work because neither factor is the derivative of an inner expression in the other. However, differentiating $\ln x$ turns it into the algebraic fraction $\dfrac{1}{x}$, which combines cleanly with the power of $x$!
- **Choice of parts:** We must differentiate $\ln x$ and integrate $x$:
  $$u=\ln x \implies du=\frac{1}{x}\,dx,\qquad dv=x\,dx \implies v=\frac{x^2}{2}.$$
- **Calculation:** Applying $\int u\,dv = uv - \int v\,du$:
  $$\int x\ln x\,dx = \frac{x^2}{2}\ln x - \int\frac{x^2}{2}\cdot\frac{1}{x}\,dx = \frac{x^2}{2}\ln x - \frac{1}{2}\int x\,dx = \frac{x^2}{2}\ln x - \frac{x^2}{4}+C.$$

## 3. Third integral: $\displaystyle\int\frac{x}{\sqrt{x^2+1}}\,dx$

- **Method & how we recognize it:** **Substitution (reversing the chain rule).** Inside the square root in the denominator is the quadratic $u=x^2+1$, and its derivative $2x$ is proportional to the numerator $x$.
- **Calculation:** Set $u=x^2+1$, so $du=2x\,dx \implies x\,dx=\dfrac{1}{2}\,du$. Rewriting the square root in the denominator as a power $u^{-1/2}$:
  $$\int\frac{x\,dx}{\sqrt{x^2+1}} = \int\frac{\frac{1}{2}\,du}{\sqrt{u}} = \frac{1}{2}\int u^{-1/2}\,du = \frac{1}{2}\cdot\frac{u^{1/2}}{1/2}+C = \sqrt{u}+C = \sqrt{x^2+1}+C.$$

## Quick verification

We differentiate all three results to verify them:

1. $\dfrac{d}{dx}\left(-\dfrac{1}{3}\cos(3x)+C\right) = -\dfrac{1}{3}\bigl(-\sin(3x)\cdot 3\bigr)=\sin(3x)$. ✓
2. $\dfrac{d}{dx}\left(\dfrac{x^2}{2}\ln x - \dfrac{x^2}{4}+C\right) = \left(x\ln x + \dfrac{x^2}{2}\cdot\dfrac{1}{x}\right)-\dfrac{2x}{4} = x\ln x + \dfrac{x}{2}-\dfrac{x}{2}=x\ln x$. ✓
3. $\dfrac{d}{dx}\left((x^2+1)^{1/2}+C\right) = \dfrac{1}{2}(x^2+1)^{-1/2}\cdot(2x) = \dfrac{x}{\sqrt{x^2+1}}$. ✓

## A concrete example

Notice how in integral (2), $\int x\ln x\,dx$, the roles in integration by parts are the **reverse** of $\int xe^x\,dx$ and $\int x\cos x\,dx$:
- For $xe^x$ and $x\cos x$, we set $u=x$ to eliminate the polynomial.
- For $x\ln x$, if we set $dv=\ln x\,dx$, we immediately get stuck because $\ln x$ is not an elementary derivative on our basic list; whereas setting $u=\ln x$ turns the transcendental function $\ln x$ into the rational function $\frac{1}{x}$, reducing $\int v\,du$ to the simple polynomial integral $\frac{1}{2}\int x\,dx$.

## How I would explain this in class

> I always diagnose the structure before computing. In (1), $\sin(3x)$ has a linear inside $3x$, so substitution $u=3x$ just divides by $3$ to give $-\frac{1}{3}\cos(3x)+C$. In (2), $x\ln x$ is a product of a power and a logarithm, which calls for integration by parts with $u=\ln x$ and $dv=x\,dx$ because differentiating $\ln x$ gives $\frac{1}{x}$ and cancels a power of $x^2$, yielding $\frac{x^2}{2}\ln x-\frac{x^2}{4}+C$. In (3), the numerator $x$ is half the derivative of the inside $x^2+1$ under the square root, so substituting $u=x^2+1$ turns it into $\frac{1}{2}\int u^{-1/2}\,du = \sqrt{x^2+1}+C$.

## Related workbook topics

- [Exercise 4: Substitution as Reversing the Chain Rule](problem_04_solution.md)
- [Exercise 8: Choosing the Factors in Integration by Parts](problem_08_solution.md)
