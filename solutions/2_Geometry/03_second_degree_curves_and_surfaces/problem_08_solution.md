# Exercise 8. Sphere

## The question

Reduce

$$x^2+y^2+z^2-4x+2y-6z-2=0$$

to canonical form. Find the center and radius. Give two points on the sphere and check them in the equation.

## Before calculating: what idea do we need?

A sphere in three-dimensional space is the set of all points $(x,y,z)$ at a fixed distance $r$ from a center $C=(x_0,y_0,z_0)$. By the 3D distance formula, its canonical equation is

$$(x-x_0)^2 + (y-y_0)^2 + (z-z_0)^2 = r^2.$$

Just as for a circle in the plane, we reduce a general sphere equation to canonical form by **completing the square independently in $x$, $y$, and $z$**.

## 1. Grouping terms and completing the three squares

Group the $x$-, $y$-, and $z$-terms, and move the constant $-2$ to the right-hand side:

$$(x^2-4x) + (y^2+2y) + (z^2-6z) = 2.$$

Complete each square using $u^2+bu = \left(u+\frac{b}{2}\right)^2 - \left(\frac{b}{2}\right)^2$:
- For $x$: $x^2-4x = (x-2)^2 - 4$,
- For $y$: $y^2+2y = (y+1)^2 - 1$,
- For $z$: $z^2-6z = (z-3)^2 - 9$.

Substitute these into the equation:

$$(x-2)^2 - 4 + (y+1)^2 - 1 + (z-3)^2 - 9 = 2.$$

Add $4+1+9=14$ to both sides to get the canonical form:

$$(x-2)^2 + (y+1)^2 + (z-3)^2 = 16.$$

## 2. Center and radius

Comparing $(x-2)^2 + (y-(-1))^2 + (z-3)^2 = 4^2$ with $(x-x_0)^2 + (y-y_0)^2 + (z-z_0)^2 = r^2$:

- **Center:** $C = (2,-1,3)$.
- **Radius:** $r = \sqrt{16} = 4$.

## 3. Finding two points on the sphere

Starting from the center $C=(2,-1,3)$, we can step by the radius $r=4$ along any coordinate axis:

- Step $+4$ along the $x$-axis: $P_1 = (2+4, -1, 3) = (6,-1,3)$.
- Step $+4$ along the $y$-axis: $P_2 = (2, -1+4, 3) = (2,3,3)$.
- *(Other cardinal points include $(-2,-1,3)$, $(2,-5,3)$, $(2,-1,7)$, and $(2,-1,-1)$.)*

## 4. Checking the two points in the equation

Let us check $P_1=(6,-1,3)$ and $P_2=(2,3,3)$ in both forms of the equation:

- **For $P_1=(6,-1,3)$:**
  - Canonical: $(6-2)^2 + (-1+1)^2 + (3-3)^2 = 4^2 + 0 + 0 = 16$.
  - Original: $6^2 + (-1)^2 + 3^2 - 4(6) + 2(-1) - 6(3) - 2 = 36 + 1 + 9 - 24 - 2 - 18 - 2 = 0$.

- **For $P_2=(2,3,3)$:**
  - Canonical: $(2-2)^2 + (3+1)^2 + (3-3)^2 = 0 + 4^2 + 0 = 16$.
  - Original: $2^2 + 3^2 + 3^2 - 4(2) + 2(3) - 6(3) - 2 = 4 + 9 + 9 - 8 + 6 - 18 - 2 = 0$.

## Quick verification

Let us also check the antipodal point along the $z$-axis, $P_3 = (2,-1,3-4) = (2,-1,-1)$, in the original equation:

$$2^2 + (-1)^2 + (-1)^2 - 4(2) + 2(-1) - 6(-1) - 2 = 4 + 1 + 1 - 8 - 2 + 6 - 2 = 0.$$

And expanding $(x-2)^2+(y+1)^2+(z-3)^2-16 = (x^2-4x+4)+(y^2+2y+1)+(z^2-6z+9)-16 = x^2+y^2+z^2-4x+2y-6z-2=0$. ✓

## A concrete example

Does this sphere intersect the $xy$-plane ($z=0$)? Setting $z=0$ in the canonical equation gives

$$(x-2)^2 + (y+1)^2 + (0-3)^2 = 16 \implies (x-2)^2 + (y+1)^2 = 16 - 9 = 7.$$

So the sphere slices the $xy$-plane in a circle centered at $(2,-1,0)$ with radius $\sqrt{7}$.

## How I would explain this in class

> Completing the square for a sphere in 3D works just like for a circle in 2D, with one extra variable $z$. Grouping terms gives $(x^2-4x)+(y^2+2y)+(z^2-6z)=2$, which becomes $(x-2)^2-4+(y+1)^2-1+(z-3)^2-9=2$, or $(x-2)^2+(y+1)^2+(z-3)^2=16$. That tells us the center is $(2,-1,3)$ and the radius is $r=4$. Moving $4$ units along the $x$- or $y$-axis from the center gives $(6,-1,3)$ and $(2,3,3)$, which both make the original equation equal to $0$.

## Related workbook topics

- [Exercise 2: Circle by Completing the Square](problem_02_solution.md)
- [Exercise 13: Intersection of a Sphere and a Plane](problem_13_solution.md)
