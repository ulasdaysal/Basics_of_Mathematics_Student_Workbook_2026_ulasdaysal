# Exercise 7. Linear Dependence Without Heavy Computation

## The question

Given

$$u=(1,2,3),\qquad v=(2,4,6),\qquad w=(0,1,1).$$

Identify a specific relation between $u$ and $v$, decide whether the three vectors can be linearly independent, and explain why no long calculation is needed.

## Before calculating: what idea do we need?

Vectors $v_1, v_2, v_3$ are **linearly dependent** if there exist scalars $c_1, c_2, c_3$, **not all zero**, such that

$$c_1 v_1 + c_2 v_2 + c_3 v_3 = \mathbf{0}.$$

A key structural rule is:

> **If any subset of a collection of vectors is already linearly dependent (for instance, if two vectors are scalar multiples of each other), then the entire collection is automatically linearly dependent.**

We can simply assign coefficient $0$ to all the remaining vectors.

## 1. Identifying the relation between $u$ and $v$

Comparing the coordinates of $u=(1,2,3)$ and $v=(2,4,6)$ term by term:

$$v = (2,4,6) = (2\cdot 1,\, 2\cdot 2,\, 2\cdot 3) = 2(1,2,3) = 2u.$$

Equivalently,

$$2u - v = (0,0,0) = \mathbf{0}.$$

Geometrically, $u$ and $v$ are **collinear**: they lie on the exact same line through the origin, with $v$ having twice the length of $u$.

## 2. Deciding whether $u,v,w$ can be linearly independent

No—the three vectors $u,v,w$ are **linearly dependent** (so they **cannot** be linearly independent).

Indeed, using the relation $2u-v=\mathbf{0}$, we can write a nontrivial linear combination of all three vectors by giving $w$ the coefficient $0$:

$$2u - 1v + 0w = \mathbf{0}.$$

Because the coefficients $(c_1,c_2,c_3)=(2,-1,0)$ are not all zero, the definition of linear dependence is satisfied immediately.

## 3. Why no long calculation is needed

Normally, testing three vectors in $\mathbb R^3$ for linear independence might involve row-reducing a $3\times 3$ matrix or computing a $3\times 3$ determinant. Here, no such calculation is needed because:

1. **Redundancy is already visible in the first two vectors:** Since $v=2u$, $v$ contributes no new direction beyond $u$. Together, $\operatorname{span}(u,v)$ is just a 1D line.
2. **Adding one more vector $w$ can increase the dimension by at most $1$:** A line plus one vector $w$ can span at most a 2D plane in $\mathbb R^3$, never all of $\mathbb R^3$. Three vectors trapped inside a 2D plane are always linearly dependent.

## Quick verification

1. **Direct substitution into the linear combination:**
   $$2u - 1v + 0w = 2(1,2,3) - 1(2,4,6) + 0(0,1,1) = (2-2,\, 4-4,\, 6-6) = (0,0,0).\quad \checkmark$$
2. **Determinant check:** If we place $u,v,w$ as the rows of a $3\times 3$ matrix,
   $$\det\begin{pmatrix}1&2&3\\2&4&6\\0&1&1\end{pmatrix} = 0$$
   because Row 2 is twice Row 1, and any matrix with proportional rows has determinant $0$. $\checkmark$

## A concrete example

Think of $u,v,w$ as three movement instructions in 3D space:

- Instruction $u$: step along $(1,2,3)$.
- Instruction $v$: step along $(2,4,6)$—which is just **two steps of instruction $u$**.
- Instruction $w$: step along $(0,1,1)$.

Because instruction $v$ duplicates the direction of instruction $u$, you only have **two independent directions** of motion ($u$ and $w$), not three. You are confined to the plane spanned by $u$ and $w$, and taking $2$ steps of $u$ followed by $-1$ step of $v$ brings you right back to the origin without ever using $w$.

## How I would explain this in class

> Before setting up a matrix or a determinant, always look at the vectors first. Here $v=(2,4,6)$ is simply $2u$. That means $2u - v + 0w = \mathbf{0}$ is a nontrivial linear combination equal to the zero vector, with coefficients $(2,-1,0)\neq(0,0,0)$. Whenever two vectors in a set are proportional, the whole set is automatically linearly dependent—no row reduction or determinant calculation is needed.

## Related workbook topics

- [Exercise 8: Linear combination and checking the result](problem_08_solution.md)
- [Exercise 15: Comparing directions using the cosine of the angle](problem_15_solution.md)
