# Exercise 8. Linear Combination and Checking the Result

## The question

Check whether $w=(5,1)$ can be written as

$$w=au+bv,$$

where $u=(1,1)$ and $v=(2,-1)$. If so, find $a,b$, reconstruct $w$ from them, and explain the geometric meaning of the existence of such coefficients.

## Before calculating: what idea do we need?

Writing a target vector $w$ as a **linear combination**

$$w = au + bv$$

means finding how much we need to stretch or shrink $u$ (by factor $a$) and $v$ (by factor $b$) so that their vector sum reaches $w$.

In $\mathbb R^2$, equating the two coordinates of $au+bv$ and $w$ turns the single vector equation into a system of two linear equations in the two unknowns $a$ and $b$. Since $u=(1,1)$ and $v=(2,-1)$ are not scalar multiples of each other, they point in two different directions and span the entire plane $\mathbb R^2$.

## 1. Setting up the system of equations

We substitute $u=(1,1)$, $v=(2,-1)$, and $w=(5,1)$ into $au+bv=w$:

$$a(1,1) + b(2,-1) = (5,1) \iff (a+2b,\, a-b) = (5,1).$$

Comparing the first and second coordinates gives the linear system:

$$\begin{cases}
a + 2b = 5, \\
a - b = 1.
\end{cases}$$

## 2. Solving for $a$ and $b$

From the second equation, we express $a$ in terms of $b$:

$$a = b + 1.$$

Substituting $a = b + 1$ into the first equation:

$$(b + 1) + 2b = 5 \implies 3b + 1 = 5 \implies 3b = 4 \implies b = \frac{4}{3}.$$

Now we find $a$:

$$a = \frac{4}{3} + 1 = \frac{7}{3}.$$

So $w$ **can** be written as $au+bv$, with unique coefficients $a = \frac{7}{3}$ and $b = \frac{4}{3}$.

## 3. Reconstructing $w$ from $a$ and $b$

We compute $\frac{7}{3}u + \frac{4}{3}v$ directly:

$$\frac{7}{3}(1,1) + \frac{4}{3}(2,-1) = \left(\frac{7}{3},\, \frac{7}{3}\right) + \left(\frac{8}{3},\, -\frac{4}{3}\right) = \left(\frac{7+8}{3},\, \frac{7-4}{3}\right) = \left(\frac{15}{3},\, \frac{3}{3}\right) = (5,1) = w.$$

## 4. Geometric meaning of the existence of $a$ and $b$

Geometrically, the existence of $a=\frac73$ and $b=\frac43$ means:

1. **$u$ and $v$ form a basis (a skewed coordinate grid) for $\mathbb R^2$:** Because $u=(1,1)$ and $v=(2,-1)$ are non-collinear, we can reach any point in the plane by moving exclusively along the directions of $u$ and $v$.
2. **Parallelogram decomposition:** If we draw lines through the origin along $u$ and $v$, and lines through $w=(5,1)$ parallel to $u$ and $v$, we form a parallelogram with vertices $(0,0)$, $au=\left(\frac73,\frac73\right)$, $bv=\left(\frac83,-\frac43\right)$, and $w=(5,1)$.
3. **New coordinates:** The pair $(a,b)=\left(\frac73,\frac43\right)$ are the coordinates of $w$ in the basis $\{u,v\}$: to reach $(5,1)$, take $\frac73$ steps of $u$ followed by $\frac43$ steps of $v$.

## Quick verification

Let us check both scalar equations with $a=\frac73$ and $b=\frac43$:

- First coordinate: $a + 2b = \frac{7}{3} + 2\left(\frac{4}{3}\right) = \frac{7+8}{3} = \frac{15}{3} = 5.\quad \checkmark$
- Second coordinate: $a - b = \frac{7}{3} - \frac{4}{3} = \frac{3}{3} = 1.\quad \checkmark$

We can also check using Cramer's rule:

$$\det\begin{pmatrix}1&2\\1&-1\end{pmatrix} = -1 - 2 = -3 \neq 0,$$

$$a = \frac{\det\begin{pmatrix}5&2\\1&-1\end{pmatrix}}{-3} = \frac{-5-2}{-3} = \frac{7}{3},\qquad b = \frac{\det\begin{pmatrix}1&5\\1&1\end{pmatrix}}{-3} = \frac{1-5}{-3} = \frac{4}{3}.\quad \checkmark$$

## A concrete example

Compare this with standard coordinates: when we write $w=(5,1)$, we are writing

$$(5,1) = 5(1,0) + 1(0,1),$$

which uses the standard horizontal and vertical unit vectors $e_1=(1,0)$ and $e_2=(0,1)$. When we instead use the tilted axes $u=(1,1)$ and $v=(2,-1)$, the exact same geometric arrow $w$ is described by the recipe $\frac73 u + \frac43 v$.

## How I would explain this in class

> Writing $w=au+bv$ gives the system $a+2b=5$ and $a-b=1$. Subtracting the second equation from the first gives $3b=4$, so $b=\frac43$ and $a=b+1=\frac73$. Reconstructing $\frac73(1,1)+\frac43(2,-1)$ gives $(\frac{15}{3},\frac33)=(5,1)=w$. Geometrically, because $u$ and $v$ point in different directions in $\mathbb R^2$, they act as a tilted coordinate grid, and $(\frac73,\frac43)$ tells us how far to travel along each direction to land on $w$.

## Related workbook topics

- [Exercise 1: Vector operations and their meaning](problem_01_solution.md)
- [Exercise 7: Linear dependence without heavy computation](problem_07_solution.md)
