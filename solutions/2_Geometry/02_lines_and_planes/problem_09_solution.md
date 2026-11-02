# Exercise 9. Distances

## The question

Compute:
1. the distance from $P=(2,3)$ to the line $3x+4y-10=0$,
2. the distance from $Q=(2,-1,3)$ to the plane $2x-2y+z-4=0$.

Compare the two formulas and explain their common connection with the normal direction.

## Before calculating: what idea do we need?

Whether we measure the distance from a point to a **line in $\mathbb{R}^2$** or from a point to a **plane in $\mathbb{R}^3$**, the shortest path always runs perpendicular to the object—that is, **along the normal vector** $n$.

If the object has the equation $n\cdot x+c=0$ and $X_0$ is any point on the object (so $n\cdot X_0=-c$), the distance from an external point $P$ is the length of the orthogonal projection of $\overrightarrow{X_0P}=P-X_0$ onto the unit normal vector $\frac{n}{\|n\|}$:

$$\text{dist}=\frac{|n\cdot(P-X_0)|}{\|n\|}=\frac{|n\cdot P+c|}{\|n\|}.$$

## 1. Distance from $P=(2,3)$ to the line $3x+4y-10=0$

For the line $3x+4y-10=0$ in $\mathbb{R}^2$:
- The normal vector is $n=(3,4)$, with length $\|n\|=\sqrt{3^2+4^2}=\sqrt{9+16}=\sqrt{25}=5$.
- Evaluating $|3x+4y-10|$ at $P=(2,3)$ gives $|3(2)+4(3)-10|=|6+12-10|=8$.

Dividing by $\|n\|=5$:

$$d(P,L)=\frac{|3(2)+4(3)-10|}{\sqrt{3^2+4^2}}=\frac{8}{5}=1.6.$$

## 2. Distance from $Q=(2,-1,3)$ to the plane $2x-2y+z-4=0$

For the plane $2x-2y+z-4=0$ in $\mathbb{R}^3$:
- The normal vector is $n=(2,-2,1)$, with length $\|n\|=\sqrt{2^2+(-2)^2+1^2}=\sqrt{4+4+1}=\sqrt{9}=3$.
- Evaluating $|2x-2y+z-4|$ at $Q=(2,-1,3)$ gives $|2(2)-2(-1)+1(3)-4|=|4+2+3-4|=5$.

Dividing by $\|n\|=3$:

$$d(Q,\Pi)=\frac{|2(2)-2(-1)+3-4|}{\sqrt{2^2+(-2)^2+1^2}}=\frac{5}{3}.$$

## 3. Comparing the two formulas and their connection to the normal direction

Compare the two expressions side by side:

$$\text{In }\mathbb{R}^2:\quad d=\frac{|ax_0+by_0+c|}{\sqrt{a^2+b^2}},\qquad\qquad \text{In }\mathbb{R}^3:\quad d=\frac{|ax_0+by_0+cz_0+d|}{\sqrt{a^2+b^2+c^2}}.$$

Both are instances of the exact same vector formula $\dfrac{|n\cdot P+c|}{\|n\|}$:
- The **numerator** $|n\cdot P+c|=|n\cdot(P-X_0)|$ measures how far $P$ is displaced along the normal direction, scaled by $\|n\|$.
- The **denominator** $\|n\|$ divides out the length of the normal vector so that the result is measured in true geometric unit lengths (it projects $P-X_0$ onto the unit normal $\hat{n}=n/\|n\|$).

## Quick verification

Let us verify both distances by finding the actual closest point (orthogonal projection) in each case:

1. **For the line in $\mathbb{R}^2$:** Moving from $P=(2,3)$ along $n=(3,4)$ gives $(2+3t,3+4t)$. Plugging into $3x+4y-10=0$:
   $$3(2+3t)+4(3+4t)-10=0\implies 8+25t=0\implies t=-\frac{8}{25}.$$
   The displacement vector has length $|t|\,\|n\|=\frac{8}{25}\cdot 5=\frac{8}{5}$. ✓
2. **For the plane in $\mathbb{R}^3$:** Moving from $Q=(2,-1,3)$ along $n=(2,-2,1)$ gives $(2+2t,-1-2t,3+t)$. Plugging into $2x-2y+z-4=0$:
   $$2(2+2t)-2(-1-2t)+(3+t)-4=0\implies 5+9t=0\implies t=-\frac{5}{9}.$$
   The displacement vector has length $|t|\,\|n\|=\frac{5}{9}\cdot 3=\frac{5}{3}$. ✓

## A concrete example

Notice why dividing by $\|n\|$ is essential: if we multiply the line equation $3x+4y-10=0$ by $2$, we get the exact same line $6x+8y-20=0$. At $P=(2,3)$, the numerator doubles from $8$ to $|6(2)+8(3)-20|=16$, and the denominator $\|n\|=\sqrt{6^2+8^2}=10$ also doubles from $5$ to $10$, leaving the geometric distance $\frac{16}{10}=\frac{8}{5}$ unchanged.

## How I would explain this in class

> A line in 2D and a plane in 3D are both defined by a single normal vector $n$, so their distance formulas work the exact same way: plug the point into the equation's left-hand side, take the absolute value, and divide by the length of the normal vector $\|n\|$. For $P=(2,3)$ and $3x+4y-10=0$, $\|n\|=\sqrt{3^2+4^2}=5$ and the numerator is $|6+12-10|=8$, giving $\frac{8}{5}$. For $Q=(2,-1,3)$ and $2x-2y+z-4=0$, $\|n\|=\sqrt{4+4+1}=3$ and the numerator is $|4+2+3-4|=5$, giving $\frac{5}{3}$.

## Related workbook topics

- [Exercise 10: Projection of a Point onto a Plane](problem_10_solution.md)
- [Exercise 13: Closest Point on a Plane](problem_13_solution.md)
