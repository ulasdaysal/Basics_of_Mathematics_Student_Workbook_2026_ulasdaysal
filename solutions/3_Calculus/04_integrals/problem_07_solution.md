# Exercise 7. Integration by Parts as Reversing the Product Rule

## The question

Compute

$$\int xe^x\,dx.$$

First write the product differentiation rule and, on that basis, explain the meaning of the integration-by-parts formula. Verify the result by differentiation.

## Before calculating: what idea do we need?

Why doesn't substitution work on $\int xe^x\,dx$? Because the exponent is $x$ (not $x^2$), so the factor $x$ in front is **not** the derivative of the inner function; instead, $x$ and $e^x$ are two independent factors multiplied together.

Just as substitution reverses the chain rule, **integration by parts** reverses the **product rule** for derivatives. It trades an integral of one product $\int u\,dv$ for an integral of another product $\int v\,du$ that is simpler to compute.

## 1. From the product rule to integration by parts

For two differentiable functions $u(x)$ and $v(x)$, the product differentiation rule states:

$$(u\cdot v)' = u'\cdot v + u\cdot v'.$$

Integrating both sides with respect to $x$ gives:

$$u\cdot v = \int u'\,v\,dx + \int u\,v'\,dx.$$

Rearranging to isolate $\int u\,v'\,dx$ (and writing $du=u'\,dx$, $dv=v'\,dx$) yields the **integration-by-parts formula**:

$$\int u\,dv = u\,v - \int v\,du.$$

**Meaning of the formula:** If we split our integrand into a factor $u$ (which we differentiate) and a differential $dv$ (which we integrate), we can shift the derivative onto $u$ so that the new integral $\int v\,du$ becomes easier than the original one.

## 2. Choosing the parts for $\int xe^x\,dx$

We want the new integral $\int v\,du$ to be simpler than $\int xe^x\,dx$. Notice that differentiating $x$ reduces it to the constant $1$, while integrating $e^x$ leaves $e^x$ unchanged:

$$\begin{aligned}
u &= x & \implies \quad du &= 1\,dx, \\
dv &= e^x\,dx & \implies \quad v &= e^x.
\end{aligned}$$

## 3. Applying the integration-by-parts formula

Substitute $u$, $du$, $v$, and $dv$ into $\int u\,dv = u\,v - \int v\,du$:

$$\int \underbrace{x}_{u}\underbrace{e^x\,dx}_{dv} = \underbrace{x}_{u}\underbrace{e^x}_{v} - \int \underbrace{e^x}_{v}\underbrace{dx}_{du} = xe^x - \int e^x\,dx.$$

The remaining integral is the basic exponential integral $\int e^x\,dx=e^x+C$, so we get:

$$\int xe^x\,dx = xe^x - e^x + C = (x-1)e^x + C.$$

## Quick verification

We differentiate $F(x)=xe^x-e^x+C$ using the product rule on the first term $xe^x$:

$$F'(x)=\frac{d}{dx}(x\cdot e^x)-\frac{d}{dx}(e^x)+0=\left(1\cdot e^x + x\cdot e^x\right)-e^x=e^x+xe^x-e^x=xe^x.$$

Notice how the extra $+e^x$ created by the product rule on $xe^x$ is cancelled by the derivative of $-e^x$, leaving $xe^x$. ✓

## A concrete example

Why isn't the antiderivative of a product simply the product of the antiderivatives?
If someone guessed $\left(\int x\,dx\right)\left(\int e^x\,dx\right)=\frac{1}{2}x^2e^x$, its derivative would be $xe^x+\frac{1}{2}x^2e^x$, which is wrong. Even if someone guessed $xe^x$, differentiating $xe^x$ by the product rule gives $xe^x+e^x$—it has an unwanted $+e^x$ term. Subtracting $e^x$ in $xe^x-e^x$ is precisely what cancels that unwanted product-rule term!

## How I would explain this in class

> The product rule says $(uv)' = u'v + uv'$. Rearranging and integrating gives $\int u\,dv = uv - \int v\,du$. For $\int xe^x\,dx$, I choose $u=x$ and $dv=e^x\,dx$ because differentiating $x$ turns it into $1$, which eliminates the $x$ factor from the new integral. The formula gives $xe^x - \int e^x\,dx = xe^x - e^x + C$. When we check by differentiating $xe^x - e^x$, the product rule on $xe^x$ gives $e^x + xe^x$, and the $-e^x$ cancels the extra $e^x$.

## Related workbook topics

- [Exercise 8: Choosing the Factors in Integration by Parts](problem_08_solution.md)
- [Exercise 11: Choose the Method First](problem_11_solution.md)
