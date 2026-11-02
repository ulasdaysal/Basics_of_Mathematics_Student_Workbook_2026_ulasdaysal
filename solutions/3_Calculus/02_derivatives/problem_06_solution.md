# Exercise 6. Product Rule and Trigonometry

## The question

For

$$f(x)=x\sin x+\cos x$$

compute the derivative and simplify the result. Then compute $f'(0)$ and interpret the direction of the tangent line at that point.

## Before calculating: what idea do we need?

First, inspect the overall structure of $f(x)=x\sin x+\cos x$:
- It is a **sum** of two terms: $x\sin x$ and $\cos x$.
- The first term $x\sin x$ is a **product** of two functions of $x$, namely $u(x)=x$ and $v(x)=\sin x$, so it requires the **product rule** $(uv)'=u'v+uv'$.
- We also need the basic trigonometric derivatives:

$$\frac{d}{dx}(\sin x)=\cos x,\qquad \frac{d}{dx}(\cos x)=-\sin x.$$

## 1. Differentiate the product term $x\sin x$

Apply the product rule to $x\sin x$ with $u(x)=x$ and $v(x)=\sin x$:

- $u'(x)=1$,
- $v'(x)=\cos x$.

Therefore,

$$\frac{d}{dx}(x\sin x)=1\cdot\sin x+x\cdot\cos x=\sin x+x\cos x.$$

## 2. Differentiate the second term and simplify $f'(x)$

The derivative of $\cos x$ is $-\sin x$. Adding the two parts together:

$$f'(x)=(\sin x+x\cos x)+(-\sin x)=x\cos x.$$

Notice the neat cancellation: the $+\sin x$ from the product rule and the $-\sin x$ from differentiating $\cos x$ cancel out completely, leaving the compact expression $f'(x)=x\cos x$.

## 3. Compute $f'(0)$ and interpret the tangent line

Substitute $x=0$ into $f'(x)=x\cos x$:

$$f'(0)=0\cdot\cos 0=0\cdot 1=0.$$

What does $f'(0)=0$ mean geometrically?
- At $x=0$, the point on the graph is $(0,f(0))=(0,0\cdot\sin 0+\cos 0)=(0,1)$.
- Since the slope is $f'(0)=0$, the **tangent line to the graph at $(0,1)$ is horizontal** (parallel to the $x$-axis), with equation $y=1$.

## Quick verification

Let us check the behavior of $f(x)=x\sin x+\cos x$ near $x=0$:

1. **Symmetry check**: $f(-x)=(-x)\sin(-x)+\cos(-x)=x\sin x+\cos x=f(x)$. Every differentiable **even function** is symmetric across the $y$-axis and therefore must have $f'(0)=0$. ✓
2. **Small-$x$ approximation**: near $x=0$, $\sin x\approx x$ and $\cos x\approx 1-\frac{1}{2}x^2$, so

$$f(x)\approx x(x)+\left(1-\frac{1}{2}x^2\right)=1+\frac{1}{2}x^2.$$

The linear term in $x$ is $0\cdot x$, confirming $f'(0)=0$, and the parabola $1+\frac{1}{2}x^2$ has a horizontal tangent and local minimum at $(0,1)$. ✓

## A concrete example

At $x=\dfrac{\pi}{3}$:

$$f'\left(\frac{\pi}{3}\right)=\frac{\pi}{3}\cos\frac{\pi}{3}=\frac{\pi}{6}\approx 0.5236>0,$$

 while at $x=-\dfrac{\pi}{3}$:

$$f'\left(-\frac{\pi}{3}\right)=-\frac{\pi}{3}\cos\left(-\frac{\pi}{3}\right)=-\frac{\pi}{6}\approx -0.5236<0.$$

As $x$ passes through $0$ from negative to positive values, $f'(x)=x\cos x$ changes sign from negative to positive, so $(0,1)$ is a local minimum where the curve levels off horizontally.

## How I would explain this in class

> To differentiate $f(x)=x\sin x+\cos x$, we use the product rule on $x\sin x$ to get $\sin x+x\cos x$, and then add the derivative of $\cos x$, which is $-\sin x$. The $\sin x$ and $-\sin x$ terms cancel out, leaving $f'(x)=x\cos x$. At $x=0$, $f'(0)=0\cdot\cos 0=0$, which tells us that the tangent line at $(0,1)$ is completely horizontal.

## Related workbook topics

- [Exercise 3: The Product Rule — Why Is It Needed?](problem_03_solution.md)
- [Exercise 7: A Trigonometric Composition](problem_07_solution.md)
