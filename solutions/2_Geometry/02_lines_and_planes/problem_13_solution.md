# Exercise 13. Closest Point on a Plane

## The question

Find the point on the plane $x+2y+2z=4$ closest to $P=(3,0,0)$. Give the distance and check that the segment joining the two points is perpendicular to the plane.

## Before calculating: what idea do we need?

By the Pythagorean theorem, for any point $X$ on the plane $\Pi$ and the orthogonal projection $Q$ of $P$ onto $\Pi$, the triangle $\triangle PQX$ has a right angle at $Q$, so

$$\|P-X\|^2=\|P-Q\|^2+\|Q-X\|^2\ge \|P-Q\|^2.$$

Therefore, the **closest point** $Q$ on the plane to $P$ is the **orthogonal projection** of $P$ onto $\Pi$, obtained by following the normal vector $n$ from $P$ until we hit the plane. The distance from $P$ to the plane is then the length $\|P-Q\|$.

## 1. Finding the closest point $Q$ via the normal line

The plane $x+2y+2z=4$ has normal vector

$$n=(1,2,2).$$

The line through $P=(3,0,0)$ in the normal direction $n=(1,2,2)$ is

$$(x,y,z)=(3,0,0)+t(1,2,2)=(3+t,\,2t,\,2t),\qquad t\in\mathbb{R}.$$

Substitute these coordinates into the plane equation $x+2y+2z=4$:

$$(3+t)+2(2t)+2(2t)=4\implies 3+9t=4\implies 9t=1\implies t=\frac{1}{9}.$$

Plugging $t=\frac{1}{9}$ back into the normal line gives the closest point on the plane:

$$Q=\left(3+\frac{1}{9},\,\frac{2}{9},\,\frac{2}{9}\right)=\left(\frac{28}{9},\,\frac{2}{9},\,\frac{2}{9}\right).$$

## 2. Computing the distance from $P$ to the plane

The displacement vector from $P$ to $Q$ is

$$\overrightarrow{PQ}=Q-P=\left(\frac{1}{9},\,\frac{2}{9},\,\frac{2}{9}\right)=\frac{1}{9}(1,2,2).$$

Its length is the distance from $P$ to the plane:

$$d(P,\Pi)=\|\overrightarrow{PQ}\|=\frac{1}{9}\sqrt{1^2+2^2+2^2}=\frac{1}{9}\sqrt{9}=\frac{3}{9}=\frac{1}{3}.$$

## 3. Checking perpendicularity of the segment $PQ$ to the plane

The segment joining $P$ and $Q$ has direction vector $\overrightarrow{PQ}=\frac{1}{9}(1,2,2)=\frac{1}{9}n$. Because $\overrightarrow{PQ}$ is a scalar multiple of the plane's normal vector $n=(1,2,2)$, it is perpendicular to every vector $w$ lying in the plane ($w\cdot\overrightarrow{PQ}=\frac{1}{9}(w\cdot n)=0$).

## Quick verification

1. **Check that $Q$ lies on the plane $x+2y+2z=4$:**
   $$\frac{28}{9}+2\left(\frac{2}{9}\right)+2\left(\frac{2}{9}\right)=\frac{28+4+4}{9}=\frac{36}{9}=4.\text{ ✓}$$
2. **Check the distance using the point-to-plane distance formula:**
   $$d(P,\Pi)=\frac{|1(3)+2(0)+2(0)-4|}{\sqrt{1^2+2^2+2^2}}=\frac{|3-4|}{\sqrt{9}}=\frac{1}{3}.\text{ ✓}$$
3. **Check perpendicularity with a specific vector in the plane:** The point $A=(4,0,0)$ lies on the plane ($4+0+0=4$). The vector in the plane from $A$ to $Q$ is $\overrightarrow{AQ}=\left(-\frac{8}{9},\frac{2}{9},\frac{2}{9}\right)$, and
   $$\overrightarrow{PQ}\cdot\overrightarrow{AQ}=\frac{1}{9}\left(-\frac{8}{9}\right)+\frac{2}{9}\left(\frac{2}{9}\right)+\frac{2}{9}\left(\frac{2}{9}\right)=\frac{-8+4+4}{81}=0.\text{ ✓}$$

## A concrete example

Compare our closest point $Q=\left(\frac{28}{9},\frac{2}{9},\frac{2}{9}\right)$ with the $x$-intercept of the plane, $A=(4,0,0)$:
- Moving horizontally from $P=(3,0,0)$ along the $x$-axis to $A=(4,0,0)$ stays on the $x$-axis and gives distance $\|A-P\|=1$.
- Moving diagonally along the normal vector to $Q=\left(\frac{28}{9},\frac{2}{9},\frac{2}{9}\right)$ reaches the plane in just $\frac{1}{3}$ of a unit—three times closer!

## How I would explain this in class

> The shortest path from $P=(3,0,0)$ to the plane $x+2y+2z=4$ goes straight along the normal vector $n=(1,2,2)$. That normal line is $(3+t,2t,2t)$. Plugging it into the plane gives $(3+t)+4t+4t=4$, so $9t=1$ and $t=\frac{1}{9}$. That puts the closest point at $Q=\left(\frac{28}{9},\frac{2}{9},\frac{2}{9}\right)$. The vector $\overrightarrow{PQ}=\frac{1}{9}(1,2,2)$ is a multiple of the normal $n$, so $PQ$ is perpendicular to the plane, and its length is $\frac{1}{9}\sqrt{1^2+2^2+2^2}=\frac{1}{3}$.

## Related workbook topics

- [Exercise 9: Distances](problem_09_solution.md)
- [Exercise 10: Projection of a Point onto a Plane](problem_10_solution.md)
