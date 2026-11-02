# Exercise 12. Intersection Line of Two Planes

## The question

Find a parametric equation of the line that is the intersection of

$$x+y+z=3,\qquad x-y+z=1.$$

Find its direction vector in two ways: from the system of equations and from the cross product of the normal vectors. Compare the results.

## Before calculating: what idea do we need?

When two non-parallel planes $\Pi_1$ and $\Pi_2$ intersect, their common points form a line $L$. We can find the direction vector $v$ of this line from two perspectives:

1. **Algebraically (from the system of equations):** Solving the two linear equations in three unknowns leaves one free parameter $t$. The vector of coefficients of $t$ in $(x(t),y(t),z(t))$ is a direction vector of the line.
2. **Geometrically (from the normal vectors):** Because the intersection line $L$ lies in **both** planes simultaneously, its direction vector $v$ must be perpendicular to both normal vectors $n_1$ and $n_2$. Therefore, $v$ is parallel to the cross product $n_1\times n_2$.

## 1. Method 1: Solving the system of equations

We solve the system

$$\begin{cases}x+y+z=3,\\x-y+z=1.\end{cases}$$

Subtracting the second equation from the first eliminates $x$ and $z$:

$$(x+y+z)-(x-y+z)=3-1\implies 2y=2\implies y=1.$$

Substituting $y=1$ back into the first equation gives

$$x+1+z=3\implies x+z=2.$$

Choosing $z=t\in\mathbb{R}$ as our free parameter gives $x=2-t$. Thus, the parametric equation of the intersection line is

$$(x,y,z)=(2-t,\,1,\,t)=(2,1,0)+t(-1,0,1),\qquad t\in\mathbb{R}.$$

From this parametric form, we read off:
- A point on the line: $P_0=(2,1,0)$,
- Direction vector (Method 1): $v_1=(-1,0,1)$.

## 2. Method 2: Cross product of the normal vectors

The normal vectors of the two planes are

$$n_1=(1,1,1),\qquad n_2=(1,-1,1).$$

Taking their cross product gives a vector perpendicular to both normals:

$$v_2=n_1\times n_2=\det\begin{pmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\1&1&1\\1&-1&1\end{pmatrix}=\mathbf{i}(1-(-1))-\mathbf{j}(1-1)+\mathbf{k}(-1-1)=(2,0,-2).$$

## 3. Comparing the two results

Comparing the direction vector $v_1=(-1,0,1)$ from Method 1 and $v_2=(2,0,-2)$ from Method 2:

$$v_2=(2,0,-2)=-2(-1,0,1)=-2v_1.$$

The two vectors are non-zero scalar multiples of each other, so they define the **exact same line direction**! (Moving along $v_2$ simply traverses the same line twice as fast in the opposite orientation as $v_1$.)

## Quick verification

Let us check that the general point $(x,y,z)=(2-t,\,1,\,t)$ satisfies both plane equations for all $t\in\mathbb{R}$:

1. **First plane $x+y+z=3$:**
   $$(2-t)+1+t=3.\text{ ✓}$$
2. **Second plane $x-y+z=1$:**
   $$(2-t)-1+t=1.\text{ ✓}$$
3. **Orthogonality of $v_1=(-1,0,1)$ with both normals:**
   $$v_1\cdot n_1=(-1,0,1)\cdot(1,1,1)=0,\qquad v_1\cdot n_2=(-1,0,1)\cdot(1,-1,1)=0.\text{ ✓}$$

## A concrete example

What if we had chosen $x=s$ as our free parameter in Method 1 instead of $z=t$? From $x+z=2$ we would get $z=2-s$, giving

$$(x,y,z)=(s,\,1,\,2-s)=(0,1,2)+s(1,0,-1).$$

Here the starting point is $(0,1,2)$ (which corresponds to $t=2$ in our first parameterization) and the direction vector is $(1,0,-1)=-v_1=\frac{1}{2}v_2$. All of these parameterizations describe the exact same geometric line in $\mathbb{R}^3$.

## How I would explain this in class

> To find the intersection line of $x+y+z=3$ and $x-y+z=1$, I first subtract the equations to get $2y=2$, so $y=1$ is fixed, which leaves $x+z=2$. Setting $z=t$ gives $x=2-t$, so the line is $(2,1,0)+t(-1,0,1)$ with direction vector $(-1,0,1)$. Geometrically, since the intersection line lies in both planes, its direction must be perpendicular to both normal vectors $n_1=(1,1,1)$ and $n_2=(1,-1,1)$. Their cross product is $n_1\times n_2=(2,0,-2)$, which is just $-2$ times $(-1,0,1)$—both methods give the exact same direction.

## Related workbook topics

- [Exercise 5: Relative Position of Two Lines](problem_05_solution.md)
- [Exercise 6: Angle Between Planes](problem_06_solution.md)
