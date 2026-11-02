# Exercise 4. Area Between Curves

## The question

Find the area of the region bounded by the graphs

$$y=x \quad\text{and}\quad y=x^2.$$

First find the intersection points and justify which function is greater on the relevant interval.

## Before calculating: what idea do we need?

The area of a planar region bounded vertically between two continuous curves $y=f(x)$ and $y=g(x)$ on an interval $[a,b]$ is obtained by integrating the vertical height of the region:

$$\text{Area}=\int_a^b \bigl(y_{\text{upper}}(x)-y_{\text{lower}}(x)\bigr)\,dx.$$

Before setting up the integral, we must:
1. Solve $f(x)=g(x)$ to find the horizontal limits of integration $a$ and $b$.
2. Determine which curve lies on top ($y_{\text{upper}}\ge y_{\text{lower}}$) on $[a,b]$ so that the integrand represents a non-negative height.

## 1. Finding the intersection points

We set the two formulas equal to each other:

$$x^2=x \iff x^2-x=0 \iff x(x-1)=0.$$

Thus, the graphs intersect at

$$x_1=0 \quad\text{and}\quad x_2=1,$$

which correspond to the points $(0,0)$ and $(1,1)$ in the plane. The bounded region therefore spans the interval $[0,1]$.

## 2. Determining which function is greater on $[0,1]$

On the open interval $(0,1)$, we have $0<x<1$. Multiplying the inequality $x<1$ by the positive number $x$ gives

$$x^2 < x \qquad\text{for all } x\in(0,1).$$

Equivalently, $x-x^2=x(1-x)>0$ on $(0,1)$ because both factors $x$ and $1-x$ are positive. Hence, the line $y=x$ is the **upper curve** and the parabola $y=x^2$ is the **lower curve** on $[0,1]$.

## 3. Setting up and computing the area integral

Integrating the vertical slice height $(x-x^2)$ from $x=0$ to $x=1$ gives

$$\text{Area}=\int_0^1 (x-x^2)\,dx.$$

Using the Fundamental Theorem of Calculus:

$$\text{Area}=\left[\frac{x^2}{2}-\frac{x^3}{3}\right]_0^1=\left(\frac{1}{2}-\frac{1}{3}\right)-(0-0)=\frac{1}{6}.$$

## 4. Geometric decomposition of the result

We can interpret the integral $\int_0^1 x\,dx - \int_0^1 x^2\,dx = \frac{1}{2}-\frac{1}{3}=\frac{1}{6}$ directly:
- The region under the line $y=x$ on $[0,1]$ is a right triangle of base $1$ and height $1$, whose area is $\frac{1}{2}$.
- The region under the parabola $y=x^2$ on $[0,1]$ has area $\frac{1}{3}$ (a classic result known since Archimedes).
- Removing the parabolic region from the right triangle leaves the lens-shaped region of area $\frac{1}{2}-\frac{1}{3}=\frac{1}{6}$.

## Quick verification

Let us verify the inequality and the magnitude of the area:

- Midpoint check at $x=\frac{1}{2}$: the line height is $y=\frac{1}{2}=0.5$, while the parabola height is $y=\bigl(\frac{1}{2}\bigr)^2=0.25<0.5$, confirming $x>x^2$ on $(0,1)$. ✓
- Bounding box check: the entire region fits inside the right triangle of area $\frac{1}{2}$, and its maximum vertical thickness (attained at $x=\frac{1}{2}$) is $\frac{1}{4}$. Thus $0<\text{Area}<\frac{1}{2}$, and $\frac{1}{6}\approx 0.1667$ fits this bound cleanly. ✓

## A concrete example

If we forgot to check which curve was on top and mistakenly integrated $\int_0^1 (x^2-x)\,dx$, we would get $-\frac{1}{6}$, which is negative and cannot be a geometric area. Even worse, if two curves cross inside an interval—for instance $y=x$ and $y=x^3$ on $[-1,1]$, which cross at $x=-1,0,1$—integrating $\int_{-1}^1 (x-x^3)\,dx=0$ cancels the two lobes completely! Checking intersections and ordering first prevents signed cancellation.

## How I would explain this in class

> First we find where the curves meet by solving $x=x^2$, which gives $x=0$ and $x=1$. Between $0$ and $1$, squaring a fraction makes it smaller, so the line $y=x$ lies above the parabola $y=x^2$. We integrate top minus bottom: $\int_0^1 (x-x^2)\,dx = \bigl[\frac{x^2}{2}-\frac{x^3}{3}\bigr]_0^1 = \frac{1}{2}-\frac{1}{3} = \frac{1}{6}$.

## Related workbook topics

- [Exercise 6: Average Value of a Function](problem_06_solution.md)
- [Exercise 11: Volume of a Solid of Revolution](problem_11_solution.md)
