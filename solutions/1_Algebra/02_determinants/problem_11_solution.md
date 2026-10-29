# Exercise 11. Shortening the Calculation with Row Operations

## The question

Compute

$$\det\begin{pmatrix}1&2&3\\1&3&4\\1&4&6\end{pmatrix}$$

by first performing row operations that create as many zeros as possible. State which operations do not change the determinant.

## Before calculating: what idea do we need?

**Plan before calculating.** All three rows start with $1$, so subtracting $R_1$ from the other rows immediately gives zeros in the first column.

Effects of row operations:

- $R_i\leftarrow R_i+cR_j$ ($i\neq j$): determinant **unchanged**,
- swapping two rows: sign changes,
- scaling a row by $c$: determinant is multiplied by $c$.

We will use only the first type, so the determinant never changes.

## 1. Clear the first column

$R_2\leftarrow R_2-R_1$: $(1,3,4)-(1,2,3)=(0,1,1)$. Unchanged.

$R_3\leftarrow R_3-R_1$: $(1,4,6)-(1,2,3)=(0,2,3)$. Unchanged.

$$\begin{pmatrix}1&2&3\\0&1&1\\0&2&3\end{pmatrix}.$$

## 2. Clear below the second pivot

$R_3\leftarrow R_3-2R_2$: $(0,2,3)-(0,2,2)=(0,0,1)$. Unchanged.

$$\begin{pmatrix}1&2&3\\0&1&1\\0&0&1\end{pmatrix}.$$

## 3. Read off the determinant

The matrix is upper triangular:

$$\det=1\cdot1\cdot1=1.$$

## 4. Which operations did not change the determinant?

All three: $R_2-R_1$, $R_3-R_1$, $R_3-2R_2$ are all of the type "add a multiple of another row". No swaps or scalings were used, so the original determinant is exactly $1$.

## 5. Why planning helps

Without row operations, Sarrus' rule needs six triple products. Here, three subtractions with small numbers turn the problem into multiplying three $1$'s. The less arithmetic we do, the fewer chances for mistakes.

## 6. Quick verification

Cofactor expansion along the first row of the original matrix:

$$1(3\cdot6-4\cdot4)-2(1\cdot6-4\cdot1)+3(1\cdot4-3\cdot1)=1\cdot2-2\cdot2+3\cdot1=2-4+3=1.\ ✓$$

## 7. A concrete example

$\det=1$ means the matrix preserves volume and orientation. Its inverse also has determinant $1$, and since all entries are integers, the inverse matrix $\frac{1}{\det}\operatorname{adj}(A)$ also has only integer entries.

## How I would explain this in class

> All rows start with $1$, so I subtract the first row from the others. Then I subtract twice the new second row from the third. These operations don't change the determinant, and I end with a triangular matrix with ones on the diagonal. So the determinant is $1$. A direct expansion confirms it: $2-4+3=1$.

## Related workbook topics

- [Exercise 5: Row operations](problem_05_solution.md)
- [Exercise 13: Determinant by elimination](problem_13_solution.md)
