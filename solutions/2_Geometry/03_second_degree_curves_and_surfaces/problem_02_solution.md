# Exercise 2. Circle by Completing the Square

## The question

Reduce

$$x^2+y^2-6x+4y-3=0$$

to canonical form. Find the center and radius, then substitute two simple points from the circle into both forms of the equation.

## Before calculating: what idea do we need?

A circle with center $(x_0,y_0)$ and radius $r>0$ has the canonical equation

$$(x-x_0)^2+(y-y_0)^2=r^2.$$

When this equation is expanded, it produces linear terms $-2x_0 x$ and $-2y_0 y$. To reverse the expansion, we group the $x$-terms and $y$-terms separately and **complete the square** using

$$x^2+bx = \left(x+\frac{b}{2}\right)^2 - \left(\frac{b}{2}\right)^2.$$

## 1. Grouping terms and completing the square

Start by grouping the $x$-terms, grouping the $y$-terms, and moving the constant to the right-hand side:

$$(x^2-6x) + (y^2+4y) = 3.$$

For $x^2-6x$, half of $-6$ is $-3$, and $(-3)^2=9$:

$$x^2-6x = (x-3)^2 - 9.$$

For $y^2+4y$, half of $4$ is $2$, and $2^2=4$:

$$y^2+4y = (y+2)^2 - 4.$$

Substitute these into the grouped equation:

$$(x-3)^2 - 9 + (y+2)^2 - 4 = 3.$$

Add $9+4=13$ to both sides to obtain the canonical form:

$$(x-3)^2 + (y+2)^2 = 16.$$

## 2. Reading the center and radius

Compare $(x-3)^2 + (y-(-2))^2 = 4^2$ with $(x-x_0)^2 + (y-y_0)^2 = r^2$:

- **Center:** $C = (3,-2)$ (note the opposite signs of the numbers inside the parentheses).
- **Radius:** $r = \sqrt{16} = 4$.

## 3. Finding two simple points on the circle

From the center $(3,-2)$, moving by the radius $r=4$ parallel to the coordinate axes gives four cardinal points:

- Moving right by $4$: $P_1 = (3+4,-2) = (7,-2)$.
- Moving up by $4$: $P_2 = (3,-2+4) = (3,2)$.
- (Also left: $(-1,-2)$ and down: $(3,-6)$.)

## 4. Substituting the points into both forms

For $P_1 = (7,-2)$:
- **Canonical form:** $(7-3)^2 + (-2+2)^2 = 4^2 + 0^2 = 16$.
- **General form:** $7^2 + (-2)^2 - 6(7) + 4(-2) - 3 = 49 + 4 - 42 - 8 - 3 = 0$.

For $P_2 = (3,2)$:
- **Canonical form:** $(3-3)^2 + (2+2)^2 = 0^2 + 4^2 = 16$.
- **General form:** $3^2 + 2^2 - 6(3) + 4(2) - 3 = 9 + 4 - 18 + 8 - 3 = 0$.

Both forms represent the exact same set of points.

## Quick verification

Expand the canonical form $(x-3)^2+(y+2)^2=16$ back out:

$$(x^2-6x+9) + (y^2+4y+4) - 16 = x^2+y^2-6x+4y-3 = 0.$$

This recovers the original equation identically. ✓

## A concrete example

Notice that $(0,0)$ is at squared distance $(0-3)^2+(0+2)^2 = 9+4 = 13 < 16$ from the center $(3,-2)$, so the origin lies **inside** the circle. In the general equation, substituting $(0,0)$ gives $-3<0$, which also shows that $(0,0)$ is inside the circle.

## How I would explain this in class

> To find the center and radius of $x^2+y^2-6x+4y-3=0$, we complete the square separately for $x$ and $y$. Half of $-6$ is $-3$ and half of $+4$ is $+2$, which gives $(x-3)^2-9 + (y+2)^2-4 - 3 = 0$, or $(x-3)^2+(y+2)^2=16$. From this canonical form we immediately read the center $(3,-2)$ and radius $r=4$. Stepping $4$ units right or up from the center gives $(7,-2)$ and $(3,2)$, which satisfy both equations.

## Related workbook topics

- [Exercise 6: Shifted Ellipse](problem_06_solution.md)
- [Exercise 8: Sphere](problem_08_solution.md)
