# Exercise 6. Parameter and Invertibility

## The question

For

$$A(t)=\begin{pmatrix}t&1\\2&t\end{pmatrix}$$

find all values of $t$ for which the matrix is not invertible, and explain how the answer is related to the determinant being zero.

## Before calculating: what idea do we need?

A square matrix is invertible **if and only if** its determinant is non-zero. So instead of trying to invert $A(t)$ for every $t$, we compute $\det A(t)$ as a function of $t$ and find where it is zero.

## 1. Compute the determinant

$$\det A(t)=t\cdot t-1\cdot2=t^2-2.$$

## 2. Find the forbidden values

$$t^2-2=0\iff t^2=2\iff t=\pm\sqrt2.$$

So $A(t)$ is **not invertible** exactly for

$$t=\sqrt2\quad\text{or}\quad t=-\sqrt2,$$

and it is invertible for all $t\in\mathbb{R}\setminus\{-\sqrt2,\sqrt2\}$.

## 3. The inverse for allowed values

$$A(t)^{-1}=\frac{1}{t^2-2}\begin{pmatrix}t&-1\\-2&t\end{pmatrix}.$$

The factor $\frac{1}{t^2-2}$ shows directly why $t=\pm\sqrt2$ is excluded: we would divide by zero.

## 4. Why the excluded values fail

Take $t=\sqrt2$:

$$A(\sqrt2)=\begin{pmatrix}\sqrt2&1\\2&\sqrt2\end{pmatrix},\qquad (2,\sqrt2)=\sqrt2\cdot(\sqrt2,1).$$

The second row is a multiple of the first, so the rows are dependent. For $t=-\sqrt2$: $(2,-\sqrt2)=-\sqrt2\cdot(-\sqrt2,1)$, again dependent. In both cases the plane is squashed onto a line, and the map cannot be undone.

## 5. Quick verification

$$\begin{pmatrix}t&1\\2&t\end{pmatrix}\begin{pmatrix}t&-1\\-2&t\end{pmatrix}=\begin{pmatrix}t^2-2&-t+t\\2t-2t&-2+t^2\end{pmatrix}=(t^2-2)I.$$

After dividing by $t^2-2$ we get $I$, which confirms the inverse formula. ✓

## 6. A concrete example

For $t=2$: $\det=2$, and

$$A(2)=\begin{pmatrix}2&1\\2&2\end{pmatrix},\qquad A(2)^{-1}=\frac12\begin{pmatrix}2&-1\\-2&2\end{pmatrix}=\begin{pmatrix}1&-\tfrac12\\-1&1\end{pmatrix}.$$

## How I would explain this in class

> The matrix is invertible exactly when the determinant isn't zero. Here $\det A(t)=t^2-2$, which is zero for $t=\pm\sqrt2$. At those values the rows are multiples of each other, so the matrix is singular. For every other $t$ the inverse is $\frac{1}{t^2-2}\begin{pmatrix}t&-1\\-2&t\end{pmatrix}$.

## Related workbook topics

- [Exercise 1: Determinant of a 2×2 matrix](problem_01_solution.md)
- [Exercise 12: A parameter revealed by a row operation](problem_12_solution.md)
- [Exercise 14: A system of equations and the determinant](problem_14_solution.md)
