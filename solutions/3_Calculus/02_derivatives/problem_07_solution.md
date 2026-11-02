# Exercise 7. A Trigonometric Composition

## The question

For

$$f(x)=\sin(x^2+1)$$

compute the derivative. Explicitly identify the outer function, the inner function, and the derivative of the inner function. Finally, determine the sign of $f'(0)$.

## Before calculating: what idea do we need?

Unlike $x\sin x$, the expression $\sin(x^2+1)$ is **not a product** ("$\sin$" by itself is not a number or factor; it is an operation applied to the angle $x^2+1$). Instead, $f(x)=\sin(x^2+1)$ is a **composition** $h(g(x))$:
- first, $x$ is mapped to the angle $u=g(x)=x^2+1$,
- second, the sine function is applied to $u$: $y=h(u)=\sin u$.

By the **chain rule**,

$$\frac{d}{dx}\big(\sin(g(x))\big)=\cos(g(x))\cdot g'(x).$$

## 1. Identify the outer function, inner function, and inner derivative

Break $f(x)=\sin(x^2+1)$ into its components:

- **Inner function**: $u=g(x)=x^2+1$,
- **Outer function**: $y=h(u)=\sin u$,
- **Derivative of the outer function**: $h'(u)=\cos u=\cos(x^2+1)$,
- **Derivative of the inner function**: $g'(x)=\dfrac{d}{dx}(x^2+1)=2x$.

## 2. Compute the derivative $f'(x)$

Multiply the derivative of the outer function (evaluated at the inner function $x^2+1$) by the derivative of the inner function:

$$f'(x)=\cos(x^2+1)\cdot 2x=2x\cos(x^2+1).$$

*(Writing the algebraic factor $2x$ in front of $\cos(x^2+1)$ avoids any ambiguity about whether $2x$ is inside or outside the cosine.)*

## 3. Determine the sign of $f'(0)$

Substitute $x=0$ into $f'(x)=2x\cos(x^2+1)$:

$$f'(0)=2(0)\cos(0^2+1)=0\cdot\cos(1)=0.$$

Because $f'(0)=0$, the value is **neither positive nor negative** (its sign is zero). Even though $\cos(1)\approx 0.5403>0$, the factor $2x$ from the derivative of the inner function vanishes at $x=0$, making the tangent line horizontal at $(0,\sin 1)$.

## Quick verification

Let us verify using two independent observations:

1. **Even symmetry**: $f(-x)=\sin((-x)^2+1)=\sin(x^2+1)=f(x)$. Because $f$ is an even differentiable function, its graph is symmetric across the $y$-axis, so its slope at $x=0$ must be $f'(0)=0$. ✓
2. **Numerical difference quotient at $x=1$**:
   - Formula value: $f'(1)=2(1)\cos(1^2+1)=2\cos(2)\approx 2(-0.416147)=-0.832294$.
   - Difference quotient with $h=0.0001$:

$$\frac{\sin(1.0001^2+1)-\sin(2)}{0.0001}=\frac{\sin(2.00020001)-\sin(2)}{0.0001}\approx -0.83252 \approx f'(1).\quad\checkmark$$

## A concrete example

Compare $x=-0.5$, $x=0$, and $x=0.5$ (note that for $x\in[-0.5,0.5]$, the angle $x^2+1\in[1,1.25]$ radians lies in the first quadrant $(0,\frac{\pi}{2})$, so $\cos(x^2+1)>0$):

- At $x=-0.5$: $f'(-0.5)=-1\cdot\cos(1.25)\approx -0.3153<0$ (decreasing),
- At $x=0$: $f'(0)=0$ (horizontal tangent at the local minimum $y=\sin 1\approx 0.8415$),
- At $x=0.5$: $f'(0.5)=1\cdot\cos(1.25)\approx +0.3153>0$ (increasing).

## How I would explain this in class

> $\sin(x^2+1)$ is a composition: the outer function is $\sin u$ and the inner function is $u=x^2+1$. By the chain rule, we differentiate the outer sine to get $\cos(x^2+1)$, keeping the inside untouched, and multiply by the derivative of the inside, which is $2x$. That gives $f'(x)=2x\cos(x^2+1)$. At $x=0$, the factor $2x$ equals $0$, so $f'(0)=0$ and the tangent line is horizontal.

## Related workbook topics

- [Exercise 5: The Chain Rule as Working Through Layers](problem_05_solution.md)
- [Exercise 13: A Multi-Layer Composition](problem_13_solution.md)
