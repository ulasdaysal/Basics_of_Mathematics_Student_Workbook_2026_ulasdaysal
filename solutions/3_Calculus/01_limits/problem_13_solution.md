# Exercise 13. Fundamental Trigonometric Limit

## The question

Using

$$\lim_{x\to0}\frac{\sin x}{x}=1,$$

compute

$$\lim_{x\to0}\frac{\sin5x}{x},\qquad \lim_{x\to0}\frac{\sin2x}{\sin3x}.$$

In each case, show how you reduce the expression to the fundamental limit.

## Before calculating: what idea do we need?

The fundamental trigonometric limit tells us that for any nonzero expression $u(x)$ that approaches $0$,

$$\lim_{u\to0}\frac{\sin u}{u} = 1\qquad\text{and equivalently}\qquad \lim_{u\to0}\frac{u}{\sin u} = 1.$$

Wait: we **cannot** pull constants out of $\sin(kx)$ as if sine were multiplication ($\sin 5x \neq 5\sin x$)! Instead, since we cannot change the argument $kx$ inside the sine, we **adjust the denominator** by multiplying and dividing by $k$ so that the denominator matches the exact angle inside $\sin(\,\cdot\,)$.

## 1. First limit: $\lim_{x\to0}\dfrac{\sin 5x}{x}$

The angle inside the sine is $5x$, so we want $5x$ in the denominator. Multiplying numerator and denominator by $5$:

$$\frac{\sin 5x}{x} = 5\cdot\frac{\sin 5x}{5x}.$$

Let $u=5x$. As $x\to0$, we also have $u\to0$, so $\lim_{x\to0}\dfrac{\sin 5x}{5x} = \lim_{u\to0}\dfrac{\sin u}{u} = 1$. Therefore:

$$\lim_{x\to0}\frac{\sin 5x}{x} = 5\cdot\lim_{x\to0}\frac{\sin 5x}{5x} = 5\cdot 1 = 5.$$

## 2. Second limit: setting up the reduction for $\lim_{x\to0}\dfrac{\sin 2x}{\sin 3x}$

Here we have two sine expressions, $\sin 2x$ and $\sin 3x$. To pair each sine with its matching angle, we multiply and divide by $2x$ and $3x$:

$$\frac{\sin 2x}{\sin 3x} = \frac{\sin 2x}{2x}\cdot\frac{3x}{\sin 3x}\cdot\frac{2x}{3x} = \frac{2}{3}\cdot\frac{\sin 2x}{2x}\cdot\frac{3x}{\sin 3x}.$$

## 3. Evaluating the second limit

As $x\to0$, both $2x\to0$ and $3x\to0$. Using the fundamental trigonometric limit on each factor:

$$\lim_{x\to0}\frac{\sin 2x}{2x} = 1,\qquad \lim_{x\to0}\frac{3x}{\sin 3x} = \frac{1}{\lim_{x\to0}\dfrac{\sin 3x}{3x}} = \frac{1}{1} = 1.$$

Multiplying the limits of the factors together gives:

$$\lim_{x\to0}\frac{\sin 2x}{\sin 3x} = \frac{2}{3}\cdot 1\cdot 1 = \frac{2}{3}.$$

## 4. Geometric meaning of the reduction

Why does $\lim_{u\to0}\dfrac{\sin u}{u}=1$ hold in the first place (when $u$ is measured in radians)? Because near $u=0$, the graph of $y=\sin u$ is tangent to the line $y=u$, so for tiny angles **$\sin u \approx u$**.

- Replacing $\sin 5x \approx 5x$ immediately suggests $\dfrac{\sin 5x}{x}\approx \dfrac{5x}{x}=5$.
- Replacing $\sin 2x \approx 2x$ and $\sin 3x \approx 3x$ suggests $\dfrac{\sin 2x}{\sin 3x}\approx \dfrac{2x}{3x}=\dfrac{2}{3}$.

Multiplying and dividing by $5x$, $2x$, and $3x$ is simply the algebraic way to make the approximation $\sin u\approx u$ into a rigorous proof.

## Quick verification

Alternatively, divide both numerator and denominator of $\dfrac{\sin 2x}{\sin 3x}$ by $x$:

$$\lim_{x\to0}\frac{\sin 2x}{\sin 3x} = \lim_{x\to0}\frac{\dfrac{\sin 2x}{x}}{\dfrac{\sin 3x}{x}} = \frac{\lim_{x\to0}2\dfrac{\sin 2x}{2x}}{\lim_{x\to0}3\dfrac{\sin 3x}{3x}} = \frac{2\cdot 1}{3\cdot 1} = \frac{2}{3}. \quad \checkmark$$

## A concrete example

Let us test both expressions for a small angle $x=0.01$ radians:

- First expression: $\dfrac{\sin(0.05)}{0.01} \approx \dfrac{0.049979}{0.01} \approx 4.9979$ (very close to $5$).
- Second expression: $\dfrac{\sin(0.02)}{\sin(0.03)} \approx \dfrac{0.0199987}{0.0299955} \approx 0.66672$ (very close to $\dfrac{2}{3}\approx 0.66667$).

## How I would explain this in class

> The rule $\lim_{u\to0}\dfrac{\sin u}{u}=1$ works whenever the denominator matches the exact argument inside $\sin u$. Since you can never pull the $5$ out of $\sin 5x$, you instead create a $5x$ on the bottom: $\dfrac{\sin 5x}{x} = 5\cdot\dfrac{\sin 5x}{5x}\to 5\cdot 1=5$. For $\dfrac{\sin 2x}{\sin 3x}$, you give $\sin 2x$ a $2x$ and $\sin 3x$ a $3x$, leaving $\dfrac{2x}{3x}=\dfrac{2}{3}$.

## Related workbook topics

- [Exercise 12: Exponential function limit](problem_12_solution.md)
- [Exercise 14: A 0/0 limit with trigonometry](problem_14_solution.md)
