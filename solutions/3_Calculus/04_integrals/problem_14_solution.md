# Exercise 14. A Piecewise-Defined Function

## The question

Let

$$f(x)=\begin{cases}x+1,&-1\le x<1,\\2,&1\le x\le 3.\end{cases}$$

Sketch the graph, decide where to split the integral, compute

$$\int_{-1}^{3}f(x)\,dx$$

and verify the result geometrically.

## Before calculating: what idea do we need?

When a function is defined by **different formulas on different subintervals**, there is no single algebraic formula for its antiderivative across the entire interval. Instead, we use the **interval additivity property** of the definite integral:

$$\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx,$$

splitting the integral at the boundary point $x=c$ where the rule of $f(x)$ changes.

## 1. Describing the graph and deciding where to split the integral

The definition of $f(x)$ changes at **$x=1$**, so we must split $[-1,3]$ at $x=1$ into $[-1,1]$ and $[1,3]$:

- **On $[-1,1]$:** $f(x)=x+1$ is a straight line with slope $1$, rising from the point $(-1,0)$ on the $x$-axis up to $(1,2)$.
- **On $[1,3]$:** $f(x)=2$ is a horizontal line segment at height $y=2$ from $(1,2)$ to $(3,2)$.

Notice that the two pieces meet continuously at $(1,2)$, forming a rising ramp followed by a flat plateau, all lying on or above the $x$-axis.

```
y
2 |         *---------*  y = 2
  |       / |         |
1 |     *   |         |
  |   /     |         |
0 +-*-------+---------+---> x
   -1       0    1    3
```

## 2. Computing the integral analytically by splitting at $x=1$

Using additivity at $x=1$:

$$\int_{-1}^{3}f(x)\,dx = \int_{-1}^{1}(x+1)\,dx + \int_{1}^{3}2\,dx.$$

We compute each piece separately:

1. **First piece on $[-1,1]$:**
   $$\int_{-1}^{1}(x+1)\,dx = \left[\frac{x^2}{2}+x\right]_{-1}^{1} = \left(\frac{1^2}{2}+1\right)-\left(\frac{(-1)^2}{2}+(-1)\right) = \frac{3}{2}-\left(-\frac{1}{2}\right) = 2.$$
2. **Second piece on $[1,3]$:**
   $$\int_{1}^{3}2\,dx = \Bigl[2x\Bigr]_{1}^{3} = 2(3)-2(1) = 6-2 = 4.$$

Adding the two contributions gives:

$$\int_{-1}^{3}f(x)\,dx = 2 + 4 = 6.$$

## 3. Geometric verification

Because $f(x)\ge 0$ on $[-1,3]$, the definite integral equals the geometric area under the graph, which decomposes into two basic shapes:

1. **On $[-1,1]$ (a right triangle):**
   The base has length $1-(-1)=2$ and the height at $x=1$ is $2$. Its area is:
   $$A_{\text{triangle}}=\frac{1}{2}\cdot\text{base}\cdot\text{height}=\frac{1}{2}\cdot 2\cdot 2 = 2.$$
2. **On $[1,3]$ (a rectangle):**
   The base has length $3-1=2$ and the constant height is $2$. Its area is:
   $$A_{\text{rectangle}}=\text{base}\cdot\text{height}=2\cdot 2 = 4.$$

Total geometric area:

$$A_{\text{total}} = A_{\text{triangle}} + A_{\text{rectangle}} = 2 + 4 = 6.$$

## Quick verification

We can also view the entire region under $y=f(x)$ on $[-1,3]$ as a single **right trapezoid** lying on its side (or with parallel horizontal bases of length $b_1=3-(-1)=4$ at the bottom $y=0$ and $b_2=3-1=2$ at the top $y=2$, and height $h=2$):

$$A_{\text{trapezoid}}=\frac{b_1+b_2}{2}\cdot h = \frac{4+2}{2}\cdot 2 = 6.$$

All three methods (analytical integration, triangle + rectangle, and single trapezoid) give $6$. ✓

## A concrete example

Note that in the definition of $f(x)$, the formula $x+1$ is given on $-1\le x<1$ with a strict inequality $<1$. Does a single boundary point affect the integral on $[-1,1]$? No: changing the value of a function at a single point changes the area under the curve by a line segment of width $0$ (area $0$). Here $f(x)$ is even continuous at $x=1$ since $\lim_{x\to 1^-}(x+1)=2=f(1)$.

## How I would explain this in class

> Because $f(x)$ changes its formula at $x=1$, I split the integral at $x=1$ into $\int_{-1}^1(x+1)\,dx + \int_1^3 2\,dx$. The first integral evaluates to $\frac{3}{2}-(-\frac{1}{2})=2$, and the second evaluates to $2(3-1)=4$, giving a total of $6$. Geometrically, the graph on $[-1,1]$ is a right triangle of base $2$ and height $2$ (area $2$), and on $[1,3]$ it is a $2\times 2$ square (area $4$), which immediately confirms $2+4=6$.

## Related workbook topics

- [Exercise 9: Definite Integral and Geometric Area](problem_09_solution.md)
- [Exercise 12: Symmetry, Sign, and Absolute Value](problem_12_solution.md)
