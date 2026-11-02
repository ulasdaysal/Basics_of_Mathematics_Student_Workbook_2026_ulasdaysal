# Exercise 10. Projection of a Point onto a Plane

## The question

Find the orthogonal projection of $P=(2,1,3)$ onto the plane $x+y+z=3$, and then find the reflection of $P$ across this plane. Check that the midpoint of the segment joining the point and its reflection lies on the plane.

## Before calculating: what idea do we need?

Imagine dropping a plumb line from $P$ straight down onto the plane $\Pi$ at a $90^\circ$ angle:

1. Because the line is perpendicular to $\Pi$, its direction vector is the plane's **normal vector** $n$.
2. Where this normal line $P+tn$ intersects $\Pi$ is the **orthogonal projection** $P'$ (the foot of the perpendicular).
3. If it takes a step $t_0n$ to go from $P$ to the mirror $\Pi$, then continuing by another identical step $t_0n$ on the other side of the mirror lands at the **reflection** $P''=P+2t_0n=2P'-P$.

## 1. Constructing the normal line through $P$

The plane $\Pi:x+y+z=3$ has normal vector

$$n=(1,1,1).$$

The line passing through $P=(2,1,3)$ perpendicular to $\Pi$ has parametric equation

$$(x,y,z)=(2,1,3)+t(1,1,1)=(2+t,\,1+t,\,3+t),\qquad t\in\mathbb{R}.$$

## 2. Finding the orthogonal projection $P'$

We find where the normal line hits the plane $x+y+z=3$ by substituting its coordinates:

$$(2+t)+(1+t)+(3+t)=3\implies 6+3t=3\implies 3t=-3\implies t=-1.$$

Substituting $t=-1$ into the line gives the orthogonal projection:

$$P'=(2-1,\,1-1,\,3-1)=(1,0,2).$$

## 3. Finding the reflection $P''$ across the plane

To go from $P$ to the plane $\Pi$, we added the displacement $\overrightarrow{PP'}=(-1)n=(-1,-1,-1)$. To reflect across the plane, we take **twice** this step from $P$ (or one more step from $P'$):

$$P''=P+2(-1)n=(2,1,3)+(-2,-2,-2)=(0,-1,1).$$

Equivalently, using $P'=\frac{P+P''}{2}\implies P''=2P'-P=2(1,0,2)-(2,1,3)=(0,-1,1)$.

## Quick verification

1. **Midpoint check:** The midpoint $M$ of $P=(2,1,3)$ and $P''=(0,-1,1)$ is
   $$M=\frac{P+P''}{2}=\left(\frac{2+0}{2},\,\frac{1+(-1)}{2},\,\frac{3+1}{2}\right)=(1,0,2)=P'.$$
   Substituting $M=(1,0,2)$ into the plane equation $x+y+z=3$:
   $$1+0+2=3.\text{ ✓}$$
2. **Perpendicularity check:** The vector $\overrightarrow{PP''}=P''-P=(-2,-2,-2)=-2(1,1,1)=-2n$ is parallel to the normal vector $n$, so the segment $PP''$ is indeed perpendicular to the plane. ✓

## A concrete example

How far are $P$ and $P''$ from the plane?
- The distance from $P=(2,1,3)$ to $P'=(1,0,2)$ is $\|\overrightarrow{PP'}\|=\|(-1,-1,-1)\|=\sqrt{3}$.
- The distance from $P''=(0,-1,1)$ to $P'=(1,0,2)$ is $\|\overrightarrow{P''P'}\|=\|(1,1,1)\|=\sqrt{3}$.

Both points lie at the exact same distance $\sqrt{3}$ on opposite sides of the mirror plane $x+y+z=3$.

## How I would explain this in class

> To project $P=(2,1,3)$ onto the plane $x+y+z=3$, I shoot a line from $P$ in the direction of the plane's normal vector $n=(1,1,1)$, which gives $(2+t,1+t,3+t)$. Plugging this into $x+y+z=3$ gives $6+3t=3$, so $t=-1$. At $t=-1$, we hit the plane at the projection $P'=(1,0,2)$. To get the reflection $P''$, we just keep walking the same step $(-1,-1,-1)$ one more time past the mirror, landing at $t=-2$, which is $P''=(0,-1,1)$.

## Related workbook topics

- [Exercise 8: Intersection Point of a Line and a Plane](problem_08_solution.md)
- [Exercise 13: Closest Point on a Plane](problem_13_solution.md)
