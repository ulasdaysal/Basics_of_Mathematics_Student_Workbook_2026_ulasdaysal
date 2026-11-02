# Exercise 1. From a System to a Matrix

## The question

Write the system

$$\begin{cases}2x-y+z=4,\\x+3y-2z=1,\\3x+y+z=7.\end{cases}$$

in the form $Ax=b$. Identify the coefficient matrix, the vector of unknowns, and the right-hand side vector. Explain how each row of the matrix corresponds to one equation.

## Before calculating: what idea do we need?

A system of linear equations is a compact way of asking: *which vector of unknowns $x$, when multiplied by a grid of coefficients $A$, produces the target vector $b$?*

By the definition of matrix-vector multiplication, the $i$-th entry of the product $Ax$ is the dot product of the $i$-th row of $A$ with the column vector $x$. Therefore:
- Each **row** of $A$ stores the coefficients of **one equation**.
- Each **column** of $A$ corresponds to **one variable** ($x$, $y$, or $z$, kept in a fixed order).

## 1. Identifying the three components

First, make sure the variables appear in the same order ($x$, then $y$, then $z$) in every equation, and write any implicit $\pm 1$ coefficients explicitly:

$$\begin{cases}
2x + (-1)y + 1z = 4,\\
1x + 3y + (-2)z = 1,\\
3x + 1y + 1z = 7.
\end{cases}$$

From this aligned layout, we read off:

1. **The coefficient matrix $A$ ($3\times 3$):**
   $$A = \begin{pmatrix} 2 & -1 & 1 \\ 1 & 3 & -2 \\ 3 & 1 & 1 \end{pmatrix}.$$

2. **The vector of unknowns $x$ ($3\times 1$):**
   $$\mathbf{x} = \begin{pmatrix} x \\ y \\ z \end{pmatrix}.$$

3. **The right-hand side vector $b$ ($3\times 1$):**
   $$b = \begin{pmatrix} 4 \\ 1 \\ 7 \end{pmatrix}.$$

## 2. Writing the matrix equation $Ax=b$

Putting the three pieces together gives the matrix equation

$$\begin{pmatrix} 2 & -1 & 1 \\ 1 & 3 & -2 \\ 3 & 1 & 1 \end{pmatrix}\begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 4 \\ 1 \\ 7 \end{pmatrix}.$$

## 3. How each row corresponds to one equation

When we multiply $A$ by $\mathbf{x}$, each row of $A$ pairs up term-by-term with the column $(x,y,z)^T$:

- **Row 1:** $(2, -1, 1)\cdot(x,y,z)^T = 2x - y + z$, which must equal the first entry of $b$, namely $4$.
- **Row 2:** $(1, 3, -2)\cdot(x,y,z)^T = x + 3y - 2z$, which must equal the second entry of $b$, namely $1$.
- **Row 3:** $(3, 1, 1)\cdot(x,y,z)^T = 3x + y + z$, which must equal the third entry of $b$, namely $7$.

Two vectors are equal if and only if all of their corresponding components are equal, so the single vector equation $Ax=b$ states all three scalar equations simultaneously.

## Quick verification

Let us multiply out $A\mathbf{x}$ directly using the rules of matrix multiplication:

$$A\mathbf{x} = \begin{pmatrix} 2 & -1 & 1 \\ 1 & 3 & -2 \\ 3 & 1 & 1 \end{pmatrix}\begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 2\cdot x + (-1)\cdot y + 1\cdot z \\ 1\cdot x + 3\cdot y + (-2)\cdot z \\ 3\cdot x + 1\cdot y + 1\cdot z \end{pmatrix} = \begin{pmatrix} 2x - y + z \\ x + 3y - 2z \\ 3x + y + z \end{pmatrix}.$$

Setting this column vector equal to $b = (4, 1, 7)^T$ reproduces the exact original system line by line. ✓

## A concrete example

Suppose we test whether the specific vector $\mathbf{x} = (2, 0, 0)^T$ is a solution. In the matrix form, we compute one matrix-vector product:

$$A\begin{pmatrix} 2 \\ 0 \\ 0 \end{pmatrix} = \begin{pmatrix} 2(2) - 1(0) + 1(0) \\ 1(2) + 3(0) - 2(0) \\ 3(2) + 1(0) + 1(0) \end{pmatrix} = \begin{pmatrix} 4 \\ 2 \\ 6 \end{pmatrix} \neq \begin{pmatrix} 4 \\ 1 \\ 7 \end{pmatrix}.$$

Notice how the first component matches ($4=4$), meaning $(2,0,0)$ lies on the plane of the first equation, but it fails the second and third equations. On the other hand, testing the actual solution $\mathbf{x} = (2, 0, 0)^T$ vs. $\mathbf{x} = \left(\frac{36}{13}, -\frac{1}{13}, -\frac{19}{13}\right)^T$ (or checking $(1, 1, 3)^T$) gives

$$A\begin{pmatrix} 1 \\ 1 \\ 3 \end{pmatrix} = \begin{pmatrix} 2 - 1 + 3 \\ 1 + 3 - 6 \\ 3 + 1 + 3 \end{pmatrix} = \begin{pmatrix} 4 \\ -2 \\ 7 \end{pmatrix},$$

which satisfies the first and third equations simultaneously.

## How I would explain this in class

> Think of $Ax=b$ as separating the "wiring" of the system from the "variables." The matrix $A$ holds just the numbers in front of $x, y, z$—keep the columns strictly aligned by variable and the rows strictly aligned by equation. When you multiply a row of $A$ by the column $(x,y,z)^T$, you reconstruct the left-hand side of that equation, and setting the result equal to $b$ locks in the right-hand sides.

## Related workbook topics

- [Exercise 2: Gaussian Elimination — One Solution](problem_02_solution.md)
- [Exercise 8: Two Systems with the Same Coefficient Matrix](problem_08_solution.md)
