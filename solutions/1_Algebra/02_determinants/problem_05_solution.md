# Exercise 5. Row Operations

## The question

For

$$A=\begin{pmatrix}1&2&3\\2&1&0\\-1&4&2\end{pmatrix}$$

find $\det A$ by simplifying the matrix with row operations. At each step, state whether and how the determinant changes.

## Before calculating: what idea do we need?

How each elementary row operation affects the determinant:

| Operation | Effect on $\det$ |
|---|---|
| $R_i\leftarrow R_i+cR_j$ (add a multiple of another row) | **no change** |
| $R_i\leftrightarrow R_j$ (swap) | multiply by $-1$ |
| $R_i\leftarrow cR_i$ (scale a row) | multiply by $c$ |

Plan: use only "add a multiple" operations to reach a triangular matrix (no change at all), then multiply the diagonal (Exercise 4).

## 1. Clear the first column

$R_2\leftarrow R_2-2R_1$: $(2,1,0)-(2,4,6)=(0,-3,-6)$. **No change** to $\det$.

$R_3\leftarrow R_3+R_1$: $(-1,4,2)+(1,2,3)=(0,6,5)$. **No change** to $\det$.

$$A_1=\begin{pmatrix}1&2&3\\0&-3&-6\\0&6&5\end{pmatrix},\qquad \det A_1=\det A.$$

## 2. Clear the second column

$R_3\leftarrow R_3+2R_2$: $(0,6,5)+(0,-6,-12)=(0,0,-7)$. **No change** to $\det$.

$$A_2=\begin{pmatrix}1&2&3\\0&-3&-6\\0&0&-7\end{pmatrix},\qquad \det A_2=\det A.$$

## 3. Read off the determinant

$A_2$ is upper triangular, so

$$\det A=\det A_2=1\cdot(-3)\cdot(-7)=21.$$

## 4. Summary of the steps

| Step | Operation | Factor | Running $\det$ relation |
|---|---|---|---|
| 1 | $R_2\leftarrow R_2-2R_1$ | $1$ | $\det A_{\text{new}}=\det A$ |
| 2 | $R_3\leftarrow R_3+R_1$ | $1$ | $\det A_1=\det A$ |
| 3 | $R_3\leftarrow R_3+2R_2$ | $1$ | $\det A_2=\det A$ |

No swaps and no scalings were needed, so no correction factor appears.

## 5. Why "add a multiple" does not change the determinant

The determinant is linear in each row, so

$$\det(\dots,R_i+cR_j,\dots)=\det(\dots,R_i,\dots)+c\,\det(\dots,R_j,\dots).$$

The last determinant has two equal rows ($R_j$ appears twice), so it is $0$. Geometrically, this is a shear, which slides the shape without changing its volume.

## 6. Quick verification

Cofactor expansion along the first row of the original matrix:

$$\det A=1(1\cdot2-0\cdot4)-2(2\cdot2-0\cdot(-1))+3(2\cdot4-1\cdot(-1))=2-8+27=21.\ ✓$$

## 7. A concrete example

If at step 3 we had instead scaled $R_2$ by $-\tfrac13$ to get a pivot $1$, the determinant would have been multiplied by $-\tfrac13$, and we would need to multiply back by $-3$ at the end. Avoiding scaling keeps the bookkeeping simple.

## How I would explain this in class

> I use only operations of the type "add a multiple of one row to another", because they don't change the determinant. After three such steps the matrix is upper triangular with diagonal $1,-3,-7$, so $\det A=21$. A direct cofactor expansion gives the same value, $2-8+27=21$.

## Related workbook topics

- [Exercise 4: Triangular matrix](problem_04_solution.md)
- [Exercise 13: Determinant by elimination](problem_13_solution.md)
- [Matrices, Exercise 8: Row operations](../01_matrices_and_operations/problem_08_solution.md)
