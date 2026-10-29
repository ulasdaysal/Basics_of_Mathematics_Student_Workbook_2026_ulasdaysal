# Exercise 15. Combining Determinant Properties

## The question

Let $A$ and $B$ be invertible $2\times2$ matrices with

$$\det A=-2,\qquad \det B=3.$$

Without finding the entries, compute

$$\det\left(B^{-1}A^TB\right).$$

State the properties used in order and explain why the factors involving $B$ cancel.

## Before calculating: what idea do we need?

We need three properties:

1. **Product rule:** $\det(XYZ)=\det X\cdot\det Y\cdot\det Z$.
2. **Inverse rule:** $\det(B^{-1})=\dfrac{1}{\det B}$, because $\det B\cdot\det B^{-1}=\det I=1$.
3. **Transpose rule:** $\det(A^T)=\det A$.

The idea: the product rule turns a product of **matrices** (which don't commute) into a product of **numbers** (which do).

## 1. Product rule

$$\det\left(B^{-1}A^TB\right)=\det(B^{-1})\cdot\det(A^T)\cdot\det B.$$

## 2. Inverse rule

$$\det(B^{-1})=\frac{1}{\det B}=\frac13.$$

## 3. Transpose rule

$$\det(A^T)=\det A=-2.$$

## 4. Combine

$$\det\left(B^{-1}A^TB\right)=\frac13\cdot(-2)\cdot3=-2.$$

## 5. Why the factors with $B$ cancel

As matrices, $B^{-1}$ and $B$ are **not** next to each other, and $A^T$ sits between them. So we cannot just cancel $B^{-1}B=I$ in the matrix product, because in general $B^{-1}A^TB\neq A^T$.

But after taking determinants we have the numbers $\frac{1}{\det B}$ and $\det B$. Numbers commute, so they can be moved together:

$$\frac{1}{\det B}\cdot\det B\cdot\det A^T=1\cdot\det A^T.$$

So the answer does not depend on $B$ at all: for any invertible $B$,

$$\det(B^{-1}MB)=\det M.$$

**Meaning:** $B^{-1}MB$ is the same transformation as $M$, only described in a different coordinate system (a change of basis). The volume scaling factor is a property of the transformation itself, not of the coordinates, so it is unchanged.

## 6. Quick verification with concrete matrices

Take $A=\begin{pmatrix}1&0\\0&-2\end{pmatrix}$ ($\det -2$) and $B=\begin{pmatrix}1&1\\0&3\end{pmatrix}$ ($\det 3$). Then $A^T=A$, $B^{-1}=\frac13\begin{pmatrix}3&-1\\0&1\end{pmatrix}$, and

$$A^TB=\begin{pmatrix}1&1\\0&-6\end{pmatrix},\qquad B^{-1}A^TB=\frac13\begin{pmatrix}3&-1\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&-6\end{pmatrix}=\frac13\begin{pmatrix}3&9\\0&-6\end{pmatrix}=\begin{pmatrix}1&3\\0&-2\end{pmatrix}.$$

This matrix differs from $A^T$, but its determinant is $1\cdot(-2)=-2$. ✓

## How I would explain this in class

> I use the product rule to split the determinant into three numbers: $\det B^{-1}$, $\det A^T$ and $\det B$. The inverse rule gives $\frac13$, and the transpose rule gives $-2$. As matrices, $B^{-1}$ and $B$ can't cancel because $A^T$ is between them, but as numbers they can, so the answer is $\frac13\cdot(-2)\cdot3=-2$. A change of basis doesn't change the determinant.

## Related workbook topics

- [Exercise 7: Using properties instead of recomputing](problem_07_solution.md)
- [Exercise 8: Determinant of a product](problem_08_solution.md)
