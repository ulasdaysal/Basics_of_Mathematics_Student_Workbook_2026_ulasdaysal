# Exercise 13. Determinant by Elimination

## The question

Compute the determinant of

$$A=\begin{pmatrix}1&2&3\\2&5&7\\1&0&2\end{pmatrix}$$

using elimination, and record the effect of every row operation on the value of the determinant.

## Before calculating: what idea do we need?

**Elimination** turns the matrix into upper triangular form, whose determinant is the product of the diagonal (Exercise 4). We must keep track of how each step changes the determinant:

| Operation | Factor applied to $\det$ |
|---|---|
| $R_i\leftarrow R_i+cR_j$ | $1$ (no change) |
| $R_i\leftrightarrow R_j$ | $-1$ |
| $R_i\leftarrow cR_i$ | $c$ |

Then $\det A=\dfrac{\det(\text{triangular})}{\text{product of all factors}}$.

## 1. Eliminate the first column

The pivot is $a_{11}=1$.

| Step | Operation | New row | Factor |
|---|---|---|---|
| 1 | $R_2\leftarrow R_2-2R_1$ | $(2,5,7)-(2,4,6)=(0,1,1)$ | $1$ |
| 2 | $R_3\leftarrow R_3-R_1$ | $(1,0,2)-(1,2,3)=(0,-2,-1)$ | $1$ |

$$\begin{pmatrix}1&2&3\\0&1&1\\0&-2&-1\end{pmatrix}.$$

## 2. Eliminate the second column

The pivot is now $1$ in position $(2,2)$.

| Step | Operation | New row | Factor |
|---|---|---|---|
| 3 | $R_3\leftarrow R_3+2R_2$ | $(0,-2,-1)+(0,2,2)=(0,0,1)$ | $1$ |

$$U=\begin{pmatrix}1&2&3\\0&1&1\\0&0&1\end{pmatrix}.$$

## 3. Result

All factors were $1$, so

$$\det A=\det U=1\cdot1\cdot1=1.$$

## 4. Meaning

- $\det A=1\neq0$: $A$ is invertible.
- The pivots $1,1,1$ are all non-zero, which is the elimination version of the same statement: a matrix is invertible exactly when elimination produces a full set of non-zero pivots.
- Elimination is the practical method for large matrices. It needs roughly $n^3/3$ operations, while cofactor expansion grows like $n!$.

## 5. Quick verification

Cofactor expansion along the first row:

$$\det A=1(5\cdot2-7\cdot0)-2(2\cdot2-7\cdot1)+3(2\cdot0-5\cdot1)=10-2(-3)+3(-5)=10+6-15=1.\ ✓$$

## 6. A concrete example

Suppose in step 3 we had swapped $R_2$ and $R_3$ first. Then the factor would be $-1$, the triangular matrix would have a different diagonal, and we would have to divide by $-1$ at the end. The final answer must still be $1$. The bookkeeping protects us from sign errors.

## How I would explain this in class

> I use the pivot $1$ to clear the first column by subtracting $2R_1$ and $R_1$. Then I use the new pivot $1$ to clear below it by adding $2R_2$. All three operations are "add a multiple of a row", so the determinant never changes. The final triangular matrix has diagonal $1,1,1$, so $\det A=1$, which a cofactor expansion confirms.

## Related workbook topics

- [Exercise 4: Triangular matrix](problem_04_solution.md)
- [Exercise 5: Row operations](problem_05_solution.md)
- [Exercise 11: Shortening the calculation](problem_11_solution.md)
