# Exercise 13. Do Four Points Lie in One Plane?

## The question

Given

$$A=(0,0,0),\qquad B=(1,2,0),\qquad C=(0,1,1),\qquad D=(2,5,1).$$

1. Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$.
2. Find $n=\overrightarrow{AB}\times\overrightarrow{AC}$.
3. Construct $\overrightarrow{AD}$ and check whether $\overrightarrow{AD}\cdot n=0$.
4. Based on this, decide whether $D$ lies in the plane determined by $A,B,C$, and justify the criterion.

## Before calculating: what idea do we need?

Suppose $A,B,C$ are three non-collinear points in $\mathbb R^3$. The cross product

$$n = \overrightarrow{AB}\times\overrightarrow{AC}$$

is a nonzero **normal vector** perpendicular to the plane through $A,B,C$.

Now take any fourth point $D$. The plane through $A,B,C$ consists of all points whose displacement from $A$ is perpendicular to $n$. Therefore:

$$D \text{ lies in the plane } ABC \iff \overrightarrow{AD} \perp n \iff \overrightarrow{AD}\cdot n = 0.$$

Geometrically, $|\overrightarrow{AD}\cdot n|$ is the volume of the parallelepiped spanned by $\overrightarrow{AB},\overrightarrow{AC},\overrightarrow{AD}$; this volume is zero if and only if all three vectors lie flat in the same plane.

## 1. Constructing $\overrightarrow{AB}$ and $\overrightarrow{AC}$

Since $A=(0,0,0)$, subtracting $A$ from $B=(1,2,0)$ and $C=(0,1,1)$ gives:

$$\overrightarrow{AB} = B - A = (1,2,0),$$

$$\overrightarrow{AC} = C - A = (0,1,1).$$

## 2. Finding the normal vector $n=\overrightarrow{AB}\times\overrightarrow{AC}$

We compute the cross product of $\overrightarrow{AB}=(1,2,0)$ and $\overrightarrow{AC}=(0,1,1)$:

$$n = \overrightarrow{AB}\times\overrightarrow{AC} = \begin{vmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\1&2&0\\0&1&1\end{vmatrix} = \left(\begin{vmatrix}2&0\\1&1\end{vmatrix},\; -\begin{vmatrix}1&0\\0&1\end{vmatrix},\; \begin{vmatrix}1&2\\0&1\end{vmatrix}\right).$$

Evaluating the $2\times 2$ determinants:

- First component: $2(1) - 0(1) = 2$,
- Second component: $-(1(1) - 0(0)) = -1$,
- Third component: $1(1) - 2(0) = 1$.

Thus,

$$n = (2,-1,1).$$

*(Quick check: $n\cdot\overrightarrow{AB} = 2-2+0=0$ and $n\cdot\overrightarrow{AC} = 0-1+1=0$.)*

## 3. Constructing $\overrightarrow{AD}$ and checking $\overrightarrow{AD}\cdot n=0$

For $D=(2,5,1)$ and $A=(0,0,0)$:

$$\overrightarrow{AD} = D - A = (2,5,1).$$

Taking the dot product with $n=(2,-1,1)$:

$$\overrightarrow{AD}\cdot n = (2,5,1)\cdot(2,-1,1) = 2\cdot 2 + 5\cdot(-1) + 1\cdot 1 = 4 - 5 + 1 = 0.$$

## 4. Decision and justification of the criterion

Because $\overrightarrow{AD}\cdot n = 0$, the point $D$ **does lie in the plane** determined by $A,B,C$ (the four points $A,B,C,D$ are **coplanar**).

**Why this criterion works:**
Since $n=\overrightarrow{AB}\times\overrightarrow{AC}=(2,-1,1)\neq\mathbf{0}$, the vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ span a 2D plane through $A$, and $n$ is perpendicular to that plane. The orthogonal complement of the nonzero vector $n$ in $\mathbb R^3$ is a 2D subspace—namely, the exact plane spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$. Therefore, $\overrightarrow{AD}\cdot n=0$ means $\overrightarrow{AD}$ has zero component in the normal direction (zero height above or below the plane $ABC$), so $D$ lies inside the plane $ABC$.

## Quick verification

If $D$ lies in the plane spanned by $\overrightarrow{AB}=(1,2,0)$ and $\overrightarrow{AC}=(0,1,1)$ through $A$, then $\overrightarrow{AD}=(2,5,1)$ must be an explicit linear combination of $\overrightarrow{AB}$ and $\overrightarrow{AC}$:

$$\overrightarrow{AD} = \alpha\overrightarrow{AB} + \beta\overrightarrow{AC} = \alpha(1,2,0) + \beta(0,1,1) = (\alpha,\, 2\alpha+\beta,\, \beta).$$

Comparing with $(2,5,1)$ immediately gives $\alpha=2$ and $\beta=1$, and the middle coordinate satisfies $2(2)+1 = 5$! Indeed:

$$2\overrightarrow{AB} + 1\overrightarrow{AC} = 2(1,2,0) + (0,1,1) = (2,5,1) = \overrightarrow{AD}.\quad \checkmark$$

## A concrete example

What if the fourth point were $D'=(2,5,2)$, just $1$ unit higher in the $z$-direction than $D=(2,5,1)$? Then $\overrightarrow{AD'}=(2,5,2)$, and

$$\overrightarrow{AD'}\cdot n = (2,5,2)\cdot(2,-1,1) = 4 - 5 + 2 = 1 \neq 0.$$

That nonzero result ($1$) tells us immediately that $D'$ does **not** lie in the plane $ABC$—it sticks out of the plane on the side toward which $n$ points.

## How I would explain this in class

> First, $\overrightarrow{AB}=(1,2,0)$ and $\overrightarrow{AC}=(0,1,1)$ lie in the plane through $A,B,C$, so their cross product $n=\overrightarrow{AB}\times\overrightarrow{AC}=(2,-1,1)$ is a normal vector perpendicular to that plane. Next, we check whether $\overrightarrow{AD}=(2,5,1)$ is also perpendicular to $n$: $(2,5,1)\cdot(2,-1,1) = 4-5+1 = 0$. Because $\overrightarrow{AD}$ has zero component along the normal $n$, it does not rise above or dip below the plane—in fact, $\overrightarrow{AD}=2\overrightarrow{AB}+\overrightarrow{AC}$, so $D$ lies in the plane $ABC$.

## Related workbook topics

- [Exercise 8: Linear combination and checking the result](problem_08_solution.md)
- [Exercise 12: A normal vector to a plane](problem_12_solution.md)
