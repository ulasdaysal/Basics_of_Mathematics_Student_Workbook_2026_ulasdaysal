# Exercise 12. Homogeneous System

## The question

Solve

$$\begin{cases}x+2y-z=0,\\2x+4y-2z=0,\\x-y+2z=0.\end{cases}$$

Give all solutions in parametric form and explain why $(0,0,0)$ always satisfies a homogeneous system.

## Before calculating: what idea do we need?

A linear system is called **homogeneous** when every constant term on the right-hand side is zero ($Ax = \mathbf{0}$).

Unlike general systems $Ax = b$, a homogeneous system **can never be inconsistent**:
- Every homogeneous system has at least the **trivial solution** $(x,y,z) = (0,0,0)$.
- Therefore, there are only two possibilities for a homogeneous system: either $(0,0,0)$ is the **only** solution (when every column has a pivot), or there are **infinitely many solutions** (when at least one variable is free).

## 1. Why $(0,0,0)$ always satisfies any homogeneous system

In any homogeneous equation

$$a_1 x_1 + a_2 x_2 + \dots + a_n x_n = 0,$$

every term on the left-hand side is a coefficient multiplied by an unknown $x_i$. If we substitute $x_1 = 0, x_2 = 0, \dots, x_n = 0$, each product becomes $a_i \cdot 0 = 0$, and the sum of zeros is zero:

$$a_1(0) + a_2(0) + \dots + a_n(0) = 0 + 0 + \dots + 0 = 0.$$

In matrix terms, $A\mathbf{0} = \mathbf{0}$ for every matrix $A$, so the zero vector $\mathbf{0} = (0,0,0)^T$ is guaranteed to satisfy $Ax = \mathbf{0}$ regardless of what the coefficients in $A$ are. Geometrically, every plane of the form $ax + by + cz = 0$ passes through the origin $(0,0,0)$.

## 2. Gaussian elimination on the homogeneous system

Write the augmented matrix:

$$\left[\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\
2 & 4 & -2 & 0 \\
1 & -1 & 2 & 0
\end{array}\right].$$

Eliminate $x$ below the first pivot by performing $R_2 \leftarrow R_2 - 2R_1$ and $R_3 \leftarrow R_3 - R_1$:

$$\left[\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\
0 & 0 & 0 & 0 \\
0 & -3 & 3 & 0
\end{array}\right].$$

Swap rows 2 and 3 ($R_2 \leftrightarrow R_3$), and divide the new second row by $-3$ ($R_2 \leftarrow -\frac{1}{3}R_2$):

$$\left[\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\
0 & 1 & -1 & 0 \\
0 & 0 & 0 & 0
\end{array}\right].$$

## 3. Finding all solutions in parametric form

The row echelon matrix has pivots in column 1 ($x$) and column 2 ($y$), while **column 3 ($z$) has no pivot**. Thus, $z$ is a free variable.

Translate the non-zero rows back into equations:

$$\begin{cases}
x + 2y - z = 0,\\
y - z = 0.
\end{cases}$$

Set the free variable $z = t \in \mathbb{R}$:
- From the second equation:
  $$y = z = t.$$
- Substitute $y = t$ and $z = t$ into the first equation:
  $$x = -2y + z = -2t + t = -t.$$

Therefore, all solutions in parametric form are given by:

$$\begin{cases}
x = -t,\\
y = t,\\
z = t,
\end{cases} \quad t \in \mathbb{R},$$

or in vector form as a line through the origin:

$$\begin{pmatrix} x \\ y \\ z \end{pmatrix} = t\begin{pmatrix} -1 \\ 1 \\ 1 \end{pmatrix}, \quad t \in \mathbb{R}.$$

## Quick verification

Substitute $(x, y, z) = (-t, t, t)$ into all three original equations:
- **Equation 1:** $(-t) + 2(t) - (t) = (-1 + 2 - 1)t = 0$. ✓
- **Equation 2:** $2(-t) + 4(t) - 2(t) = (-2 + 4 - 2)t = 0$. ✓
- **Equation 3:** $(-t) - (t) + 2(t) = (-1 - 1 + 2)t = 0$. ✓

Every equation reduces to $0 = 0$ for all $t \in \mathbb{R}$.

## A concrete example

Let us look at two specific parameter values on our solution line $(x,y,z) = (-t, t, t)$:
- Setting **$t = 0$** gives the trivial solution $(0, 0, 0)$—the origin through which all three planes pass.
- Setting **$t = 1$** gives a non-trivial solution $(-1, 1, 1)$. Checking $(-1, 1, 1)$ in the original system:
  $$-1 + 2(1) - 1 = 0, \qquad 2(-1) + 4(1) - 2(1) = 0, \qquad -1 - 1 + 2(1) = 0.$$
- Because the system is homogeneous, any scalar multiple of $(-1, 1, 1)$—such as $(-5, 5, 5)$ or $(3, -3, -3)$—is automatically another solution!

## How I would explain this in class

> A homogeneous system has $0$ on the right-hand side of every equation, so plugging in $(0,0,0)$ makes every left-hand side a sum of zeros, which always equals $0$. That means a homogeneous system is never inconsistent—the only question is whether there are *other* solutions besides $(0,0,0)$. Here, the second equation is twice the first, so elimination leaves a zero row and makes $z = t$ a free variable. Back-substituting gives $y = t$ and $x = -t$, a whole line of solutions passing through the origin.

## Related workbook topics

- [Exercise 4: Infinitely Many Solutions](problem_04_solution.md)
- [Exercise 5: Row Echelon Form and Number of Solutions](problem_05_solution.md)
