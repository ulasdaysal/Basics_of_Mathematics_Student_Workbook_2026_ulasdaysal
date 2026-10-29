# Exercise 12. A Parameter Revealed by a Row Operation

## The question

For

$$A(t)=\begin{pmatrix}1&2&3\\2&4&t\\0&1&1\end{pmatrix}$$

find the values of $t$ for which the matrix is not invertible. First perform $R_2\leftarrow R_2-2R_1$ and use the resulting structure. At the end, explain what happens to the rows for the value found.

## Before calculating: what idea do we need?

- The matrix is not invertible exactly when $\det A(t)=0$.
- $R_2\leftarrow R_2-2R_1$ does **not** change the determinant, so we may compute the determinant of the simplified matrix instead.
- The first two entries of $R_2$ are exactly twice those of $R_1$. The row operation will therefore create zeros and isolate the parameter $t$ in a single entry.

## 1. The row operation

$$R_2-2R_1=(2,4,t)-(2,4,6)=(0,0,t-6).$$

$$A'(t)=\begin{pmatrix}1&2&3\\0&0&t-6\\0&1&1\end{pmatrix},\qquad \det A'(t)=\det A(t).$$

## 2. Use the structure

Row 2 now has only one possibly non-zero entry. Expanding along row 2, only position $(2,3)$ contributes, with sign $(-1)^{2+3}=-1$:

$$\det A(t)=-(t-6)\cdot\det\begin{pmatrix}1&2\\0&1\end{pmatrix}=-(t-6)\cdot1=6-t.$$

## 3. Find the forbidden value

$$6-t=0\iff t=6.$$

So $A(t)$ is **not invertible only for $t=6$**, and invertible for all $t\neq6$.

## 4. What happens to the rows at $t=6$

For $t=6$ the second row is

$$R_2=(2,4,6)=2\cdot(1,2,3)=2R_1.$$

The second row is just a multiple of the first, so it adds no new information. After the row operation it becomes the zero row. The rows are dependent, the matrix flattens $\mathbb{R}^3$ into a plane, and it cannot be inverted.

## 5. Quick verification

Direct cofactor expansion along the first row of $A(t)$:

$$\det A(t)=1(4\cdot1-t\cdot1)-2(2\cdot1-t\cdot0)+3(2\cdot1-4\cdot0)=(4-t)-4+6=6-t.\ ✓$$

## 6. A concrete example

- $t=7$: $\det=-1\neq0$, invertible.
- $t=6$: $A(6)\begin{pmatrix}1\\1\\-1\end{pmatrix}=\begin{pmatrix}1+2-3\\2+4-6\\0+1-1\end{pmatrix}=\begin{pmatrix}0\\0\\0\end{pmatrix}$. A non-zero vector is sent to zero, confirming that $A(6)$ is singular.

## How I would explain this in class

> I subtract twice the first row from the second. This doesn't change the determinant, and the second row becomes $(0,0,t-6)$. Expanding along that row gives $\det=6-t$, so the matrix is singular only for $t=6$. At $t=6$ the second row is exactly twice the first, so the rows are dependent.

## Related workbook topics

- [Exercise 6: Parameter and invertibility](problem_06_solution.md)
- [Exercise 10: Detecting dependence](problem_10_solution.md)
