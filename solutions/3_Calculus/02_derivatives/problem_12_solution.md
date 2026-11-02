# Exercise 12. Several Rules at Once

## The question

For

$$f(x)=(x^2+1)^3e^x$$

compute the derivative. Before calculating, write down a plan: which rule applies to the whole expression and which rule applies to one of its factors. Finally, organize the result by factoring out common factors.

## Before calculating: what idea do we need?

When an expression combines several operations, we always **differentiate from the outermost operation inward**:

1. **Top-level structure (the whole expression)**: $f(x)=\underbrace{(x^2+1)^3}_{u(x)}\cdot\underbrace{e^x}_{v(x)}$ is a **product** of two factors. Therefore, the **product rule** $(uv)'=u'v+uv'$ governs the overall derivative.
2. **Sub-problem (the first factor)**: to find $u'(x)$ for $u(x)=(x^2+1)^3$, notice that $u(x)$ is a **composition** (an inner polynomial $x^2+1$ raised to the $3$-rd power). Therefore, we must apply the **chain rule** inside the first step of the product rule.

## 1. Write the differentiation plan

- **Step A (Outer rule — Product Rule)**: Write $f(x)=u(x)v(x)$ with $u(x)=(x^2+1)^3$ and $v(x)=e^x$, so

$$f'(x)=u'(x)v(x)+u(x)v'(x).$$

- **Step B (Inner rule — Chain Rule on $u(x)$)**: Differentiate $u(x)=(x^2+1)^3$ by differentiating the outer cube $w^3\mapsto 3w^2$ and multiplying by the derivative of the inner polynomial $w=x^2+1\mapsto 2x$.
- **Step C (Algebraic cleanup)**: Factor out the greatest common factors $(x^2+1)^2$ and $e^x$.

## 2. Differentiate each factor

For the first factor $u(x)=(x^2+1)^3$, apply the chain rule:

$$u'(x)=3(x^2+1)^2\cdot\frac{d}{dx}(x^2+1)=3(x^2+1)^2\cdot(2x)=6x(x^2+1)^2.$$

For the second factor $v(x)=e^x$:

$$v'(x)=e^x.$$

## 3. Combine with the product rule

Substitute $u,u',v,v'$ into $f'(x)=u'(x)v(x)+u(x)v'(x)$:

$$f'(x)=6x(x^2+1)^2e^x+(x^2+1)^3e^x.$$

## 4. Factor out common factors

Both terms contain $(x^2+1)^2$ and $e^x$. Factor out $(x^2+1)^2e^x$:

$$f'(x)=(x^2+1)^2e^x\big[6x+(x^2+1)\big]=(x^2+1)^2(x^2+6x+1)e^x.$$

Why is this factored form much better than the unfactored sum?
- We can immediately see the sign of $f'(x)$: since $(x^2+1)^2>0$ and $e^x>0$ for all $x\in\mathbb{R}$, the zeros and sign changes of $f'(x)$ come solely from the quadratic factor $x^2+6x+1$.

## Quick verification

Let us check at $x=0$ and $x=1$:

- **At $x=0$**:
  - Factored formula: $f'(0)=(0+1)^2(0+0+1)e^0=1\cdot1\cdot1=1$.
  - Small-$x$ expansion of $f(x)=(1+x^2)^3e^x$: since $(1+x^2)^3=1+3x^2+\dots$ has no linear $x$ term, near $x=0$ we have $f(x)\approx 1\cdot(1+x)=1+x$, so $f'(0)=1$. ✓
- **At $x=1$**:
  - Unfactored sum: $6(1)(2)^2e^1+(2)^3e^1=24e+8e=32e$.
  - Factored formula: $(1+1)^2(1+6+1)e^1=4\cdot8\cdot e=32e$. ✓

## A concrete example

To find the critical points of $f(x)=(x^2+1)^3e^x$ (where the tangent line is horizontal, $f'(x)=0$), our factored form makes the task effortless:

$$(x^2+1)^2(x^2+6x+1)e^x=0 \iff x^2+6x+1=0 \iff x=-3\pm\sqrt{9-1}=-3\pm2\sqrt{2}.$$

Without factoring out $(x^2+1)^2e^x$, solving $6x(x^2+1)^2e^x+(x^2+1)^3e^x=0$ would look like a degree-$6$ equation!

## How I would explain this in class

> Before differentiating $f(x)=(x^2+1)^3e^x$, we look at its overall structure: it is a product of $(x^2+1)^3$ and $e^x$, so we start with the product rule. When we need the derivative of the first factor $(x^2+1)^3$, we use the chain rule to get $3(x^2+1)^2\cdot 2x=6x(x^2+1)^2$. Putting the product rule together gives $6x(x^2+1)^2e^x+(x^2+1)^3e^x$, and factoring out $(x^2+1)^2e^x$ simplifies the answer to $(x^2+1)^2(x^2+6x+1)e^x$.

## Related workbook topics

- [Exercise 3: The Product Rule — Why Is It Needed?](problem_03_solution.md)
- [Exercise 5: The Chain Rule as Working Through Layers](problem_05_solution.md)
