# Exercise 7. A Line Relative to a Plane

## The question

For

$$L:(x,y,z)=(1,1,0)+t(1,-1,0),\qquad \Pi:x+y+z=2,$$

determine whether the line intersects the plane at one point, is parallel to it, or lies in it. Explain the role of the dot product of the direction vector and the normal vector.

## Before calculating: what idea do we need?

A line $L$ has a **direction vector** $v$ pointing along the line, whereas a plane $\Pi$ has a **normal vector** $n$ pointing **perpendicular** to the plane. Because $n$ is already rotated by $90^\circ$ relative to $\Pi$:

- The line is parallel to the plane (or lies in it) if and only if $v$ is **perpendicular** to $n$, which means
  $$v\cdot n=0.$$
- If $v\cdot n\neq 0$, the line is not parallel to the plane and therefore pierces it at **exactly one point**.

When $v\cdot n=0$, we distinguish between "strictly parallel" and "lies in the plane" by checking whether the starting point $P_0$ of the line satisfies the plane's equation.

## 1. Extracting the vectors and computing their dot product

From the given equations:
- Starting point of $L$: $P_0=(1,1,0)$,
- Direction vector of $L$: $v=(1,-1,0)$,
- Normal vector of $\Pi$: $n=(1,1,1)$.

Their dot product is

$$v\cdot n=(1,-1,0)\cdot(1,1,1)=1\cdot1+(-1)\cdot1+0\cdot1=1-1+0=0.$$

Because $v\cdot n=0$, the direction of $L$ is perpendicular to the normal of $\Pi$, so $L$ moves parallel to $\Pi$ (it either misses $\Pi$ completely or lies entirely inside $\Pi$).

## 2. Testing the starting point $P_0$ in the plane

We substitute $P_0=(1,1,0)$ into the plane equation $x+y+z=2$:

$$1+1+0=2.$$

Since $P_0$ lies on $\Pi$ and the line moves in a direction parallel to $\Pi$, **every point of $L$ stays in $\Pi$**. Thus, the line $L$ **lies in the plane $\Pi$**.

## 3. Algebraic view: substituting the general point of $L$ into $\Pi$

If we substitute $(x,y,z)=(1+t,\,1-t,\,0)$ directly into $x+y+z=2$, we get

$$(1+t)+(1-t)+0=2\implies 2+0\cdot t=2\implies 2=2.$$

Notice that the coefficient of $t$ is $1-1+0=v\cdot n=0$, and the constant term is $1+1+0=2$. Because $2=2$ holds for **every** $t\in\mathbb{R}$, the entire line lies in $\Pi$.

## Quick verification

Let us pick two other values of $t$ on $L$ and check that those points also satisfy $x+y+z=2$:

- For $t=1$: $P_1=(1+1,\,1-1,\,0)=(2,0,0)$, and $2+0+0=2$. ✓
- For $t=-3$: $P_{-3}=(1-3,\,1+3,\,0)=(-2,4,0)$, and $-2+4+0=2$. ✓

## A concrete example

What if the plane were $\Pi':x+y+z=5$ instead, with the same normal vector $n=(1,1,1)$?
- We would still have $v\cdot n=0$, so the line moves parallel to $\Pi'$.
- However, plugging in $P_0=(1,1,0)$ gives $1+1+0=2\neq 5$ (the equation for $t$ becomes $2+0\cdot t=5$, which has no solution).

In that case, $L$ would be **strictly parallel** to $\Pi'$ with no common points.

## How I would explain this in class

> To see how the line $L$ and plane $\Pi$ relate, I take the dot product of the line's direction vector $v=(1,-1,0)$ and the plane's normal vector $n=(1,1,1)$. Since $v\cdot n=1-1+0=0$, the line's direction is perpendicular to the plane's normal, which means the line runs parallel to the plane. To decide whether it hovers outside the plane or sits inside it, I plug the line's starting point $(1,1,0)$ into $x+y+z=2$. Since $1+1+0=2$ works, the entire line lies inside the plane.

## Related workbook topics

- [Exercise 8: Intersection Point of a Line and a Plane](problem_08_solution.md)
- [Exercise 15: Complete Classification of a Line Relative to a Plane](problem_15_solution.md)
