# Exercise 1. Definition of the Inverse

## The question

For

$$A=\begin{pmatrix}2&1\\1&1\end{pmatrix},\qquad B=\begin{pmatrix}1&-1\\-1&2\end{pmatrix}$$

check, without using a formula, whether $B=A^{-1}$. Compute $AB$ and $BA$ and relate the result to the definition of the inverse.

## Before calculating: what idea do we need?

A square matrix $B$ is the **inverse** of $A$ (written $B=A^{-1}$) if and only if multiplying them in either order produces the identity matrix $I$:

$$AB=I \quad\text{and}\quad BA=I,$$

where for $2\times2$ matrices

$$I=\begin{pmatrix}1&0\\0&1\end{pmatrix}.$$

In numbers, the multiplicative inverse of $5$ is $\frac{1}{5}$ because $5\cdot\frac{1}{5}=1$. For matrices, $I$ plays the role of $1$: it is the matrix that leaves every vector unchanged ($Iv=v$).

## 1. Compute the product $AB$

Multiply the rows of $A$ by the columns of $B$:

$$AB=\begin{pmatrix}2&1\\1&1\end{pmatrix}\begin{pmatrix}1&-1\\-1&2\end{pmatrix}=\begin{pmatrix}2\cdot1+1\cdot(-1) & 2\cdot(-1)+1\cdot2\\1\cdot1+1\cdot(-1) & 1\cdot(-1)+1\cdot2\end{pmatrix}.$$

Simplifying each entry gives

$$AB=\begin{pmatrix}2-1 & -2+2\\1-1 & -1+2\end{pmatrix}=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I.$$

## 2. Compute the product $BA$

Now multiply the rows of $B$ by the columns of $A$:

$$BA=\begin{pmatrix}1&-1\\-1&2\end{pmatrix}\begin{pmatrix}2&1\\1&1\end{pmatrix}=\begin{pmatrix}1\cdot2+(-1)\cdot1 & 1\cdot1+(-1)\cdot1\\(-1)\cdot2+2\cdot1 & (-1)\cdot1+2\cdot1\end{pmatrix}.$$

Simplifying each entry gives

$$BA=\begin{pmatrix}2-1 & 1-1\\-2+2 & -1+2\end{pmatrix}=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I.$$

## 3. Relate the result to the definition

Since both products equal the $2\times2$ identity matrix,

$$AB=BA=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I,$$

the definition of the inverse matrix is satisfied directly. Therefore,

$$B=A^{-1}.$$

## 4. Geometric meaning of $AB=I$ and $BA=I$

Matrix multiplication corresponds to applying one linear transformation after another:

- $AB=I$ means: if we first apply $B$ to a vector and then apply $A$, the vector returns to its starting position.
- $BA=I$ means: if we first apply $A$ to a vector and then apply $B$, the vector also returns to its starting position.

Each matrix completely undoes the action of the other.

## Quick verification

We can independently verify using the $2\times2$ determinant and adjugate rule:

$$\det(A)=2\cdot1-1\cdot1=1,$$

and swapping the diagonal entries while negating the off-diagonal entries of $A$ gives

$$A^{-1}=\frac{1}{1}\begin{pmatrix}1&-1\\-1&2\end{pmatrix}=B.$$

This matches $B$ entry for entry. ✓

## A concrete example

Take the vector $v=\begin{pmatrix}3\\4\end{pmatrix}$. First apply $A$:

$$Av=\begin{pmatrix}2&1\\1&1\end{pmatrix}\begin{pmatrix}3\\4\end{pmatrix}=\begin{pmatrix}10\\7\end{pmatrix}.$$

Now apply $B$ to the output $\begin{pmatrix}10\\7\end{pmatrix}$:

$$B(Av)=\begin{pmatrix}1&-1\\-1&2\end{pmatrix}\begin{pmatrix}10\\7\end{pmatrix}=\begin{pmatrix}10-7\\-10+14\end{pmatrix}=\begin{pmatrix}3\\4\end{pmatrix}=v.$$

The matrix $B$ reverses the effect of $A$ and recovers the original vector $(3,4)^T$.

## How I would explain this in class

> To check whether $B$ is the inverse of $A$ without using any formula, we just multiply them together. When we compute $AB$ and $BA$, all off-diagonal terms cancel out to $0$ and the diagonal terms simplify to $1$, giving the identity matrix $I$ in both orders. By definition, that means $B$ is $A^{-1}$—it is the transformation that undoes $A$.

## Related workbook topics

- [Exercise 2: Formula for a 2×2 Matrix](problem_02_solution.md)
- [Exercise 8: Inverse of a Transformation](problem_08_solution.md)
