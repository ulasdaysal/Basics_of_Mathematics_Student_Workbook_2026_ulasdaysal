# Exercise 6. Angle Between Planes

## The question

Given

$$\Pi_1:x+y+z=1,\qquad \Pi_2:x-y=2.$$

First use the normal vectors to decide whether the planes are parallel. If not, compute the angle between them and explain why the normal vectors alone are enough for this calculation.

## Before calculating: what idea do we need?

Every plane $\Pi:ax+by+cz=d$ has a normal vector $n=(a,b,c)$ perpendicular to it. When two planes tilt in space, their normal vectors tilt by the exact same amount: rotating two planes together with their normals in a cross-section perpendicular to their intersection line shows that the dihedral angle $\theta\in[0,\frac{\pi}{2}]$ between $\Pi_1$ and $\Pi_2$ satisfies

$$\cos\theta=\frac{|n_1\cdot n_2|}{\|n_1\|\,\|n_2\|}.$$

In particular:
- Two planes are **parallel** if and only if $n_1$ and $n_2$ are scalar multiples of each other.
- Two planes are **perpendicular** ($\theta=90^\circ$) if and only if $n_1\cdot n_2=0$.

## 1. Reading the normal vectors and testing parallelism

From the equations $\Pi_1:1x+1y+1z=1$ and $\Pi_2:1x-1y+0z=2$, the normal vectors are

$$n_1=(1,1,1),\qquad n_2=(1,-1,0).$$

Are $n_1$ and $n_2$ parallel? For $n_1=k\,n_2$ we would need $1=k\cdot0$ in the third coordinate, which is impossible. Therefore, the normal vectors are **not parallel**, so the planes $\Pi_1$ and $\Pi_2$ **are not parallel** and must intersect along a line.

## 2. Computing the dot product and the angle

Now we compute the dot product of $n_1$ and $n_2$:

$$n_1\cdot n_2=1\cdot1+1\cdot(-1)+1\cdot0=1-1+0=0.$$

Since $n_1\cdot n_2=0$, we have

$$\cos\theta=\frac{|n_1\cdot n_2|}{\|n_1\|\,\|n_2\|}=\frac{0}{\sqrt{3}\,\sqrt{2}}=0\implies \theta=\frac{\pi}{2}=90^\circ.$$

The two planes are **perpendicular** (orthogonal).

## 3. Why the normal vectors alone are enough

Notice that we never needed the right-hand constants $1$ and $2$, nor did we need to find the line of intersection:
1. Changing the constant $d$ in $ax+by+cz=d$ only translates a plane parallel to itself without changing its tilt.
2. In a plane perpendicular to the intersection line of $\Pi_1$ and $\Pi_2$, the two planes appear as two rays, and $n_1,n_2$ are obtained by rotating those rays by $90^\circ$. Rotating two lines by $90^\circ$ preserves the angle between them.

## Quick verification

Let us verify that the normal vector of $\Pi_2$, namely $n_2=(1,-1,0)$, is actually a direction vector **inside** $\Pi_1$:
- Take the point $A=(1,0,0)$ on $\Pi_1$ (since $1+0+0=1$).
- Move from $A$ along $n_2=(1,-1,0)$ to $B=A+n_2=(2,-1,0)$.
- Check whether $B$ lies on $\Pi_1$: $2+(-1)+0=1$. ✓

Because $\Pi_1$ contains the line in the direction of $n_2$ (which is perpendicular to $\Pi_2$), the plane $\Pi_1$ stands at a right angle to $\Pi_2$. ✓

## A concrete example

What if the second plane were $\Pi_3:x+y=2$ with normal $n_3=(1,1,0)$ instead? Then:

$$n_1\cdot n_3=(1,1,1)\cdot(1,1,0)=2,\qquad \|n_1\|=\sqrt{3},\qquad \|n_3\|=\sqrt{2},$$

so the acute angle between $\Pi_1$ and $\Pi_3$ would satisfy

$$\cos\theta=\frac{2}{\sqrt{6}}=\sqrt{\frac{2}{3}}\implies \theta=\arccos\sqrt{\frac{2}{3}}\approx 35.26^\circ.$$

By flipping the sign of $y$ in $\Pi_2:x-y=2$, the two terms in the dot product cancel ($1-1=0$), making $\Pi_1$ and $\Pi_2$ exactly perpendicular.

## How I would explain this in class

> To find how two planes meet, I just look at their normal vectors: $n_1=(1,1,1)$ for the first plane and $n_2=(1,-1,0)$ for the second. They aren't multiples of each other, so the planes aren't parallel. Next, I take their dot product to find the angle between the normals—and since $(1,1,1)\cdot(1,-1,0)=1-1+0=0$, the normals are perpendicular! Because the angle between two planes equals the angle between their normals, the two planes meet at a $90^\circ$ angle.

## Related workbook topics

- [Exercise 3: Plane Through a Point with a Given Normal Vector](problem_03_solution.md)
- [Exercise 12: Intersection Line of Two Planes](problem_12_solution.md)
