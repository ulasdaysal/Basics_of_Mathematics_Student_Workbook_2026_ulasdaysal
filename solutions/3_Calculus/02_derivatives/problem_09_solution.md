# Exercise 9. A Logarithm and the Chain Rule

## The question

For

$$f(x)=\ln(x^2+1)$$

compute the derivative. Then determine the sign of $f'(x)$ for $x<0$, $x=0$, and $x>0$, and describe qualitatively how the function behaves around zero.

## Before calculating: what idea do we need?

First, notice that $x^2+1\ge1>0$ for every real number $x$, so the domain of $f(x)=\ln(x^2+1)$ is the entire real line $\mathbb{R}$.

Second, $f(x)=\ln(g(x))$ is a composition of the natural logarithm $\ln u$ (whose derivative is $\frac{1}{u}$) with the inner polynomial $u=g(x)=x^2+1$. By the **chain rule**:

$$\frac{d}{dx}\big(\ln(g(x))\big)=\frac{1}{g(x)}\cdot g'(x)=\frac{g'(x)}{g(x)}.$$

Finally, the sign of $f'(x)$ tells us the **monotonicity** of $f$:
- $f'(x)<0$ on an interval $\implies f$ is strictly decreasing there,
- $f'(x)=0$ $\implies$ horizontal tangent (stationary point),
- $f'(x)>0$ on an interval $\implies f$ is strictly increasing there.

## 1. Compute the derivative

Identify the layers of $f(x)=\ln(x^2+1)$:

- Outer function: $h(u)=\ln u \implies h'(u)=\dfrac{1}{u}$,
- Inner function: $u=g(x)=x^2+1 \implies g'(x)=2x$.

Multiply by the chain rule:

$$f'(x)=\frac{1}{x^2+1}\cdot 2x=\frac{2x}{x^2+1}.$$

## 2. Sign analysis of $f'(x)$

In the fraction $f'(x)=\dfrac{2x}{x^2+1}$, the denominator satisfies

$$x^2+1\ge1>0\quad\text{for all }x\in\mathbb{R}.$$

Because the denominator is always strictly positive, the sign of $f'(x)$ is determined entirely by the numerator $2x$:

- For $x<0$: $2x<0$, so $f'(x)<0$ (**negative**).
- For $x=0$: $2x=0$, so $f'(0)=0$ (**zero**).
- For $x>0$: $2x>0$, so $f'(x)>0$ (**positive**).

| Interval / Point | $x<0$ | $x=0$ | $x>0$ |
| :--- | :---: | :---: | :---: |
| Sign of $f'(x)$ | $-$ | $0$ | $+$ |
| Behavior of $f(x)$ | strictly decreasing $\searrow$ | local (and global) minimum | strictly increasing $\nearrow$ |

## 3. Qualitative behavior of $f(x)$ around zero

- As $x$ approaches $0$ from the left ($x<0$), $f'(x)<0$, so the graph slopes downward toward the origin.
- At $x=0$, $f(0)=\ln(0^2+1)=\ln 1=0$ and $f'(0)=0$. The graph touches the origin $(0,0)$ with a **horizontal tangent line** ($y=0$, the $x$-axis).
- As $x$ moves to the right of $0$ ($x>0$), $f'(x)>0$, so the graph turns upward and increases symmetrically ($f(-x)=f(x)$).
- Therefore, $f(x)$ has a **smooth U-shaped valley (global minimum)** at $(0,0)$.

## Quick verification

Let us check near $x=0$ using the standard approximation $\ln(1+u)\approx u$ for small $u$:

Setting $u=x^2$, for $x$ very close to $0$ we have:

$$f(x)=\ln(1+x^2)\approx x^2.$$

Near the origin, $f(x)=\ln(x^2+1)$ looks almost indistinguishable from the standard parabola $y=x^2$, whose derivative is $2x$ — which matches $\dfrac{2x}{x^2+1}\approx \dfrac{2x}{1}=2x$ when $x$ is small! ✓

## A concrete example

Evaluate $f(x)$ and $f'(x)$ at $x=-1$, $0$, and $1$:

- At $x=-1$: $f(-1)=\ln 2\approx 0.693$, and $f'(-1)=\dfrac{2(-1)}{(-1)^2+1}=-1<0$.
- At $x=0$: $f(0)=\ln 1=0$, and $f'(0)=0$.
- At $x=1$: $f(1)=\ln 2\approx 0.693$, and $f'(1)=\dfrac{2(1)}{1^2+1}=+1>0$.

The function drops from $\ln 2$ at $x=-1$ down to $0$ at $x=0$, and rises symmetrically back to $\ln 2$ at $x=1$.

## How I would explain this in class

> By the chain rule for logarithms, $(\ln g(x))'=\frac{g'(x)}{g(x)}$, so $f'(x)=\frac{2x}{x^2+1}$. Since the denominator $x^2+1$ is always positive, the sign of $f'(x)$ is the same as the sign of $2x$: negative for $x<0$, zero at $x=0$, and positive for $x>0$. This means the function decreases on $(-\infty,0)$, hits a minimum with a horizontal tangent at $(0,0)$, and increases on $(0,\infty)$.

## Related workbook topics

- [Exercise 4: A Quotient and Domain Control](problem_04_solution.md)
- [Exercise 5: The Chain Rule as Working Through Layers](problem_05_solution.md)
