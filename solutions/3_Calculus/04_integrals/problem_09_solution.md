# Exercise 9. Definite Integral and Geometric Area

## The question

Compute

$$\int_{-1}^{2}x\,dx.$$

Then separately compute the areas of the parts of the graph below and above the $x$-axis and explain the difference between the definite integral and geometric area.

## Before calculating: what idea do we need?

By the **Fundamental Theorem of Calculus (Newton–Leibniz formula)**, if $F(x)$ is any antiderivative of a continuous function $f(x)$, then:

$$\int_a^b f(x)\,dx = \Bigl[F(x)\Bigr]_a^b = F(b)-F(a).$$

However, a **definite integral is not always equal to geometric area**:
- The **definite integral** computes **signed (net) area**: regions where $f(x)>0$ (above the $x$-axis) contribute with a **$+$ sign**, while regions where $f(x)<0$ (below the $x$-axis) contribute with a **$-$ sign**.
- The **geometric area** between the graph and the $x$-axis counts every region as **positive**, regardless of whether it lies above or below the $x$-axis: $\text{Area}=\int_a^b |f(x)|\,dx$.

## 1. Computing the definite integral

An antiderivative of $f(x)=x$ is $F(x)=\dfrac{x^2}{2}$. Applying the Newton–Leibniz formula from $x=-1$ to $x=2$:

$$\int_{-1}^{2}x\,dx = \left[\frac{x^2}{2}\right]_{-1}^{2} = \frac{2^2}{2}-\frac{(-1)^2}{2} = \frac{4}{2}-\frac{1}{2} = 2-\frac{1}{2}=\frac{3}{2}=1.5.$$

## 2. Computing the geometric areas below and above the $x$-axis

The line $y=x$ crosses the $x$-axis at $x=0$, splitting $[-1,2]$ into two right triangles:

1. **Part below the $x$-axis on $[-1,0]$:**
   Here $x\le 0$. The region between $y=x$ and the $x$-axis is a right triangle with base $1$ (from $-1$ to $0$) and height $1$ (since $|{-1}|=1$). Its geometric area is:
   $$A_{\text{below}}=\frac{1}{2}\cdot\text{base}\cdot\text{height}=\frac{1}{2}\cdot 1\cdot 1=\frac{1}{2}=0.5,$$
   or by integration: $A_{\text{below}}=\int_{-1}^{0}(-x)\,dx=\left[-\frac{x^2}{2}\right]_{-1}^{0}=0-\left(-\frac{1}{2}\right)=\frac{1}{2}$.

2. **Part above the $x$-axis on $[0,2]$:**
   Here $x\ge 0$. The region is a right triangle with base $2$ (from $0$ to $2$) and height $2$. Its geometric area is:
   $$A_{\text{above}}=\frac{1}{2}\cdot\text{base}\cdot\text{height}=\frac{1}{2}\cdot 2\cdot 2=2,$$
   or by integration: $A_{\text{above}}=\int_{0}^{2}x\,dx=\left[\frac{x^2}{2}\right]_{0}^{2}=2-0=2$.

## 3. Comparing the definite integral and the total geometric area

- **Definite integral (net signed area):**
  $$\int_{-1}^{2}x\,dx = A_{\text{above}} - A_{\text{below}} = 2 - \frac{1}{2} = \frac{3}{2}=1.5.$$
- **Total geometric area:**
  $$A_{\text{total}} = A_{\text{above}} + A_{\text{below}} = 2 + \frac{1}{2} = \frac{5}{2}=2.5.$$

The definite integral subtracts the area below the axis from the area above the axis, whereas geometric area adds both positive magnitudes together.

## Quick verification

We split the definite integral at the zero crossing $x=0$ using additivity of the integral:

$$\int_{-1}^{2}x\,dx = \int_{-1}^{0}x\,dx + \int_{0}^{2}x\,dx = \left(-\frac{1}{2}\right) + 2 = \frac{3}{2}.$$

Both the direct antiderivative calculation and the geometric triangle subtraction give $\dfrac{3}{2}$. ✓

## A concrete example

Think of $f(t)=t$ as the **velocity** (in m/s) of an object moving along a line from $t=-1\text{ s}$ to $t=2\text{ s}$:
- Between $t=-1$ and $t=0$, velocity is negative, so the object moves **backward** by $0.5\text{ m}$.
- Between $t=0$ and $t=2$, velocity is positive, so the object moves **forward** by $2\text{ m}$.
- The **definite integral** $\int_{-1}^2 t\,dt = 2-0.5=1.5\text{ m}$ gives the **net displacement** from start to finish, while the **geometric area** $2+0.5=2.5\text{ m}$ gives the **total distance traveled**.

## How I would explain this in class

> Evaluating $\int_{-1}^2 x\,dx$ with the antiderivative $\frac{x^2}{2}$ gives $\frac{4}{2}-\frac{1}{2}=\frac{3}{2}$. Geometrically, the graph of $y=x$ forms a small triangle of area $\frac{1}{2}$ below the $x$-axis on $[-1,0]$ and a larger triangle of area $2$ above the $x$-axis on $[0,2]$. The definite integral equals $2-\frac{1}{2}=\frac{3}{2}$ because it treats area below the $x$-axis as negative (signed accumulation), whereas the total geometric area is $2+\frac{1}{2}=\frac{5}{2}$.

## Related workbook topics

- [Exercise 12: Symmetry, Sign, and Absolute Value](problem_12_solution.md)
- [Exercise 14: A Piecewise-Defined Function](problem_14_solution.md)
