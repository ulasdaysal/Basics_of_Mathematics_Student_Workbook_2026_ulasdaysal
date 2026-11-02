# Exercise 6. Average Value of a Function

## The question

Compute the average value of the function

$$f(x)=x^2$$

on the interval $[0,3]$.

Find a point $c\in[0,3]$ for which $f(c)$ is equal to this average value, and interpret the result geometrically.

## Before calculating: what idea do we need?

To find the average of finitely many numbers, we add them up and divide by how many there are. For a continuous function $f(x)$ on an interval $[a,b]$, the definite integral $\int_a^b f(x)\,dx$ acts as the continuous sum of values, and the interval length $b-a$ acts as the count:

$$f_{\text{avg}} = \frac{1}{b-a}\int_a^b f(x)\,dx.$$

By the **Mean Value Theorem for Integrals**, a continuous function on $[a,b]$ always attains its average value at least once inside the interval: there exists $c\in[a,b]$ such that $f(c)=f_{\text{avg}}$.

## 1. Computing the average value on $[0,3]$

Applying the average value formula with $a=0$, $b=3$, and $f(x)=x^2$:

$$f_{\text{avg}} = \frac{1}{3-0}\int_0^3 x^2\,dx = \frac{1}{3}\left[\frac{x^3}{3}\right]_0^3.$$

Evaluating at the endpoints gives

$$f_{\text{avg}} = \frac{1}{3}\cdot\frac{27}{3} = \frac{9}{3} = 3.$$

## 2. Finding the point $c\in[0,3]$ where $f(c)=f_{\text{avg}}$

We look for $c\in[0,3]$ such that

$$f(c)=3 \iff c^2=3 \implies c=\pm\sqrt{3}.$$

Since $c$ must belong to the interval $[0,3]$, we select the positive root:

$$c=\sqrt{3}\approx 1.732.$$

## 3. Geometric interpretation (equal-area rectangle)

Rewriting the average value equation as

$$\int_0^3 x^2\,dx = f(c)\cdot(3-0) = 3\cdot 3 = 9$$

reveals its geometric meaning:
- The curved region under the parabola $y=x^2$ over $[0,3]$ has area $9$.
- A rectangle with the same base $[0,3]$ (width $3$) and constant height $y=f_{\text{avg}}=3$ (attained by the graph at $x=c=\sqrt{3}$) also has area $3\times 3=9$.

If the area under $y=x^2$ were made of water and allowed to settle into a flat horizontal level over $[0,3]$, the water depth would stabilize at $y=3$.

## 4. Why $c=\sqrt{3}$ is greater than the midpoint $1.5$

Notice that the average of the endpoint values is $\frac{f(0)+f(3)}{2}=\frac{0+9}{2}=4.5$, whereas the true integral average is $3$. Because $f(x)=x^2$ is convex (concave up), it stays below the secant line connecting $(0,0)$ and $(3,9)$, pulling the true average down to $3$ and shifting $c=\sqrt{3}\approx 1.732$ to the right of the interval's midpoint $1.5$.

## Quick verification

Let us verify the balance of areas above and below the horizontal line $y=3$:

- From $x=0$ to $x=\sqrt{3}$, the line $y=3$ lies above $y=x^2$. The "missing" area under the line is
  $$\int_0^{\sqrt{3}} (3-x^2)\,dx = \left[3x-\frac{x^3}{3}\right]_0^{\sqrt{3}} = 3\sqrt{3}-\sqrt{3} = 2\sqrt{3}.$$
- From $x=\sqrt{3}$ to $x=3$, the parabola $y=x^2$ rises above $y=3$. The "excess" area above the line is
  $$\int_{\sqrt{3}}^3 (x^2-3)\,dx = \left[\frac{x^3}{3}-3x\right]_{\sqrt{3}}^3 = (9-9) - (\sqrt{3}-3\sqrt{3}) = 2\sqrt{3}.$$

The excess peak on $[\sqrt{3},3]$ fills the deficit on $[0,\sqrt{3}]$ with exact area $2\sqrt{3}$. ✓

## A concrete example

Imagine a square plate whose local mass density varies along its length $x\in[0,3]\text{ m}$ as $\rho(x)=x^2\text{ kg/m}$. The total mass of the $3\text{ m}$ rod is $\int_0^3 x^2\,dx = 9\text{ kg}$. Replacing this non-uniform rod with a uniform $3\text{ m}$ rod of the same total mass requires a constant linear density of $\rho_{\text{avg}}=9/3=3\text{ kg/m}$, which matches the original rod's density at the exact cross-section $x=\sqrt{3}\text{ m}$.

## How I would explain this in class

> To average $f(x)=x^2$ on $[0,3]$, we divide the area under the graph by the interval width: $\frac{1}{3-0}\int_0^3 x^2\,dx = \frac{1}{3}\cdot 9 = 3$. Setting $f(c)=c^2=3$ on $[0,3]$ gives $c=\sqrt{3}\approx 1.732$. Geometrically, a rectangle of width $3$ and height $f(\sqrt{3})=3$ has area $9$, which is identical to the area under the parabola $y=x^2$ on $[0,3]$—the curved peak above $y=3$ on $[\sqrt{3},3]$ exactly fills the gap below $y=3$ on $[0,\sqrt{3}]$.

## Related workbook topics

- [Exercise 4: Area Between Curves](problem_04_solution.md)
- [Exercise 8: Number of Requests Handled by a Server](problem_08_solution.md)
