# Exercise 13. An Integral Depending on the Upper Limit

## The question

Let

$$F(x)=\int_0^x(t^2+1)\,dt.$$

Determine $F(x)$, compute $F'(x)$, and compare the result with the integrand. Explain in your own words why the height of the function describes the local rate of increase of the accumulated area.

## Before calculating: what idea do we need?

When we replace the upper limit of a definite integral by a variable $x$, the integral

$$F(x)=\int_a^x f(t)\,dt$$

becomes an **area accumulation function**: it measures the signed area accumulated under the graph of $f(t)$ from the starting point $t=a$ up to $t=x$. (We use the dummy variable $t$ inside the integral so we do not confuse it with the upper limit $x$.)

The **First Fundamental Theorem of Calculus** states that differentiating the accumulated area with respect to the right endpoint $x$ simply gives back the height of the curve at $x$:

$$F'(x)=\frac{d}{dx}\int_a^x f(t)\,dt = f(x).$$

## 1. Determining the explicit formula for $F(x)$

First we find an antiderivative of the integrand $f(t)=t^2+1$ with respect to $t$:

$$\int (t^2+1)\,dt = \frac{t^3}{3}+t+C.$$

Evaluating from the lower limit $t=0$ to the upper limit $t=x$:

$$F(x)=\left[\frac{t^3}{3}+t\right]_{t=0}^{t=x} = \left(\frac{x^3}{3}+x\right)-\left(\frac{0^3}{3}+0\right) = \frac{x^3}{3}+x.$$

## 2. Computing $F'(x)$ and comparing with the integrand

Now we differentiate $F(x)=\dfrac{x^3}{3}+x$ with respect to $x$:

$$F'(x)=\frac{d}{dx}\left(\frac{x^3}{3}+x\right) = \frac{3x^2}{3}+1 = x^2+1.$$

**Comparison:** $F'(x)=x^2+1$ is the **exact integrand** $f(t)=t^2+1$ evaluated at the upper limit $t=x$.

## 3. Why the height of the function is the rate of increase of accumulated area

Imagine moving the right boundary $x$ slightly to the right by a tiny width $\Delta x$:
- The newly added slice of area is $\Delta F = F(x+\Delta x)-F(x) = \int_x^{x+\Delta x} f(t)\,dt$.
- When $\Delta x$ is very small, the curve $y=f(t)$ barely changes height over $[x,x+\Delta x]$, so this thin vertical strip is almost a **rectangle** of width $\Delta x$ and height $f(x)$:
  $$\Delta F \approx \text{height}\times\text{width} = f(x)\cdot\Delta x.$$
- Dividing both sides by the width $\Delta x$ gives the average rate of change of area per unit width:
  $$\frac{\Delta F}{\Delta x} \approx f(x).$$

In the limit as $\Delta x\to 0$, the instantaneous rate at which accumulated area grows, $F'(x)$, is literally the height $f(x)$ of the boundary strip being swept out at $x$.

## Quick verification

Let us check that $F(x)=\dfrac{x^3}{3}+x$ agrees with our earlier calculation in Problem 10:
- At $x=0$: $F(0)=\int_0^0(t^2+1)\,dt=0$, and $\frac{0^3}{3}+0=0$. ✓
- At $x=2$: $F(2)=\int_0^2(t^2+1)\,dt=\frac{2^3}{3}+2=\frac{14}{3}$, which matches Problem 10. ✓
- Differentiating $F(x)$ gives $F'(x)=x^2+1=f(x)$. ✓

## A concrete example

Compare the rate of area growth at two different positions:
- At $x=1$, the height of the curve is $f(1)=1^2+1=2$. If we push the boundary from $x=1$ to $x=1.01$ ($\Delta x=0.01$), the area increases by approximately $f(1)\Delta x = 2(0.01)=0.02$. (The exact increase is $F(1.01)-F(1)\approx 0.0201003$.)
- At $x=3$, the curve is much taller: $f(3)=3^2+1=10$. Pushing the boundary by the same $\Delta x=0.01$ from $x=3$ to $x=3.01$ adds approximately $10(0.01)=0.10$ of area—five times as much, because the vertical strip at $x=3$ is five times as tall!

## How I would explain this in class

> Integrating $t^2+1$ from $0$ to $x$ gives the accumulation function $F(x)=\frac{x^3}{3}+x$. When we differentiate $F(x)$, we get $F'(x)=x^2+1$, which is just the integrand with $t$ replaced by $x$. Geometrically, if you slide the right wall at $x$ outward by a tiny step $\Delta x$, the extra sliver of area you sweep out is a thin rectangle of width $\Delta x$ and height $f(x)$. Dividing the new area $f(x)\Delta x$ by $\Delta x$ leaves the height $f(x)$ as the instantaneous rate of area growth.

## Related workbook topics

- [Exercise 1: Antiderivative and Verification](problem_01_solution.md)
- [Exercise 10: Definite Integral and Checking the Result](problem_10_solution.md)
