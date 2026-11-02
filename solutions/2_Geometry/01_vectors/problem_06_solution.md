# Exercise 6. Projection and Perpendicular Component

## The question

Find the projection of $u=(4,2)$ onto the direction $v=(1,1)$. Then compute

$$r=u-\operatorname{proj}_v u$$

and verify that $r\cdot v=0$. Explain this result geometrically.

## Before calculating: what idea do we need?

Given a vector $u$ and a nonzero direction vector $v$, the **orthogonal projection** of $u$ onto $v$ is the vector along the line of $v$ formed by dropping a perpendicular from the tip of $u$ onto that line:

$$\operatorname{proj}_v u = \frac{u\cdot v}{v\cdot v}\,v = \frac{u\cdot v}{\|v\|^2}\,v.$$

Once we have the shadow $\operatorname{proj}_v u$ along $v$, the **residual (perpendicular) vector**

$$r = u - \operatorname{proj}_v u$$

connects the tip of the shadow on the line of $v$ directly to the tip of $u$. Because we dropped a **perpendicular** to find the shadow, $r$ must be orthogonal to $v$ ($r\cdot v=0$).

## 1. Computing the projection $\operatorname{proj}_v u$

For $u=(4,2)$ and $v=(1,1)$, we first compute the two dot products:

$$u\cdot v = 4\cdot 1 + 2\cdot 1 = 4 + 2 = 6,$$

$$v\cdot v = 1^2 + 1^2 = 2.$$

Now we substitute these into the projection formula:

$$\operatorname{proj}_v u = \frac{u\cdot v}{v\cdot v}\,v = \frac{6}{2}(1,1) = 3(1,1) = (3,3).$$

## 2. Computing the perpendicular residual $r$

Subtracting the projection from $u$:

$$r = u - \operatorname{proj}_v u = (4,2) - (3,3) = (4-3,\, 2-3) = (1,-1).$$

## 3. Verifying that $r\cdot v = 0$

We compute the dot product of $r=(1,-1)$ and $v=(1,1)$:

$$r\cdot v = 1\cdot 1 + (-1)\cdot 1 = 1 - 1 = 0.$$

Since $r\cdot v=0$, the vector $r$ is indeed perpendicular to $v$.

## 4. Geometric explanation

The vector $v=(1,1)$ defines the $45^\circ$ diagonal line $y=x$ in the plane:

- $\operatorname{proj}_v u = (3,3)$ is the orthogonal shadow of $u=(4,2)$ on the line $y=x$. Notice that $3 = \frac{4+2}{2}$ is the average of the two coordinates of $u$.
- $r = u - \operatorname{proj}_v u = (1,-1)$ is the altitude vector from the point $(3,3)$ on the line $y=x$ to the point $(4,2)$.
- Together, the vectors $\operatorname{proj}_v u = (3,3)$ and $r=(1,-1)$ are the two legs of a right triangle whose hypotenuse is $u=(4,2)$.

## Quick verification

1. **Reconstruction check:**
   $$\operatorname{proj}_v u + r = (3,3) + (1,-1) = (4,2) = u.\quad \checkmark$$
2. **Pythagorean theorem check:** Since $\operatorname{proj}_v u \perp r$, their squared lengths must add up to $\|u\|^2$:
   $$\|\operatorname{proj}_v u\|^2 + \|r\|^2 = (3^2+3^2) + (1^2+(-1)^2) = 18 + 2 = 20,$$
   $$\|u\|^2 = 4^2+2^2 = 16 + 4 = 20.\quad \checkmark$$

## A concrete example

Suppose a rail cart can only roll along a straight track pointing in the direction $v=(1,1)$, and you pull on it with force $u=(4,2)\text{ N}$:

- The component $\operatorname{proj}_v u = (3,3)\text{ N}$ (of magnitude $3\sqrt{2}\approx 4.24\text{ N}$) is the **effective force** that actually accelerates the cart along the track.
- The component $r=(1,-1)\text{ N}$ (of magnitude $\sqrt{2}\approx 1.41\text{ N}$) pulls **sideways** against the rails and is completely absorbed by the track without moving the cart forward.

## How I would explain this in class

> To project $u=(4,2)$ onto $v=(1,1)$, we compute $\frac{u\cdot v}{v\cdot v}v = \frac{6}{2}(1,1) = (3,3)$. That is the part of $u$ parallel to $v$. Subtracting it from $u$ leaves $r = (4,2)-(3,3) = (1,-1)$, whose dot product with $v$ is $1(1)+(-1)(1)=0$. Geometrically, we split $u$ into two perpendicular legs of a right triangle: its shadow $(3,3)$ along the line of $v$, and the perpendicular drop $(1,-1)$ from $u$ to that line.

## Related workbook topics

- [Exercise 11: Decomposition into parallel and perpendicular components](problem_11_solution.md)
- [Exercise 14: Closest point on a line](problem_14_solution.md)
