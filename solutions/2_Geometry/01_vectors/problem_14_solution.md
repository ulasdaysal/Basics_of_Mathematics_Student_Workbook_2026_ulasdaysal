# Exercise 14. Closest Point on a Line

## The question

Given a point $P=(4,1)$ and a line through the origin with direction $v=(1,2)$. Using projection, find the closest point on the line, the distance from $P$ to the line, and verify that the appropriate vector is perpendicular to the direction of the line.

## Before calculating: what idea do we need?

Let $\ell$ be the line through the origin $O=(0,0)$ with direction vector $v=(1,2)$, so every point on $\ell$ has position vector $tv$ for some $t\in\mathbb R$.

By the **Pythagorean theorem**, the shortest path from an external point $P$ to a line $\ell$ is along the **perpendicular** dropped from $P$ to $\ell$:

1. The foot of the perpendicular—the **closest point $Q$ on the line**—has position vector equal to the orthogonal projection of $p=\overrightarrow{OP}$ onto $v$:
   $$\overrightarrow{OQ} = \operatorname{proj}_v p = \frac{p\cdot v}{v\cdot v}\,v.$$
2. The displacement vector from the closest point $Q$ to $P$ is the perpendicular residual
   $$\overrightarrow{QP} = p - \operatorname{proj}_v p,$$
   and its length $\|\overrightarrow{QP}\|$ is the **distance from $P$ to the line**.

## 1. Finding the closest point $Q$ on the line

Let $p = \overrightarrow{OP} = (4,1)$ and $v = (1,2)$. We compute the dot products:

$$p\cdot v = 4\cdot 1 + 1\cdot 2 = 4 + 2 = 6,$$

$$v\cdot v = 1^2 + 2^2 = 1 + 4 = 5.$$

The projection of $p$ onto $v$ is

$$\overrightarrow{OQ} = \operatorname{proj}_v p = \frac{p\cdot v}{v\cdot v}\,v = \frac{6}{5}(1,2) = \left(\frac{6}{5},\, \frac{12}{5}\right).$$

Therefore, the closest point on the line is

$$Q = \left(\frac{6}{5},\, \frac{12}{5}\right) = (1.2,\, 2.4).$$

## 2. Finding the distance from $P$ to the line

First, we construct the vector from the closest point $Q$ to $P$:

$$\overrightarrow{QP} = P - Q = (4,1) - \left(\frac{6}{5},\, \frac{12}{5}\right) = \left(\frac{20-6}{5},\, \frac{5-12}{5}\right) = \left(\frac{14}{5},\, -\frac{7}{5}\right).$$

The distance $d(P,\ell)$ from $P$ to the line is the norm of $\overrightarrow{QP}$:

$$d(P,\ell) = \left\|\overrightarrow{QP}\right\| = \sqrt{\left(\frac{14}{5}\right)^2 + \left(-\frac{7}{5}\right)^2} = \frac{1}{5}\sqrt{196 + 49} = \frac{\sqrt{245}}{5} = \frac{7\sqrt{5}}{5}.$$

## 3. Verifying perpendicularity to the line

The vector connecting the closest point $Q$ on the line to $P$ is $\overrightarrow{QP} = \left(\frac{14}{5}, -\frac{7}{5}\right)$. Taking its dot product with the line's direction vector $v=(1,2)$:

$$\overrightarrow{QP}\cdot v = \left(\frac{14}{5},\, -\frac{7}{5}\right)\cdot(1,2) = \frac{14}{5}\cdot 1 + \left(-\frac{7}{5}\right)\cdot 2 = \frac{14 - 14}{5} = 0.$$

Since $\overrightarrow{QP}\cdot v = 0$, the segment $QP$ is perpendicular to the direction of the line.

## 4. Why this perpendicularity guarantees minimum distance

Take **any** point $X = tv$ on the line $\ell$. We can split the displacement $\overrightarrow{XP}$ into a piece along the line ($\overrightarrow{XQ}$) and the perpendicular piece ($\overrightarrow{QP}$):

$$\overrightarrow{XP} = \overrightarrow{XQ} + \overrightarrow{QP}.$$

Since $\overrightarrow{XQ}$ is parallel to $v$ and $\overrightarrow{QP} \perp v$, the Pythagorean theorem gives

$$\|\overrightarrow{XP}\|^2 = \|\overrightarrow{XQ}\|^2 + \|\overrightarrow{QP}\|^2 \ge \|\overrightarrow{QP}\|^2,$$

with equality if and only if $\|\overrightarrow{XQ}\|=0$, i.e., $X=Q$. Thus $Q=\left(\frac65,\frac{12}{5}\right)$ uniquely minimizes the distance.

## Quick verification

Let us check the distance using the 2D point-to-line formula: the line through $(0,0)$ with direction $v=(1,2)$ has Cartesian equation $2x - y = 0$. The distance from $P=(4,1)$ to $2x - y = 0$ is

$$d = \frac{|2(4) - 1(1)|}{\sqrt{2^2 + (-1)^2}} = \frac{|8 - 1|}{\sqrt{5}} = \frac{7}{\sqrt{5}} = \frac{7\sqrt{5}}{5}.\quad \checkmark$$

Also check the Pythagorean theorem on $\triangle OQP$:

$$\|\overrightarrow{OQ}\|^2 + \|\overrightarrow{QP}\|^2 = \frac{36+144}{25} + \frac{196+49}{25} = \frac{180 + 245}{25} = \frac{425}{25} = 17 = 4^2 + 1^2 = \|\overrightarrow{OP}\|^2.\quad \checkmark$$

## A concrete example

Let us compare $Q=(1.2, 2.4)$ with two nearby integer-parameter points on the line $X(t)=t(1,2)$:

- At $t=1$, $X(1)=(1,2)$ has distance $\|(4,1)-(1,2)\| = \|(3,-1)\| = \sqrt{10} \approx 3.162$.
- At $t=2$, $X(2)=(2,4)$ has distance $\|(4,1)-(2,4)\| = \|(2,-3)\| = \sqrt{13} \approx 3.606$.
- At the projection parameter $t=\frac65=1.2$, $Q=(1.2, 2.4)$ achieves the minimum distance $\frac{7\sqrt{5}}{5} = \sqrt{9.8} \approx 3.130$.

## How I would explain this in class

> Every point on the line has position $tv$, and the closest point $Q$ to $P=(4,1)$ is the orthogonal projection of $p=(4,1)$ onto $v=(1,2)$: $Q = \frac{p\cdot v}{v\cdot v}v = \frac65(1,2) = (\frac65,\frac{12}{5})$. The connecting vector from $Q$ to $P$ is $\overrightarrow{QP} = (4,1)-(\frac65,\frac{12}{5}) = (\frac{14}{5},-\frac75)$. We check $\overrightarrow{QP}\cdot(1,2) = \frac{14}{5}-\frac{14}{5}=0$, confirming $\overrightarrow{QP}\perp v$, and its length $\|\overrightarrow{QP}\| = \frac{7\sqrt{5}}{5}$ is the shortest distance from $P$ to the line.

## Related workbook topics

- [Exercise 6: Projection and perpendicular component](problem_06_solution.md)
- [Exercise 11: Decomposition into parallel and perpendicular components](problem_11_solution.md)
