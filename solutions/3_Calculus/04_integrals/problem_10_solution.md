# Exercise 10. Definite Integral and Checking the Result

## The question

Before carrying out the exact calculation, estimate the possible range of values of the integral

$$\int_0^2(x^2+1)\,dx,$$

using

$$1\le x^2+1\le 5$$

on $[0,2]$. Only then compute the integral exactly, compare the result with the earlier estimate, and explain what type of computational error such a check can detect.

## Before calculating: what idea do we need?

If a continuous function $f(x)$ stays between a minimum value $m$ and a maximum value $M$ on the interval $[a,b]$, that is,

$$m\le f(x)\le M\qquad\text{for all }x\in[a,b],$$

then the area under the graph of $f(x)$ must lie between the area of the lower rectangle of height $m$ and the area of the upper rectangle of height $M$:

$$m(b-a)\le \int_a^b f(x)\,dx \le M(b-a).$$

This **bounding property** gives us a fast sanity check before we touch any antiderivatives.

## 1. Estimating the range of the integral before calculating

On the interval $[0,2]$ of length $b-a=2-0=2$, the function $f(x)=x^2+1$ is strictly increasing:
- Its minimum value is at $x=0$: $m=0^2+1=1$.
- Its maximum value is at $x=2$: $M=2^2+1=5$.

Integrating the inequality $1\le x^2+1\le 5$ over $[0,2]$ gives:

$$\int_0^2 1\,dx \le \int_0^2 (x^2+1)\,dx \le \int_0^2 5\,dx$$

$$1\cdot(2-0) \le \int_0^2 (x^2+1)\,dx \le 5\cdot(2-0)$$

$$2 \le \int_0^2 (x^2+1)\,dx \le 10.$$

So the exact value **must lie in the interval $[2,10]$**.

## 2. Computing the exact integral

An antiderivative of $x^2+1$ is $F(x)=\dfrac{x^3}{3}+x$. Using the Newton–Leibniz formula:

$$\int_0^2 (x^2+1)\,dx = \left[\frac{x^3}{3}+x\right]_0^2 = \left(\frac{2^3}{3}+2\right)-\left(0+0\right) = \frac{8}{3}+2 = \frac{14}{3}\approx 4.67.$$

## 3. Comparing with the estimate and explaining what errors it detects

Since $2 \le \dfrac{14}{3}\approx 4.67 \le 10$, our exact result sits comfortably inside the predicted range $[2,10]$.

**Errors this check can detect** (results that fall *outside* $[2,10]$):
- **Reversed limits / sign error:** $F(0)-F(2)=-\frac{14}{3}<2$.
- **Subtracting instead of adding:** $\left[\frac{x^3}{3}-x\right]_0^2=\frac{8}{3}-2=\frac{2}{3}<2$.
- **Multiplying by $3$ instead of dividing:** $\left[3x^3+x\right]_0^2=24+2=26>10$.

**Errors this check cannot detect** (wrong results that still lie *inside* $[2,10]$):
- **Differentiating instead of integrating:** $[2x]_0^2=4\in[2,10]$.
- **Forgetting to integrate the constant $1$:** $\left[\frac{x^3}{3}\right]_0^2=\frac{8}{3}\approx 2.67\in[2,10]$.
- **Arithmetic slip $2^3=6$:** $\frac{6}{3}+2=4\in[2,10]$.

So passing the bound check is only a **necessary condition**: a result outside $[2,10]$ is certainly wrong, but a result inside $[2,10]$ is not thereby verified as correct. The exact value $\frac{14}{3}$ is confirmed by the antiderivative calculation (and can be checked further, e.g. by differentiating $F$), not by the bound.

## Quick verification

We can obtain an even tighter geometric estimate by bounding the curve $y=x^2+1$ from above with the secant line connecting $(0,1)$ and $(2,5)$. Since $f(x)=x^2+1$ is convex ($f''(x)=2>0$), the area under the parabola is slightly less than the area of that trapezoid:

$$A_{\text{trapezoid}}=\frac{f(0)+f(2)}{2}\cdot(2-0)=\frac{1+5}{2}\cdot 2=6.$$

Indeed, $2 < \dfrac{14}{3}\approx 4.67 < 6 \le 10$. ✓

## A concrete example

Suppose a student subtracted instead of adding, getting $\frac{8}{3}-2=\frac{2}{3}\approx 0.67$. Because $0.67<2$, the lower rectangle bound $m(b-a)=1\cdot 2=2$ immediately flags that $\frac{2}{3}$ is impossible: a function that is always at least $1$ on an interval of width $2$ must accumulate an area of at least $2$. By contrast, a student who forgot to integrate the $+1$ term would get $\frac{8}{3}\approx 2.67$, which lies inside $[2,10]$ — the bound check would **not** catch that mistake.

## How I would explain this in class

> Before integrating $\int_0^2(x^2+1)\,dx$, I note that on $[0,2]$ the function stays between $1$ and $5$ over an interval of width $2$. So the area under the curve must be trapped between a rectangle of area $1\times 2=2$ and a rectangle of area $5\times 2=10$. Then I compute the exact integral $\left[\frac{x^3}{3}+x\right]_0^2 = \frac{8}{3}+2=\frac{14}{3}\approx 4.67$, which falls right inside $[2,10]$. This five-second rectangle check catches gross errors such as flipped signs or a factor of $3$ in the wrong place, but it is only a necessary test: wrong answers like $4$ or $\frac{8}{3}$ would also pass it.

## Related workbook topics

- [Exercise 9: Definite Integral and Geometric Area](problem_09_solution.md)
- [Exercise 13: An Integral Depending on the Upper Limit](problem_13_solution.md)
