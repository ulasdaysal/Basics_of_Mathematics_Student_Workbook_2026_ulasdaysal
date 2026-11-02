# Exercise 4. Plane Through Three Points

## The question

Find the equation of the plane through

$$A=(1,0,0),\quad B=(0,1,0),\quad C=(0,0,1).$$

First construct two vectors lying in the plane, and then use the cross product. Check the resulting equation on all three points.

## Before calculating: what idea do we need?

To write the equation of a plane, we need a point on the plane and a **normal vector** $n$ perpendicular to it. When we are given three non-collinear points $A,B,C$ instead of a normal vector:

1. We form two displacement vectors starting from one point, say $u=\overrightarrow{AB}=B-A$ and $v=\overrightarrow{AC}=C-A$. Both $u$ and $v$ lie flat inside the plane.
2. Because the cross product $u\times v$ is perpendicular to both $u$ and $v$, the vector $n=u\times v$ is perpendicular to the entire plane!
3. Once we have $n$, we use $n\cdot(X-A)=0$ to write the plane's equation.

## 1. Constructing two vectors in the plane

Using $A=(1,0,0)$ as our anchor point, we compute the vectors to $B=(0,1,0)$ and $C=(0,0,1)$:

$$u=\overrightarrow{AB}=B-A=(0-1,\,1-0,\,0-0)=(-1,1,0),$$

$$v=\overrightarrow{AC}=C-A=(0-1,\,0-0,\,1-0)=(-1,0,1).$$

Since $u$ and $v$ are not scalar multiples of each other, the three points $A,B,C$ are not collinear and define a unique plane.

## 2. Finding the normal vector via the cross product

We compute $n=u\times v$:

$$n=u\times v=\det\begin{pmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\-1&1&0\\-1&0&1\end{pmatrix}=\mathbf{i}(1\cdot1-0\cdot0)-\mathbf{j}((-1)\cdot1-0\cdot(-1))+\mathbf{k}((-1)\cdot0-1\cdot(-1)).$$

Simplifying each component:

$$n=(1,\,-(-1),\,1)=(1,1,1).$$

## 3. Writing the equation of the plane

Using the normal vector $n=(1,1,1)$ and the point $A=(1,0,0)$:

$$1(x-1)+1(y-0)+1(z-0)=0\implies x+y+z=1.$$

## Quick verification

Let us check that all three given points satisfy $x+y+z=1$, and that $n$ is orthogonal to $u$ and $v$:

- Point $A=(1,0,0)$: $1+0+0=1$. ✓
- Point $B=(0,1,0)$: $0+1+0=1$. ✓
- Point $C=(0,0,1)$: $0+0+1=1$. ✓
- Orthogonality with $u$: $n\cdot u=(1,1,1)\cdot(-1,1,0)=-1+1+0=0$. ✓
- Orthogonality with $v$: $n\cdot v=(1,1,1)\cdot(-1,0,1)=-1+0+1=0$. ✓

## A concrete example

The three points $A=(1,0,0)$, $B=(0,1,0)$, and $C=(0,0,1)$ are the unit intercepts on the $x$-, $y$-, and $z$-axes. Their centroid (average) is

$$G=\frac{A+B+C}{3}=\left(\frac{1}{3},\frac{1}{3},\frac{1}{3}\right).$$

Substituting $G$ into $x+y+z=1$ gives $\frac{1}{3}+\frac{1}{3}+\frac{1}{3}=1$, and notice that the position vector $\overrightarrow{OG}=\left(\frac{1}{3},\frac{1}{3},\frac{1}{3}\right)$ is parallel to the normal $n=(1,1,1)$—the plane faces the first octant symmetrically.

## How I would explain this in class

> We have three points on the plane, $A,B,C$, so we first create two vectors inside the plane: $\overrightarrow{AB}=(-1,1,0)$ and $\overrightarrow{AC}=(-1,0,1)$. To get a normal vector perpendicular to both of them, we take their cross product, which gives $n=(1,1,1)$. That tells us the plane has the form $x+y+z=d$, and plugging in $(1,0,0)$ immediately gives $d=1$, so the equation is $x+y+z=1$.

## Related workbook topics

- [Exercise 3: Plane Through a Point with a Given Normal Vector](problem_03_solution.md)
- [Exercise 11: Plane Containing a Line and a Point](problem_11_solution.md)
