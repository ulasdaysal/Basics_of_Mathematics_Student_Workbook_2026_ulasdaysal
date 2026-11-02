# Exercise 5. Relative Position of Two Lines

## The question

Analyze the position of

$$L_1:(x,y,z)=(1,1,0)+t(1,2,1),$$

$$L_2:(x,y,z)=(2,0,1)+s(0,1,-1).$$

If they intersect, give the intersection point. If not, determine whether they are parallel or skew. Justify the classification.

## Before calculating: what idea do we need?

Two lines in three-dimensional space can be in one of four states:
1. **Identical** (parallel direction vectors and share a point),
2. **Strictly parallel** (parallel direction vectors, no common point),
3. **Intersecting** (non-parallel direction vectors, and the system $L_1(t)=L_2(s)$ has a solution),
4. **Skew** (non-parallel direction vectors, and the system $L_1(t)=L_2(s)$ has no solution—the lines pass by each other in different planes).

So we first compare the direction vectors $v_1$ and $v_2$, and then test whether the three coordinate equations $x_1(t)=x_2(s)$, $y_1(t)=y_2(s)$, $z_1(t)=z_2(s)$ have a common solution $(t,s)$.

## 1. Comparing the direction vectors

The direction vectors of $L_1$ and $L_2$ are

$$v_1=(1,2,1),\qquad v_2=(0,1,-1).$$

If $v_1$ were a scalar multiple of $v_2$, say $(1,2,1)=k(0,1,-1)$, the first coordinate would require $1=0$, which is impossible. Thus $v_1$ and $v_2$ are **not parallel**, which rules out parallel or identical lines. The lines must either **intersect** or be **skew**.

## 2. Setting up the system for an intersection point

An intersection point occurs if there exist parameters $t,s\in\mathbb{R}$ that yield the same $(x,y,z)$:

$$(1,1,0)+t(1,2,1)=(2,0,1)+s(0,1,-1).$$

Writing this coordinate by coordinate gives three equations in two unknowns:

$$\begin{cases}(1)\quad 1+t=2,\\(2)\quad 1+2t=s,\\(3)\quad t=1-s.\end{cases}$$

## 3. Solving the first two equations and checking the third

From equation $(1)$:

$$1+t=2\implies t=1.$$

Substitute $t=1$ into equation $(2)$:

$$s=1+2(1)=3.$$

Now test $(t,s)=(1,3)$ in equation $(3)$:

$$\text{Left side: }t=1,\qquad \text{Right side: }1-s=1-3=-2.$$

Since $1\neq -2$, the third equation is violated! The system has **no solution**.

## 4. Classification

Because the direction vectors $v_1$ and $v_2$ are not parallel and the lines have no common point, the lines $L_1$ and $L_2$ are **skew**.

## Quick verification

We can independently verify skewness using the scalar triple product (determinant) of $\overrightarrow{P_1P_2}=P_2-P_1=(1,-1,1)$, $v_1=(1,2,1)$, and $v_2=(0,1,-1)$:

$$\det\begin{pmatrix}1&-1&1\\1&2&1\\0&1&-1\end{pmatrix}=1(-2-1)-(-1)(-1-0)+1(1-0)=-3-1+1=-3\neq 0.\text{ ✓}$$

A non-zero determinant means the three vectors do not lie in a single plane, so the two lines cannot be coplanar—hence they are skew. ✓

## A concrete example

At the parameters $t=1$ and $s=3$ where the $x$- and $y$-coordinates match, the points on the two lines are:
- on $L_1$ ($t=1$): $(1,1,0)+1(1,2,1)=(2,3,1)$,
- on $L_2$ ($s=3$): $(2,0,1)+3(0,1,-1)=(2,3,-2)$.

Looking down from above along the $z$-axis, the two lines appear to cross over the point $(x,y)=(2,3)$, but in 3D $L_1$ passes at height $z=1$ while $L_2$ passes underneath at height $z=-2$, missing each other by $3$ vertical units.

## How I would explain this in class

> First I check if the direction vectors $(1,2,1)$ and $(0,1,-1)$ are multiples of each other; they aren't, so the lines are not parallel. Next I try to make their coordinates equal: the $x$-equation $1+t=2$ forces $t=1$, and the $y$-equation $1+2t=s$ then forces $s=3$. But when I plug $t=1$ and $s=3$ into the $z$-coordinates, $L_1$ is at $z=1$ while $L_2$ is at $z=-2$. Since they aren't parallel and don't intersect, they pass over and under each other—they are skew lines.

## Related workbook topics

- [Exercise 2: A Line in Space](problem_02_solution.md)
- [Exercise 12: Intersection Line of Two Planes](problem_12_solution.md)
