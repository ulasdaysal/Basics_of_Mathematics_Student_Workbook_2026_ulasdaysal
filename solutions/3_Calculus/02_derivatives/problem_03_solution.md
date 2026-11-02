# Exercise 3. The Product Rule — Why Is It Needed?

## The question

For

$$f(x)=(x^2+1)e^x$$

compute the derivative. Then compare the correct result with the incorrect idea

$$f'(x)\stackrel{?}{=}(2x)e^x$$

and explain which term is missing.

## Before calculating: what idea do we need?

When a function is a product of two variable factors $u(x)$ and $v(x)$, **the derivative of a product is not the product of the derivatives**. Instead, we must use the **product rule**:

$$(u(x)v(x))'=u'(x)v(x)+u(x)v'(x).$$

Why does it have two terms? Imagine a rectangle with side lengths $u(x)$ and $v(x)$ and area $A(x)=u(x)v(x)$. When $x$ changes by a tiny amount $\Delta x$, **both sides grow simultaneously**:
- the change in width $u$ multiplied by the height $v$ gives $u'(x)v(x)\,\Delta x$,
- the width $u$ multiplied by the change in height $v$ gives $u(x)v'(x)\,\Delta x$.

Leaving out either term ignores the growth of one of the two factors.

## 1. Identify the two factors and their derivatives

Write $f(x)=u(x)v(x)$ with:

- $u(x)=x^2+1 \implies u'(x)=2x$,
- $v(x)=e^x \implies v'(x)=e^x$.

## 2. Apply the product rule

Substitute $u,u',v,v'$ into $f'(x)=u'(x)v(x)+u(x)v'(x)$:

$$f'(x)=(2x)e^x+(x^2+1)e^x.$$

Factor out the common factor $e^x$ to write the derivative cleanly:

$$f'(x)=(x^2+2x+1)e^x=(x+1)^2e^x.$$

## 3. Compare with the incorrect formula and explain the missing term

The proposed guess was

$$f_{\text{wrong}}'(x)=(2x)e^x.$$

Because $\dfrac{d}{dx}(e^x)=e^x$, this mistake is doubly deceptive:
1. A student who mistakenly thinks $(uv)'=u'v'$ computes $(x^2+1)'\cdot(e^x)'=(2x)e^x$.
2. A student who differentiates the first factor $(x^2+1)$ and forgets to differentiate the second factor $e^x$ also gets $(2x)e^x$.

In both cases, the **missing term** is

$$u(x)v'(x)=(x^2+1)e^x,$$

which accounts for how fast $e^x$ changes while $x^2+1$ acts as the multiplier.

## Quick verification

Let us test both formulas at $x=0$:

- At $x=0$, $f(x)=(x^2+1)e^x$ has value $f(0)=1\cdot e^0=1$.
- For small $x$, $x^2$ is negligible compared to $x$, so $f(x)=(1+x^2)e^x \approx 1\cdot(1+x)=1+x$, which has slope $1$ at $x=0$.
- Our product-rule formula gives $f'(0)=(0+1)^2e^0=1$. ✓
- The incorrect formula gives $f_{\text{wrong}}'(0)=2(0)e^0=0$, claiming a horizontal tangent at $x=0$ even though $f(0)=1$ and $f(0.1)=1.01\cdot e^{0.1}\approx 1.1162$ (slope $\approx 1.16$). ✓

## A concrete example

Look at $x=-1$:

$$f'(-1)=(-1+1)^2e^{-1}=0.$$

Because $f'(x)=(x+1)^2e^x\ge0$ for all $x\in\mathbb{R}$, the function $f(x)=(x^2+1)e^x$ is strictly increasing everywhere on $\mathbb{R}$, pausing with a horizontal inflection tangent only at $x=-1$, not at $x=0$.

## How I would explain this in class

> Since $f(x)=(x^2+1)e^x$ is a product of two functions of $x$, we must use the product rule $(uv)'=u'v+uv'$. That gives $f'(x)=2xe^x+(x^2+1)e^x=(x+1)^2e^x$. Writing just $2xe^x$ is wrong because it misses the second term $(x^2+1)e^x$, which comes from keeping $(x^2+1)$ fixed and differentiating $e^x$.

## Related workbook topics

- [Exercise 6: Product Rule and Trigonometry](problem_06_solution.md)
- [Exercise 12: Several Rules at Once](problem_12_solution.md)
