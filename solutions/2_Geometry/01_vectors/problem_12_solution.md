# Exercise 12. A Normal Vector to a Plane

## The question

Given $A=(1,0,2)$, $B=(2,1,0)$, and $C=(0,3,1)$. Construct two vectors lying in the plane, find a vector perpendicular to both, and check the perpendicularity using dot products.

## Before calculating: what idea do we need?

Three non-collinear points $A,B,C$ in $\mathbb R^3$ determine a unique plane. To find a **normal vector** $n$ (a vector perpendicular to the entire plane):

1. Pick one point (such as $A$) as an anchor and form two displacement vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ lying inside the plane.
2. Compute their cross product:
   $$n = \overrightarrow{AB}\times\overrightarrow{AC}.$$

Because $n$ is perpendicular to both spanning vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$, it is automatically perpendicular to every linear combination of them—and therefore perpendicular to every line in the plane.

## 1. Constructing two vectors in the plane

Using $A=(1,0,2)$ as the common starting point:

$$\overrightarrow{AB} = B - A = (2-1,\, 1-0,\, 0-2) = (1,1,-2),$$

$$\overrightarrow{AC} = C - A = (0-1,\, 3-0,\, 1-2) = (-1,3,-1).$$

Both $\overrightarrow{AB}$ and $\overrightarrow{AC}$ lie in the plane through $A,B,C$.

## 2. Finding a vector perpendicular to both

We compute the cross product $n = \overrightarrow{AB}\times\overrightarrow{AC}$:

$$n = \begin{vmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\1&1&-2\\-1&3&-1\end{vmatrix} = \left(\begin{vmatrix}1&-2\\3&-1\end{vmatrix},\; -\begin{vmatrix}1&-2\\-1&-1\end{vmatrix},\; \begin{vmatrix}1&1\\-1&3\end{vmatrix}\right).$$

Evaluating the three $2\times 2$ determinants carefully:

- First component: $1(-1) - (-2)(3) = -1 + 6 = 5$,
- Second component: $-(1(-1) - (-2)(-1)) = -(-1 - 2) = 3$,
- Third component: $1(3) - 1(-1) = 3 + 1 = 4$.

Therefore, a normal vector to the plane is

$$n = (5,3,4).$$

*(Note: because $n\neq(0,0,0)$, the three points $A,B,C$ are not collinear and genuinely determine a unique plane. Any nonzero scalar multiple of $(5,3,4)$ is also a valid normal vector.)*

## 3. Checking perpendicularity using dot products

We compute the dot products of $n=(5,3,4)$ with $\overrightarrow{AB}=(1,1,-2)$ and $\overrightarrow{AC}=(-1,3,-1)$:

$$n\cdot\overrightarrow{AB} = (5,3,4)\cdot(1,1,-2) = 5(1) + 3(1) + 4(-2) = 5 + 3 - 8 = 0,$$

$$n\cdot\overrightarrow{AC} = (5,3,4)\cdot(-1,3,-1) = 5(-1) + 3(3) + 4(-1) = -5 + 9 - 4 = 0.$$

Since both dot products vanish, $n=(5,3,4)$ is perpendicular to both $\overrightarrow{AB}$ and $\overrightarrow{AC}$.

## Quick verification

What about the third edge of the triangle, $\overrightarrow{BC} = C - B = (0-2,\, 3-1,\, 1-0) = (-2,2,1)$? It also lies in the plane, so $n$ must be perpendicular to $\overrightarrow{BC}$ as well:

$$n\cdot\overrightarrow{BC} = (5,3,4)\cdot(-2,2,1) = -10 + 6 + 4 = 0.\quad \checkmark$$

## A concrete example

Once we have the normal vector $n=(5,3,4)$ and the point $A=(1,0,2)$, we can write the **equation of the plane** through $A,B,C$ in one line: a point $P=(x,y,z)$ lies in the plane if and only if $\overrightarrow{AP}\perp n$, that is,

$$n\cdot(x-1,\, y-0,\, z-2) = 0 \iff 5(x-1) + 3y + 4(z-2) = 0 \iff 5x + 3y + 4z = 13.$$

Let us plug all three given points into $5x+3y+4z$:

- For $A=(1,0,2)$: $5(1)+3(0)+4(2) = 5+0+8 = 13$,
- For $B=(2,1,0)$: $5(2)+3(1)+4(0) = 10+3+0 = 13$,
- For $C=(0,3,1)$: $5(0)+3(3)+4(1) = 0+9+4 = 13$.

Every point in the plane has the exact same dot product $13$ with the normal vector $n=(5,3,4)$!

## How I would explain this in class

> To find a normal to the plane through $A,B,C$, we first anchor at $A$ and form two vectors inside the plane: $\overrightarrow{AB}=(1,1,-2)$ and $\overrightarrow{AC}=(-1,3,-1)$. Then we take their cross product, $\overrightarrow{AB}\times\overrightarrow{AC}=(5,3,4)$. Finally, we check our work with dot products: $(5,3,4)\cdot(1,1,-2)=5+3-8=0$ and $(5,3,4)\cdot(-1,3,-1)=-5+9-4=0$. Because $(5,3,4)$ is perpendicular to two non-parallel directions in the plane, it is perpendicular to the entire plane.

## Related workbook topics

- [Exercise 9: Cross product as a perpendicular direction](problem_09_solution.md)
- [Exercise 13: Do four points lie in one plane?](problem_13_solution.md)
