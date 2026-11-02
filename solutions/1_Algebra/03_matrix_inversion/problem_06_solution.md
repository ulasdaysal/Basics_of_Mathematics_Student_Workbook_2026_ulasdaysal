# Exercise 6. Solving a System Using the Inverse

## The question

Solve

$$Ax=b,$$

where

$$A=\begin{pmatrix}2&1\\1&3\end{pmatrix},\qquad b=\begin{pmatrix}5\\7\end{pmatrix},$$

using $x=A^{-1}b$. Then substitute the resulting vector back into the equation and check the result.

## Before calculating: what idea do we need?

In ordinary algebra, we solve $ax=b$ (with $a\neq0$) by multiplying both sides by $a^{-1}$ to get $x=a^{-1}b$.

For a matrix system $Ax=b$, when $A$ is invertible, we multiply both sides **on the left** by $A^{-1}$:

$$A^{-1}(Ax)=A^{-1}b \quad\Longrightarrow\quad (A^{-1}A)x=A^{-1}b \quad\Longrightarrow\quad Ix=A^{-1}b \quad\Longrightarrow\quad x=A^{-1}b.$$

So finding $A^{-1}$ turns solving the system into a single matrix-vector multiplication.

## 1. Find the inverse $A^{-1}$

First compute the determinant of $A$:

$$\det A = 2\cdot3 - 1\cdot1 = 6 - 1 = 5\neq0.$$

Using the $2\times2$ inverse formula, swap the diagonal entries ($2$ and $3$), negate the off-diagonal entries ($1$ and $1$), and divide by $5$:

$$A^{-1}=\frac{1}{5}\begin{pmatrix}3&-1\\-1&2\end{pmatrix}.$$

## 2. Compute $x=A^{-1}b$

Multiply $A^{-1}$ by the right-hand side vector $b=\begin{pmatrix}5\\7\end{pmatrix}$:

$$x=A^{-1}b=\frac{1}{5}\begin{pmatrix}3&-1\\-1&2\end{pmatrix}\begin{pmatrix}5\\7\end{pmatrix}.$$

First perform the matrix-vector product before dividing by $5$:

$$x=\frac{1}{5}\begin{pmatrix}3\cdot5 + (-1)\cdot7\\(-1)\cdot5 + 2\cdot7\end{pmatrix}=\frac{1}{5}\begin{pmatrix}15-7\\-5+14\end{pmatrix}=\frac{1}{5}\begin{pmatrix}8\\9\end{pmatrix}=\begin{pmatrix}\frac{8}{5}\\\frac{9}{5}\end{pmatrix}.$$

## 3. Why keeping $\frac{1}{5}$ outside until the end helps

If we distribute $\frac{1}{5}$ into $A^{-1}$ too early, we have to multiply fractions in every entry. Keeping the scalar $\frac{1}{\det A}=\frac{1}{5}$ in front lets us do whole-number arithmetic ($15-7=8$ and $-5+14=9$) and divide only once at the very end.

## Quick verification

Substitute $x=\begin{pmatrix}\frac{8}{5}\\\frac{9}{5}\end{pmatrix}$ back into the left side of $Ax=b$:

$$Ax=\begin{pmatrix}2&1\\1&3\end{pmatrix}\begin{pmatrix}\frac{8}{5}\\\frac{9}{5}\end{pmatrix}=\begin{pmatrix}2\cdot\frac{8}{5}+1\cdot\frac{9}{5}\\1\cdot\frac{8}{5}+3\cdot\frac{9}{5}\end{pmatrix}=\begin{pmatrix}\frac{16+9}{5}\\\frac{8+27}{5}\end{pmatrix}=\begin{pmatrix}\frac{25}{5}\\\frac{35}{5}\end{pmatrix}=\begin{pmatrix}5\\7\end{pmatrix}=b.$$

The left-hand side equals $b$ exactly. ✓

## A concrete example

Written out as two scalar equations, $Ax=b$ is the system of two lines in the plane:

$$\begin{cases}2x_1 + x_2 = 5,\\ x_1 + 3x_2 = 7.\end{cases}$$

Our solution $x=\left(\frac{8}{5},\frac{9}{5}\right)^T=(1.6, 1.8)^T$ is the unique intersection point of these two lines:
- Line 1: $2(1.6) + 1.8 = 3.2 + 1.8 = 5$,
- Line 2: $1.6 + 3(1.8) = 1.6 + 5.4 = 7$.

## How I would explain this in class

> To solve $Ax=b$ using the inverse, we first find $\det A = 6-1=5$, which gives $A^{-1}=\frac{1}{5}\begin{pmatrix}3&-1\\-1&2\end{pmatrix}$. Then we multiply $A^{-1}$ by $b=(5,7)^T$. Doing the integer multiplication first gives $(8,9)^T$, and dividing by $5$ gives $x=(8/5, 9/5)^T$. Plugging $(8/5, 9/5)^T$ back into $Ax$ produces $(25/5, 35/5)^T=(5,7)^T$, confirming our answer.

## Related workbook topics

- [Exercise 2: Formula for a 2×2 Matrix](problem_02_solution.md)
- [Exercise 15: Two Methods for Solving the Same System](problem_15_solution.md)
