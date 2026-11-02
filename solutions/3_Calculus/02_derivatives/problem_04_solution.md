# Exercise 4. A Quotient and Domain Control

## The question

For

$$f(x)=\frac{x^2+1}{x-1}$$

determine the domain, compute the derivative, simplify the result, and explain why the restriction $x\neq1$ remains important.

## Before calculating: what idea do we need?

When a function has the form $f(x)=\dfrac{u(x)}{v(x)}$, we need two things:

1. **Domain control**: the denominator cannot be zero ($v(x)\neq0$).
2. **The quotient rule**: at every point where $u$ and $v$ are differentiable and $v(x)\neq0$,

$$\left(\frac{u(x)}{v(x)}\right)'=\frac{u'(x)v(x)-u(x)v'(x)}{(v(x))^2}.$$

Watch the **order in the numerator**: because of the minus sign, $u'v$ must come first and $uv'$ second (switching them flips the sign of the entire derivative).

## 1. Determine the domain

The numerator $x^2+1$ and denominator $x-1$ are polynomials defined for all real $x$, so the only restriction is that the denominator cannot vanish:

$$x-1\neq0 \iff x\neq1.$$

Thus the domain of $f$ is

$$D_f=\mathbb{R}\setminus\{1\}=(-\infty,1)\cup(1,\infty).$$

## 2. Apply the quotient rule

Identify the numerator and denominator and differentiate each:

- $u(x)=x^2+1 \implies u'(x)=2x$,
- $v(x)=x-1 \implies v'(x)=1$.

Substitute into the quotient rule:

$$f'(x)=\frac{(2x)(x-1)-(x^2+1)(1)}{(x-1)^2}.$$

## 3. Simplify the result

Expand the numerator and combine like terms:

$$f'(x)=\frac{2x^2-2x-x^2-1}{(x-1)^2}=\frac{x^2-2x-1}{(x-1)^2}.$$

## 4. Why the restriction $x\neq1$ remains important

The restriction $x\neq1$ is crucial for three connected reasons:

1. **Algebraic**: setting $x=1$ in $f'(x)$ produces $(1-1)^2=0$ in the denominator, so $f'(1)$ is undefined.
2. **Geometric**: the line $x=1$ is a **vertical asymptote** of $f(x)$ ($\lim_{x\to1^-}f(x)=-\infty$ and $\lim_{x\to1^+}f(x)=+\infty$). There is no point on the graph at $x=1$, so no tangent line can exist there.
3. **Analytical**: because $x=1$ splits the domain into two separate intervals $(-\infty,1)$ and $(1,\infty)$, any theorem about the sign of $f'(x)$ (such as monotonicity or the Mean Value Theorem) applies on each interval $(-\infty,1)$ and $(1,\infty)$ **separately**, never across the jump at $x=1$.

## Quick verification

We can rewrite $f(x)$ by polynomial division for $x\neq1$:

$$f(x)=\frac{(x^2-1)+2}{x-1}=\frac{(x-1)(x+1)+2}{x-1}=x+1+\frac{2}{x-1}=x+1+2(x-1)^{-1}.$$

Differentiating term by term gives:

$$f'(x)=1+0-2(x-1)^{-2}=1-\frac{2}{(x-1)^2}=\frac{(x-1)^2-2}{(x-1)^2}=\frac{x^2-2x-1}{(x-1)^2}.\quad\checkmark$$

Both methods produce the exact same simplified formula.

## A concrete example

At $x=2$:

$$f(2)=\frac{2^2+1}{2-1}=5,\qquad f'(2)=\frac{2^2-2(2)-1}{(2-1)^2}=\frac{4-4-1}{1}=-1.$$

At $x=0$:

$$f(0)=\frac{0^2+1}{0-1}=-1,\qquad f'(0)=\frac{0-0-1}{(0-1)^2}=-1.$$

Even though $f'(0)=-1<0$ and $f'(2)=-1<0$, notice that $f(0)=-1 < f(2)=5$! Why did the function value go up from $-1$ to $5$ if the derivative was negative at those points? Because the vertical asymptote at $x=1$ separates $x=0$ and $x=2$ into two disconnected branches.

## How I would explain this in class

> First, the denominator $x-1$ cannot be zero, so the domain is $x\neq1$. Next, using the quotient rule $\frac{u'v-uv'}{v^2}$ with $u=x^2+1$ and $v=x-1$, we get $f'(x)=\frac{2x(x-1)-(x^2+1)\cdot1}{(x-1)^2}=\frac{x^2-2x-1}{(x-1)^2}$. We must keep the condition $x\neq1$ because the graph has a vertical asymptote there, splitting the function into two separate branches.

## Related workbook topics

- [Exercise 2: Powers, Roots, and the Domain](problem_02_solution.md)
- [Exercise 9: A Logarithm and the Chain Rule](problem_09_solution.md)
