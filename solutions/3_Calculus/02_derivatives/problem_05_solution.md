# Exercise 5. The Chain Rule as Working Through Layers

## The question

For

$$f(x)=(3x^2-2x+1)^5$$

identify the inner and outer functions, compute their derivatives, and combine the result according to the chain rule. Explain the origin of the additional factor.

## Before calculating: what idea do we need?

When we evaluate $f(x)=(3x^2-2x+1)^5$ for a number $x$, we do it in two steps (layers):
1. First compute the inside expression $u=g(x)=3x^2-2x+1$.
2. Then raise that result to the $5$-th power: $y=h(u)=u^5$.

So $f(x)=h(g(x))$ is a **composite function**. The **chain rule** states that the derivative of a composition is the product of the derivatives of its layers:

$$f'(x)=h'(g(x))\cdot g'(x) \qquad\text{or}\qquad \frac{dy}{dx}=\frac{dy}{du}\cdot\frac{du}{dx}.$$

## 1. Identify the inner and outer functions

Decompose $f(x)=(3x^2-2x+1)^5$ into its two layers:

- **Inner function**: $u=g(x)=3x^2-2x+1$,
- **Outer function**: $y=h(u)=u^5$.

## 2. Differentiate each layer separately

- Derivative of the outer function with respect to $u$:

$$h'(u)=\frac{dy}{du}=5u^4.$$

- Derivative of the inner function with respect to $x$:

$$g'(x)=\frac{du}{dx}=6x-2.$$

## 3. Combine according to the chain rule

Substitute $u=3x^2-2x+1$ back into $h'(u)$ and multiply by $g'(x)$:

$$f'(x)=5(3x^2-2x+1)^4\cdot(6x-2).$$

We can also factor $2$ out of $(6x-2)=2(3x-1)$ to write:

$$f'(x)=10(3x-1)(3x^2-2x+1)^4.$$

## 4. Explain the origin of the additional factor $(6x-2)$

Why isn't the derivative just $5(3x^2-2x+1)^4$?

Because $5u^4$ only measures how fast the output $y=u^5$ changes **per unit change in $u$**, not per unit change in $x$. When $x$ changes by a small amount $\Delta x$, the intermediate quantity $u=3x^2-2x+1$ does not change by $\Delta x$; it changes by approximately

$$\Delta u \approx g'(x)\,\Delta x = (6x-2)\,\Delta x.$$

Then the output $y=u^5$ changes by

$$\Delta y \approx 5u^4\,\Delta u \approx 5(3x^2-2x+1)^4(6x-2)\,\Delta x.$$

The factor $(6x-2)$ is the local magnification factor of the inner layer $u(x)$.

## Quick verification

Check at $x=0$:

- Using our chain rule formula:

$$f'(0)=5(0-0+1)^4(0-2)=5(1)^4(-2)=-10.$$

- Alternatively, expand only the lowest-degree terms of $(1-2x+3x^2)^5$ near $x=0$ using the binomial theorem $(1+w)^5 = 1 + 5w + 10w^2 + \dots$:

$$f(x) = 1 + 5(-2x+3x^2) + \dots = 1 - 10x + O(x^2).$$

The coefficient of $x$ is $-10$, which must equal $f'(0)$. ✓

## A concrete example

Look at $x=\dfrac{1}{3}$:

$$g'\left(\frac{1}{3}\right)=6\left(\frac{1}{3}\right)-2=0 \implies f'\left(\frac{1}{3}\right)=5\left(3\cdot\frac{1}{9}-\frac{2}{3}+1\right)^4\cdot 0=0.$$

Because the inner parabola $u=3x^2-2x+1$ has its vertex (horizontal tangent) at $x=\dfrac{1}{3}$, a tiny change in $x$ around $\dfrac{1}{3}$ produces zero first-order change in $u$, and therefore zero first-order change in $u^5$.

## How I would explain this in class

> We view $f(x)=(3x^2-2x+1)^5$ like peeling an onion from the outside in. The outer layer is a $5$-th power $u^5$, whose derivative is $5u^4=5(3x^2-2x+1)^4$, evaluated at the unchanged inner function. Then the chain rule tells us to multiply by the derivative of the inner layer $u=3x^2-2x+1$, which is $6x-2$, because $u$ itself is changing at rate $6x-2$ with respect to $x$.

## Related workbook topics

- [Exercise 7: A Trigonometric Composition](problem_07_solution.md)
- [Exercise 13: A Multi-Layer Composition](problem_13_solution.md)
