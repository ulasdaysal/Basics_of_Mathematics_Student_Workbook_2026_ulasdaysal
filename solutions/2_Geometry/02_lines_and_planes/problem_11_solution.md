# Exercise 11. Plane Containing a Line and a Point

## The question

Find the equation of the plane containing

$$(x,y,z)=(1,0,2)+t(1,1,-1)$$

and the point $P=(0,2,1)$. Check that both the entire line and the point lie in the plane you obtain.

## Before calculating: what idea do we need?

To determine a plane, we need a point on it and two linearly independent direction vectors lying inside it (whose cross product gives the plane's normal vector $n$):

1. Since the entire line $L:P_0+tv$ lies in the plane, the line's **direction vector** $v=(1,1,-1)$ is automatically our first direction vector in the plane, and $P_0=(1,0,2)$ is a point in the plane.
2. To get a second direction in the plane, we connect the point $P_0$ on the line to the external point $P=(0,2,1)$, forming $u=\overrightarrow{P_0P}=P-P_0$.
3. The cross product $n=v\times u$ is then perpendicular to both $v$ and $u$, giving the normal vector of the plane.

## 1. Constructing two independent directions in the plane

From the line $(x,y,z)=(1,0,2)+t(1,1,-1)$, we read off:
- A point on the line: $P_0=(1,0,2)$,
- First direction vector in the plane: $v=(1,1,-1)$.

Connecting $P_0=(1,0,2)$ to $P=(0,2,1)$ gives our second vector in the plane:

$$u=\overrightarrow{P_0P}=P-P_0=(0-1,\,2-0,\,1-2)=(-1,2,-1).$$

Since $v$ and $u$ are not scalar multiples of each other, $P$ does not lie on $L$, so $L$ and $P$ span a unique plane.

## 2. Computing the normal vector via the cross product

We take the cross product $n=v\times u$:

$$n=v\times u=\det\begin{pmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\1&1&-1\\-1&2&-1\end{pmatrix}=\mathbf{i}(1(-1)-(-1)(2))-\mathbf{j}(1(-1)-(-1)(-1))+\mathbf{k}(1(2)-1(-1)).$$

Evaluating each component:

$$n=(-1+2,\,-(-1-1),\,2+1)=(1,2,3).$$

## 3. Writing the equation of the plane

Using the normal vector $n=(1,2,3)$ and the point $P_0=(1,0,2)$:

$$1(x-1)+2(y-0)+3(z-2)=0\implies x-1+2y+3z-6=0,$$

which simplifies to

$$x+2y+3z=7.$$

## Quick verification

Let us verify that both the external point $P$ and every point of the line $L$ satisfy $x+2y+3z=7$:

1. **Check the point $P=(0,2,1)$:**
   $$0+2(2)+3(1)=0+4+3=7.\text{ ✓}$$
2. **Check the entire line $L:(1+t,\,t,\,2-t)$ for all $t\in\mathbb{R}$:**
   $$(1+t)+2(t)+3(2-t)=1+t+2t+6-3t=7+0\cdot t=7.\text{ ✓}$$
   Because $t$ cancels out completely and leaves the identity $7=7$, every point of the line lies in the plane.

## A concrete example

Another way to view this problem is as a "plane through three points": we already have $P=(0,2,1)$, and we can pick any two points on the line $L$, say
- at $t=0$: $P_0=(1,0,2)$,
- at $t=1$: $P_1=(2,1,1)$.

Notice that $\overrightarrow{P_0P_1}=P_1-P_0=(1,1,-1)$ is just the direction vector $v$, so finding the plane through $P_0,P_1,P$ leads to the exact same cross product $v\times\overrightarrow{P_0P}=(1,2,3)$ and the same plane $x+2y+3z=7$.

## How I would explain this in class

> A plane needs two independent directions inside it so we can cross them to get a normal vector. The line immediately gives us one direction vector, $v=(1,1,-1)$, and a starting point $P_0=(1,0,2)$. To get a second direction in the plane, I form the vector from $P_0$ to the given point $P=(0,2,1)$, which is $u=(-1,2,-1)$. Crossing $v$ and $u$ gives the normal $n=(1,2,3)$, so the plane is $x+2y+3z=d$. Plugging in $P=(0,2,1)$ gives $d=7$, and substituting the line $(1+t,t,2-t)$ confirms that $t$ cancels out and gives $7$ for every $t$.

## Related workbook topics

- [Exercise 4: Plane Through Three Points](problem_04_solution.md)
- [Exercise 7: A Line Relative to a Plane](problem_07_solution.md)
