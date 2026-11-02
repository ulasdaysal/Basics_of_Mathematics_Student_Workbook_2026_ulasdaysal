# Exercise 2. A Line in Space

## The question

Given

$$L:(x,y,z)=(2,-1,3)+t(1,2,-2).$$

State a point on the line and its direction vector, check whether $P=(4,3,-1)$ lies on $L$, and find the point corresponding to $t=-1$.

## Before calculating: what idea do we need?

A line in $\mathbb{R}^3$ in vector parametric form is written as

$$(x,y,z)=p_0+tv,\qquad t\in\mathbb{R},$$

where:
- $p_0=(x_0,y_0,z_0)$ is the **starting point** (reached at $t=0$),
- $v=(v_x,v_y,v_z)$ is the **direction vector** (how much $(x,y,z)$ changes when $t$ increases by $1$).

A point $P$ lies on the line $L$ if and only if there is a **single** parameter value $t$ that produces all three coordinates of $P$ simultaneously.

## 1. Point on the line and direction vector

Reading directly from $(x,y,z)=(2,-1,3)+t(1,2,-2)$:

- **A point on the line (for $t=0$):** $P_0=(2,-1,3)$.
- **Direction vector:** $v=(1,2,-2)$.

Written component by component, the parametric equations are

$$\begin{cases}x=2+t,\\y=-1+2t,\\z=3-2t,\end{cases}\qquad t\in\mathbb{R}.$$

## 2. Checking whether $P=(4,3,-1)$ lies on $L$

We set $(x,y,z)=(4,3,-1)$ and check whether all three equations yield the same $t$:

$$\begin{cases}2+t=4\implies t=2,\\-1+2t=3\implies 2t=4\implies t=2,\\3-2t=-1\implies -2t=-4\implies t=2.\end{cases}$$

Since the same value $t=2$ satisfies all three coordinate equations, the point $P=(4,3,-1)$ **does lie on the line $L$**.

## 3. Finding the point for $t=-1$

Substitute $t=-1$ into the parametric equation:

$$(x,y,z)=(2,-1,3)+(-1)(1,2,-2)=(2-1,\,-1-2,\,3+2)=(1,-3,5).$$

So the point corresponding to $t=-1$ is $Q=(1,-3,5)$.

## 4. Geometric meaning of the parameter $t$

The length of the direction vector is $\|v\|=\sqrt{1^2+2^2+(-2)^2}=\sqrt{9}=3$. Therefore:
- $P=(4,3,-1)$ at $t=2$ lies $2\|v\|=6$ units from $P_0$ in the direction of $v$,
- $Q=(1,-3,5)$ at $t=-1$ lies $1\cdot\|v\|=3$ units from $P_0$ in the opposite direction.

## Quick verification

- Check that the vector $\overrightarrow{P_0P}$ is a multiple of $v$:
  $$\overrightarrow{P_0P}=(4-2,\,3-(-1),\,-1-3)=(2,4,-4)=2(1,2,-2)=2v.\text{ ✓}$$
- Check that the vector $\overrightarrow{P_0Q}$ is $-v$:
  $$\overrightarrow{P_0Q}=(1-2,\,-3-(-1),\,5-3)=(-1,-2,2)=-1\cdot(1,2,-2)=-v.\text{ ✓}$$

## A concrete example

What happens when a point does **not** lie on $L$? Take $R=(4,3,0)$. Solving for $t$ coordinate by coordinate gives:
- from $x$: $2+t=4\implies t=2$,
- from $y$: $-1+2t=3\implies t=2$,
- from $z$: $3-2t=0\implies t=\frac{3}{2}$.

Because the third coordinate demands $t=\frac{3}{2}\neq 2$, the point $R=(4,3,0)$ misses the line (it is $1$ unit above the point $P=(4,3,-1)$).

## How I would explain this in class

> Think of $(2,-1,3)+t(1,2,-2)$ as a motion recipe: at time $t=0$ you start at $(2,-1,3)$, and every second your velocity is $(1,2,-2)$. To test if $(4,3,-1)$ is on the path, I solve $2+t=4$ to get $t=2$, and then verify that at $t=2$ the other two coordinates also match: $-1+2(2)=3$ and $3-2(2)=-1$. They do, so the point is on the line. For $t=-1$, I just step one unit backward from $(2,-1,3)$ by subtracting $(1,2,-2)$, landing at $(1,-3,5)$.

## Related workbook topics

- [Exercise 1: Line Through Two Points](problem_01_solution.md)
- [Exercise 5: Relative Position of Two Lines](problem_05_solution.md)
