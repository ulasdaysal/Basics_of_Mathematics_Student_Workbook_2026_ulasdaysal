# Exercise 15. Complete Classification of a Line Relative to a Plane

## The question

Let

$$L:p+tv,\qquad \Pi:n\cdot x=d.$$

State the conditions distinguishing the three cases: one intersection point, parallel with no common points, and the line contained in the plane. Then illustrate each case with your own simple numerical example.

## Before calculating: what idea do we need?

Every point on the line $L$ has the form $x=p+tv$ for $t\in\mathbb{R}$. Substituting $x=p+tv$ into the plane equation $n\cdot x=d$ and using the linearity of the dot product gives a single linear equation for the parameter $t$:

$$n\cdot(p+tv)=d\iff n\cdot p+t(n\cdot v)=d\iff (n\cdot v)\,t=d-n\cdot p.$$

Everything depends on two numbers:
- the **slope coefficient** $n\cdot v$ (whether the line's direction tilts across the plane or runs parallel to it), and
- the **right-hand side** $d-n\cdot p$ (whether the starting point $p$ already lies on the plane).

## 1. Complete classification of the three cases

For the linear equation $(n\cdot v)\,t=d-n\cdot p$ in the single real variable $t$:

### Case 1: One intersection point
- **Condition:** $n\cdot v\neq 0$.
- **Explanation:** Because $n\cdot v\neq 0$, we can divide by $n\cdot v$ to get a **unique** parameter value
  $$t_0=\frac{d-n\cdot p}{n\cdot v},$$
  giving the unique intersection point $x_0=p+\frac{d-n\cdot p}{n\cdot v}v$. Geometrically, $v$ is not perpendicular to $n$, so the line pierces the plane.

### Case 2: Parallel with no common points (strictly parallel)
- **Condition:** $n\cdot v=0\quad\text{and}\quad n\cdot p\neq d$.
- **Explanation:** The equation for $t$ becomes $0\cdot t=d-n\cdot p\neq 0$, which is a contradiction and has **no solution** $t\in\mathbb{R}$. Geometrically, $v\perp n$ (so the line runs parallel to the plane), and the starting point $p$ lies outside the plane.

### Case 3: The line is contained in the plane
- **Condition:** $n\cdot v=0\quad\text{and}\quad n\cdot p=d$.
- **Explanation:** The equation for $t$ becomes $0\cdot t=0$, which holds for **every** $t\in\mathbb{R}$. Geometrically, the line starts at a point $p$ inside the plane and moves in a direction $v$ parallel to the plane, so it never leaves the plane.

| Case | Condition on $n\cdot v$ | Condition on $n\cdot p$ | Equation $(n\cdot v)t=d-n\cdot p$ | Common points |
| :--- | :---: | :---: | :---: | :---: |
| **1. Intersects at one point** | $n\cdot v\neq 0$ | any | unique solution $t$ | $1$ point |
| **2. Strictly parallel** | $n\cdot v=0$ | $n\cdot p\neq d$ | $0\cdot t=\text{non-zero}$ (no solution) | $0$ points |
| **3. Contained in the plane** | $n\cdot v=0$ | $n\cdot p=d$ | $0\cdot t=0$ (all $t\in\mathbb{R}$) | infinitely many (whole line) |

## 2. Numerical examples of each case

Fix the horizontal plane $\Pi:z=0$, for which $n=(0,0,1)$ and $d=0$:

1. **Case 1 (One intersection point):** Let $p=(0,0,1)$ and $v=(0,0,1)$, so $L:(0,0,1+t)$.
   - Here $n\cdot v=(0,0,1)\cdot(0,0,1)=1\neq 0$.
   - The line is the $z$-axis and intersects $z=0$ at the single point $(0,0,0)$ (for $t=-1$).
2. **Case 2 (Strictly parallel, no common points):** Let $p=(0,0,1)$ and $v=(1,0,0)$, so $L:(t,0,1)$.
   - Here $n\cdot v=(0,0,1)\cdot(1,0,0)=0$, while $n\cdot p=1\neq 0=d$.
   - Every point $(t,0,1)$ has $z=1\neq 0$, so the line is parallel to $z=0$ with no common points.
3. **Case 3 (Line contained in the plane):** Let $p=(0,0,0)$ and $v=(1,0,0)$, so $L:(t,0,0)$.
   - Here $n\cdot v=(0,0,1)\cdot(1,0,0)=0$ and $n\cdot p=(0,0,1)\cdot(0,0,0)=0=d$.
   - This line is the $x$-axis, which lies completely inside the $xy$-plane $z=0$.

## Quick verification

Let us plug our three examples directly into $(n\cdot v)t=d-n\cdot p$ with $n=(0,0,1)$ and $d=0$:
- **Example 1:** $1\cdot t=0-1\implies t=-1$, giving $x=(0,0,1)+(-1)(0,0,1)=(0,0,0)\in\Pi$. ✓
- **Example 2:** $0\cdot t=0-1\implies 0=-1$ (impossible, $\varnothing$). ✓
- **Example 3:** $0\cdot t=0-0\implies 0=0$ (true for all $t\in\mathbb{R}$). ✓

## A concrete example

This classification shows why a line and a plane in $\mathbb{R}^3$ can have **$0$, $1$, or infinitely many** common points, but **never** exactly $2$ common points: if two distinct points $p+t_1v$ and $p+t_2v$ ($t_1\neq t_2$) both satisfy $(n\cdot v)t=d-n\cdot p$, subtracting gives $(n\cdot v)(t_1-t_2)=0\implies n\cdot v=0$, which forces $d-n\cdot p=0$ and puts us in Case 3 where the **entire** line lies in the plane.

## How I would explain this in class

> When you plug the line $x=p+tv$ into the plane $n\cdot x=d$, you always get the one-variable equation $(n\cdot v)t=d-n\cdot p$. That gives three clean cases: if $n\cdot v\neq 0$, you can divide by $n\cdot v$ and get one unique intersection point; if $n\cdot v=0$ and $n\cdot p\neq d$, you get $0\cdot t=\text{non-zero}$, so the line is parallel to the plane and never touches it; and if $n\cdot v=0$ and $n\cdot p=d$, you get $0\cdot t=0$, so every $t$ works and the whole line sits inside the plane.

## Related workbook topics

- [Exercise 7: A Line Relative to a Plane](problem_07_solution.md)
- [Exercise 14: Contrast: Intersection and Parallelism](problem_14_solution.md)
