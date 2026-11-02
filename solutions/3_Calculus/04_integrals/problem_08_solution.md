# Exercise 8. Choosing the Factors in Integration by Parts

## The question

Compute

$$\int x\cos x\,dx.$$

Before calculating, justify why it is convenient to differentiate $x$ and integrate $\cos x$, rather than the other way around.

## Before calculating: what idea do we need?

In integration by parts,

$$\int u\,dv = u\,v - \int v\,du,$$

the entire goal is to make the **new integral $\int v\,du$ simpler** than the original integral $\int u\,dv$.

When our integrand is a product of two functions, we have two ways to assign $u$ (the factor to differentiate) and $dv$ (the factor to integrate). We should choose $u$ so that differentiating it simplifies it, while $dv$ can be integrated without becoming more complicated.

## 1. Justifying the choice of factors

We compare the two possible assignments for $\int x\cos x\,dx$:

- **Choice A (differentiate $x$, integrate $\cos x$):**
  $$u=x \implies du=1\,dx,\qquad dv=\cos x\,dx \implies v=\sin x.$$
  Here, differentiating $x$ drops its degree from $1$ to $0$ (it becomes the constant $1$), while integrating $\cos x$ simply switches it to $\sin x$ without increasing complexity. The new integral is $\int \sin x\,dx$, which is an immediate basic integral.
- **Choice B (differentiate $\cos x$, integrate $x$):**
  $$u=\cos x \implies du=-\sin x\,dx,\qquad dv=x\,dx \implies v=\frac{x^2}{2}.$$
  Here, integrating $x$ **raises** the power of $x$ to $\frac{1}{2}x^2$, turning the new integral into $\int \frac{1}{2}x^2(-\sin x)\,dx$, which is **more complicated** than what we started with!

Therefore, we must choose $u=x$ and $dv=\cos x\,dx$.

## 2. Applying integration by parts

With $u=x$, $du=dx$, $dv=\cos x\,dx$, and $v=\sin x$, the integration-by-parts formula gives:

$$\int \underbrace{x}_{u}\underbrace{\cos x\,dx}_{dv} = \underbrace{x}_{u}\underbrace{\sin x}_{v} - \int \underbrace{\sin x}_{v}\underbrace{dx}_{du} = x\sin x - \int \sin x\,dx.$$

## 3. Computing the remaining basic integral

Since $\dfrac{d}{dx}(\cos x)=-\sin x$, we have $\int \sin x\,dx = -\cos x + C$. Substituting this in (and watching the double minus sign):

$$\int x\cos x\,dx = x\sin x - (-\cos x) + C = x\sin x + \cos x + C.$$

## Quick verification

We differentiate $F(x)=x\sin x+\cos x+C$ using the product rule on $x\sin x$:

$$F'(x)=\frac{d}{dx}(x\sin x)+\frac{d}{dx}(\cos x)+0=\left(1\cdot\sin x + x\cos x\right)-\sin x = x\cos x.$$

The $+\sin x$ from differentiating the first factor cancels the $-\sin x$ from differentiating $\cos x$, leaving $x\cos x$. ✓

## A concrete example

Let us see explicitly what happens if we make the wrong choice (Choice B: $u=\cos x$, $dv=x\,dx$):

$$\int x\cos x\,dx = \frac{1}{2}x^2\cos x - \int \frac{1}{2}x^2(-\sin x)\,dx = \frac{1}{2}x^2\cos x + \frac{1}{2}\int x^2\sin x\,dx.$$

Although this equation is mathematically true, it replaced $x\cos x$ with $x^2\sin x$, moving us one step further away from an elementary integral instead of closer to one.

## How I would explain this in class

> In integration by parts, we want $\int v\,du$ to be simpler than $\int u\,dv$. For $\int x\cos x\,dx$, differentiating $x$ reduces it to $1$, whereas integrating $x$ would turn it into $\frac{1}{2}x^2$ and make the integral worse. Meanwhile, integrating $\cos x$ just gives $\sin x$. So I set $u=x$ and $dv=\cos x\,dx$, which gives $x\sin x - \int \sin x\,dx = x\sin x + \cos x + C$. Differentiating by the product rule confirms the answer right away.

## Related workbook topics

- [Exercise 7: Integration by Parts as Reversing the Product Rule](problem_07_solution.md)
- [Exercise 11: Choose the Method First](problem_11_solution.md)
