# Exercise 3. Plane Through a Point with a Given Normal Vector

## The question

Find the equation of the plane through $P=(1,-2,3)$ and perpendicular to $n=(2,1,-1)$. Check the result by substituting the point $P$ and explain the role of the normal vector.

## Before calculating: what idea do we need?

In three-dimensional space, a single direction perpendicular to a plane determines the plane's tilt completely. That perpendicular vector is called the **normal vector** $n=(a,b,c)$.

A point $X=(x,y,z)$ lies on the plane through $P=(x_0,y_0,z_0)$ if and only if the displacement vector $\overrightarrow{PX}=X-P$ lies flat in the plane—which means it is perpendicular to $n$:

$$n\cdot(X-P)=0\iff a(x-x_0)+b(y-y_0)+c(z-z_0)=0.$$

## 1. Point-normal form of the plane

Given $P=(1,-2,3)$ and $n=(2,1,-1)$, for any point $X=(x,y,z)$ on the plane we have

$$\overrightarrow{PX}=(x-1,\,y+2,\,z-3).$$

Imposing orthogonality $n\cdot\overrightarrow{PX}=0$ gives

$$2(x-1)+1(y+2)-1(z-3)=0.$$

## 2. Expanding to the general equation

Expanding the parentheses and collecting the constant terms:

$$2x-2+y+2-z+3=0\implies 2x+y-z+3=0,$$

or equivalently

$$2x+y-z=-3.$$

## 3. The role of the normal vector

The normal vector $n=(2,1,-1)$ plays two key roles:

1. **Algebraically**, its components $(2,1,-1)$ are the exact coefficients of $x$, $y$, and $z$ in the linear equation $2x+y-z=-3$. Whenever we see a plane equation $ax+by+cz=d$, we can immediately read off its normal vector as $n=(a,b,c)$.
2. **Geometrically**, $n$ controls the orientation of the plane in $\mathbb{R}^3$: every vector lying inside the plane is perpendicular to $n$, and moving along $n$ moves directly away from the plane at a $90^\circ$ angle. The constant term $d=-3$ only shifts the plane parallel to itself so that it passes through $P$.

## Quick verification

Substitute $P=(1,-2,3)$ into the equation $2x+y-z=-3$:

$$2(1)+(-2)-(3)=2-2-3=-3.\text{ ✓}$$

Let us also find another point on the plane, say by setting $x=0$ and $y=0$, which gives $-z=-3\implies z=3$, so $Q=(0,0,3)$. The vector in the plane is $\overrightarrow{PQ}=(-1,2,0)$, and its dot product with $n$ is

$$n\cdot\overrightarrow{PQ}=(2,1,-1)\cdot(-1,2,0)=-2+2+0=0.\text{ ✓}$$

## A concrete example

What if we kept the same normal vector $n=(2,1,-1)$ but required the plane to pass through the origin $O=(0,0,0)$ instead of $P$? Then the equation would be

$$2x+y-z=0.$$

Our plane $2x+y-z=-3$ is simply this origin-plane shifted parallel to itself until it hits $P=(1,-2,3)$.

## How I would explain this in class

> A plane in 3D is easiest to describe not by the directions inside it, but by the single direction perpendicular to it—the normal vector $n=(2,1,-1)$. Any vector from our anchor point $P=(1,-2,3)$ to another point $(x,y,z)$ on the plane must be perpendicular to $n$, so their dot product is zero: $2(x-1)+1(y+2)-1(z-3)=0$. Simplifying gives $2x+y-z=-3$. Notice how the normal vector $(2,1,-1)$ shows up directly as the coefficients of $x,y,z$.

## Related workbook topics

- [Exercise 4: Plane Through Three Points](problem_04_solution.md)
- [Exercise 6: Angle Between Planes](problem_06_solution.md)
