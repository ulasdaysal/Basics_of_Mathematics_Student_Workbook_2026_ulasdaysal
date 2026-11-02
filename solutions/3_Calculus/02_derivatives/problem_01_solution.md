# Exercise 1. Derivative of a Polynomial and the Slope of a Tangent Line

## The question

For

$$f(x)=3x^5-2x^3+7x-4$$

find $f'(x)$. Then compute $f'(0)$ and $f'(1)$, determine the signs of the obtained values, and explain what they say about the slope of the tangent line to the graph at these two points.

## Before calculating: what idea do we need?

A polynomial is a linear combination of power functions $x^n$. To differentiate it, we combine two basic rules:

- **Linearity (sum and constant multiple rule)**: $(af(x)+bg(x))' = af'(x)+bg'(x)$, so we differentiate term by term.
- **Power rule**: $\dfrac{d}{dx}(x^n) = nx^{n-1}$ for any integer $n\ge1$, and the derivative of a constant is $0$.

Geometrically, the value $f'(a)$ is the **slope of the tangent line** to the graph $y=f(x)$ at $x=a$:
- $f'(a)>0$: the tangent line slopes upward from left to right, and the function is locally increasing,
- $f'(a)<0$: the tangent line slopes downward, and the function is locally decreasing,
- $f'(a)=0$: the tangent line is horizontal.

## 1. Differentiate term by term

Apply the power rule to each term of $f(x)=3x^5-2x^3+7x-4$:

- $\dfrac{d}{dx}(3x^5) = 3\cdot5x^{5-1} = 15x^4$,
- $\dfrac{d}{dx}(-2x^3) = -2\cdot3x^{3-1} = -6x^2$,
- $\dfrac{d}{dx}(7x) = 7\cdot1x^{1-1} = 7$,
- $\dfrac{d}{dx}(-4) = 0$.

Putting the terms together gives the derivative formula:

$$f'(x)=15x^4-6x^2+7.$$

## 2. Compute $f'(0)$ and $f'(1)$

Substitute $x=0$ into $f'(x)$:

$$f'(0)=15(0)^4-6(0)^2+7=0-0+7=7.$$

Substitute $x=1$ into $f'(x)$:

$$f'(1)=15(1)^4-6(1)^2+7=15-6+7=16.$$

## 3. Signs and geometric interpretation

- At $x=0$, we have $f'(0)=7>0$. The tangent line to the graph at $(0,-4)$ has a **positive slope of $7$**, meaning it rises $7$ units vertically for each $1$ unit horizontally. Near $x=0$, only the linear part $7x-4$ dominates because higher powers of $x$ vanish much faster than $x$.
- At $x=1$, we have $f'(1)=16>0$. The tangent line at $(1,4)$ also has a **positive slope**, and because $16>7$, the graph is rising **more than twice as steeply** at $x=1$ as it is at $x=0$.

## 4. Global behavior notice

Notice that we can complete the square in $f'(x)$:

$$f'(x)=15\left(x^2-\frac{1}{5}\right)^2+\frac{32}{5}\ge\frac{32}{5}>0\quad\text{for all }x\in\mathbb{R}.$$

So in fact every tangent line to this polynomial has positive slope, and $f(x)$ is strictly increasing on the entire real line.

## Quick verification

Near $x=0$, a polynomial behaves like its constant and linear terms:

$$f(x)=-4+7x-2x^3+3x^5 \approx -4+7x\quad\text{for }x\text{ close to }0.$$

The linear approximation at $x=0$ is $L_0(x)=-4+7x$, whose slope is $7=f'(0)$. ✓

Similarly, using a small step $h=0.001$ at $x=1$:

$$\frac{f(1.001)-f(1)}{0.001}=\frac{4.016024027003-4}{0.001}\approx 16.024 \approx 16 = f'(1).\quad\checkmark$$

## A concrete example

At $x=0$, the point on the curve is $(0,f(0))=(0,-4)$ and the tangent line has equation

$$y = -4 + 7x.$$

At $x=1$, the point on the curve is $(1,f(1))=(1,4)$ and the tangent line has equation

$$y = 4 + 16(x-1) = 16x-12.$$

If we move slightly from $x=1$ to $x=1.01$, the tangent line predicts $y\approx 4 + 16(0.01) = 4.16$, while the exact value is $f(1.01)\approx 4.1624$.

## How I would explain this in class

> To differentiate a polynomial, we apply the power rule $\frac{d}{dx}(x^n)=nx^{n-1}$ term by term and drop the constant $-4$. That gives $f'(x)=15x^4-6x^2+7$. Plugging in $x=0$ gives $7>0$ and plugging in $x=1$ gives $16>0$. Both values are positive, so the graph is rising at both points, and since $16>7$, the tangent line at $x=1$ is much steeper than at $x=0$.

## Related workbook topics

- [Exercise 2: Powers, Roots, and the Domain](problem_02_solution.md)
- [Exercise 10: The Tangent Line as an Application of the Derivative](problem_10_solution.md)
