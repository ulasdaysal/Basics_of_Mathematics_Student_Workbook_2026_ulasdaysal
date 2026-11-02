# Exercise 4. Dot Product and Perpendicularity

## The question

For $u=(1,2,-1)$ and $v=(2,-1,3)$ compute $u\cdot v$ and determine whether the vectors are perpendicular. Then find $a$ so that $w=(2,-1,a)$ is perpendicular to $u$, and check the result.

## Before calculating: what idea do we need?

For two vectors $u=(u_1,u_2,u_3)$ and $v=(v_1,v_2,v_3)$ in $\mathbb R^3$, the **dot product (scalar product)** is computed algebraically as

$$u\cdot v = u_1v_1 + u_2v_2 + u_3v_3,$$

and geometrically satisfies

$$u\cdot v = \|u\|\,\|v\|\cos\theta,$$

where $\theta$ is the angle between $u$ and $v$. For nonzero vectors, $\cos\theta=0$ if and only if $\theta=90^\circ$ ($\frac{\pi}{2}$). This gives the fundamental **orthogonality criterion**:

$$u \perp v \iff u\cdot v = 0.$$

This criterion works both as a **test** (check whether $u\cdot v=0$) and as a **design tool** (set $u\cdot w=0$ to solve for an unknown coordinate).

## 1. Computing $u\cdot v$ and testing perpendicularity

For $u=(1,2,-1)$ and $v=(2,-1,3)$:

$$u\cdot v = 1\cdot 2 + 2\cdot(-1) + (-1)\cdot 3 = 2 - 2 - 3 = -3.$$

Because $u\cdot v = -3 \neq 0$, the vectors $u$ and $v$ **are not perpendicular** (in fact, since $u\cdot v < 0$, the angle between them is obtuse).

## 2. Finding $a$ so that $w=(2,-1,a)$ is perpendicular to $u$

We require $u\perp w$, which means $u\cdot w = 0$. Using $u=(1,2,-1)$ and $w=(2,-1,a)$:

$$u\cdot w = 1\cdot 2 + 2\cdot(-1) + (-1)\cdot a = 2 - 2 - a = -a.$$

Setting this equal to zero gives:

$$-a = 0 \implies a = 0.$$

Thus, the required vector is $w=(2,-1,0)$.

## 3. Why $a=0$ works here

Notice that the first two coordinates of $u=(1,2,-1)$ and $w=(2,-1,a)$ already cancel in the dot product:

$$1\cdot 2 + 2\cdot(-1) = 2 - 2 = 0.$$

Because the horizontal ($xy$) parts are already orthogonal, the third product $(-1)\cdot a$ must also be $0$ for the total dot product to vanish. Since $-1\neq 0$, we must have $a=0$.

## Quick verification

1. **Direct dot product check for $w=(2,-1,0)$:**
   $$u\cdot w = (1,2,-1)\cdot(2,-1,0) = 1(2) + 2(-1) + (-1)(0) = 2 - 2 + 0 = 0.\quad \checkmark$$
2. **Pythagorean theorem check:** Two vectors $u$ and $w$ are perpendicular if and only if $\|u\|^2 + \|w\|^2 = \|u-w\|^2$. Here:
   $$\|u\|^2 = 1^2+2^2+(-1)^2 = 6,\qquad \|w\|^2 = 2^2+(-1)^2+0^2 = 5,$$
   $$\|u-w\|^2 = \|(-1,3,-1)\|^2 = (-1)^2+3^2+(-1)^2 = 11 = 6 + 5.\quad \checkmark$$

## A concrete example

The equation $u\cdot (x,y,z) = 0$, or

$$x + 2y - z = 0,$$

describes the entire **plane** of vectors through the origin perpendicular to $u=(1,2,-1)$. Once we fix $x=2$ and $y=-1$, we are asking at what height $z=a$ the vertical line $(2,-1,z)$ pierces that plane:

$$2 + 2(-1) - a = 0 \implies a = 0.$$

For $v=(2,-1,3)$, the height is $z=3$ instead of $0$, which is why $v$ misses the perpendicular plane and gives $u\cdot v = -3$.

## How I would explain this in class

> Two nonzero vectors are perpendicular exactly when their dot product is zero. For $u=(1,2,-1)$ and $v=(2,-1,3)$, we get $u\cdot v = 2-2-3 = -3 \neq 0$, so they are not perpendicular. To make $w=(2,-1,a)$ perpendicular to $u$, we solve $u\cdot w = 2-2-a = 0$, which immediately gives $a=0$.

## Related workbook topics

- [Exercise 5: Angle between vectors](problem_05_solution.md)
- [Exercise 9: Cross product as a perpendicular direction](problem_09_solution.md)
