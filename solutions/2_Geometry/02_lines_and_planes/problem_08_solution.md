# Exercise 8. Intersection Point of a Line and a Plane

## The question

Find the intersection point of

$$(x,y,z)=(1,0,2)+t(1,2,-1)$$

with the plane $x+y+z=4$. Check the result by substituting it into both descriptions.

## Before calculating: what idea do we need?

The parametric equation of the line expresses all three coordinates $(x,y,z)$ in terms of a **single parameter** $t$. When we substitute those expressions for $x$, $y$, and $z$ into the plane's equation $ax+by+cz=d$, the three-variable problem collapses into one linear equation in one unknown $t$.

- First, note that $v\cdot n=(1,2,-1)\cdot(1,1,1)=1+2-1=2\neq0$, so the line is not parallel to the plane and must intersect it at a unique point.
- Solving for $t$ tells us the exact "time" at which the line crosses the plane, and plugging that $t$ back into the line gives the coordinates of the intersection point.

## 1. Writing the parametric coordinates of the line

From $(x,y,z)=(1,0,2)+t(1,2,-1)$, any point on the line has coordinates

$$\begin{cases}x=1+t,\\y=2t,\\z=2-t,\end{cases}\qquad t\in\mathbb{R}.$$

## 2. Substituting into the plane equation to find $t$

Substitute $x=1+t$, $y=2t$, and $z=2-t$ into $x+y+z=4$:

$$(1+t)+(2t)+(2-t)=4.$$

Combine like terms:

$$3+2t=4\implies 2t=1\implies t=\frac{1}{2}.$$

## 3. Finding the coordinates of the intersection point

Now substitute $t=\frac{1}{2}$ back into the parametric form of the line:

$$(x,y,z)=(1,0,2)+\frac{1}{2}(1,2,-1)=\left(1+\frac{1}{2},\,0+1,\,2-\frac{1}{2}\right)=\left(\frac{3}{2},\,1,\,\frac{3}{2}\right).$$

Thus, the intersection point is

$$P=\left(\frac{3}{2},\,1,\,\frac{3}{2}\right).$$

## Quick verification

We check that $P=\left(\frac{3}{2},1,\frac{3}{2}\right)$ satisfies both descriptions:

1. **Plane check:** Substitute $P$ into $x+y+z=4$:
   $$\frac{3}{2}+1+\frac{3}{2}=3+1=4.\text{ ✓}$$
2. **Line check:** The displacement from $P_0=(1,0,2)$ to $P=\left(\frac{3}{2},1,\frac{3}{2}\right)$ is
   $$P-P_0=\left(\frac{3}{2}-1,\,1-0,\,\frac{3}{2}-2\right)=\left(\frac{1}{2},\,1,\,-\frac{1}{2}\right)=\frac{1}{2}(1,2,-1)=\frac{1}{2}v,$$
   confirming $P$ lies on the line at $t=\frac{1}{2}$. ✓

## A concrete example

At $t=0$, the point $P_0=(1,0,2)$ has $x+y+z=1+0+2=3<4$ (it is on one side of the plane). At $t=1$, the point $P_1=(2,2,1)$ has $x+y+z=2+2+1=5>4$ (it is on the opposite side of the plane). Since $x+y+z$ increases linearly from $3$ to $5$ as $t$ goes from $0$ to $1$, it hits the plane value $4$ right at the midpoint $t=\frac{1}{2}$, which is $P=\frac{P_0+P_1}{2}=\left(\frac{3}{2},1,\frac{3}{2}\right)$.

## How I would explain this in class

> Every point on the line can be written as $(1+t,\,2t,\,2-t)$. To find where the line hits the plane $x+y+z=4$, I substitute those three expressions into the plane equation: $(1+t)+2t+(2-t)=4$. That simplifies to $3+2t=4$, so $t=\frac{1}{2}$. Plugging $t=\frac{1}{2}$ back into the line equation gives the intersection point $\left(\frac{3}{2},1,\frac{3}{2}\right)$, and a quick check confirms $\frac{3}{2}+1+\frac{3}{2}=4$.

## Related workbook topics

- [Exercise 7: A Line Relative to a Plane](problem_07_solution.md)
- [Exercise 10: Projection of a Point onto a Plane](problem_10_solution.md)
