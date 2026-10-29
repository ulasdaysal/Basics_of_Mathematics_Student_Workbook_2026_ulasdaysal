# Exercise 8. Row Operations and Their Reversibility

## The question

For

$$A=\begin{pmatrix}1&2&-1\\2&4&1\\-1&1&3\end{pmatrix}$$

perform, in order:

1. $R_2\leftarrow R_2-2R_1$,
2. $R_3\leftarrow R_3+R_1$,
3. interchange $R_2$ and $R_3$.

Write the matrix after each step, and for each operation state an operation that reverses it.

## Before calculating: what idea do we need?

There are three **elementary row operations**:

- add a multiple of one row to another row,
- swap two rows,
- multiply a row by a non-zero number.

They are the tools of Gaussian elimination. Their key property is that each one is **reversible**, so no information is lost. That is why a system of equations keeps the same solutions after row operations.

The goal of these particular steps is to create zeros below the first entry (the pivot) and bring the matrix to an upper-triangular (echelon) form.

## 1. Step 1: $R_2\leftarrow R_2-2R_1$

$$R_2-2R_1=(2,4,1)-2(1,2,-1)=(2-2,\ 4-4,\ 1+2)=(0,0,3).$$

$$A_1=\begin{pmatrix}1&2&-1\\0&0&3\\-1&1&3\end{pmatrix}.$$

## 2. Step 2: $R_3\leftarrow R_3+R_1$

$$R_3+R_1=(-1,1,3)+(1,2,-1)=(0,3,2).$$

$$A_2=\begin{pmatrix}1&2&-1\\0&0&3\\0&3&2\end{pmatrix}.$$

The first column now has zeros below the pivot $1$.

## 3. Step 3: $R_2\leftrightarrow R_3$

Row 2 starts with two zeros, so it should go below row 3. Swapping gives

$$A_3=\begin{pmatrix}1&2&-1\\0&3&2\\0&0&3\end{pmatrix}.$$

This matrix is upper triangular, which is the target form of elimination.

## 4. Reverse operations

| Operation | Reverse operation | Why it works |
|---|---|---|
| $R_2\leftarrow R_2-2R_1$ | $R_2\leftarrow R_2+2R_1$ | $R_1$ was not changed, so we can add back exactly what we subtracted. |
| $R_3\leftarrow R_3+R_1$ | $R_3\leftarrow R_3-R_1$ | Again $R_1$ is unchanged, so we subtract what we added. |
| $R_2\leftrightarrow R_3$ | $R_2\leftrightarrow R_3$ | Swapping twice returns the original order. |

To get back from $A_3$ to $A$ we undo the steps in **reverse order**: first swap, then $R_3\leftarrow R_3-R_1$, then $R_2\leftarrow R_2+2R_1$.

## 5. Quick verification

Undo from $A_3$:

- Swap $R_2,R_3$: back to $A_2$.
- $R_3\leftarrow R_3-R_1$: $(0,3,2)-(1,2,-1)=(-1,1,3)$. Back to $A_1$. ✓
- $R_2\leftarrow R_2+2R_1$: $(0,0,3)+(2,4,-2)=(2,4,1)$. Back to $A$. ✓

Determinant check: adding a multiple of a row does not change the determinant, and a swap changes the sign. So $\det A=-\det A_3=-(1\cdot3\cdot3)=-9$. Directly:

$$\det A=1(12-1)-2(6+1)+(-1)(2+4)=11-14-6=-9.\ ✓$$

## 6. A concrete example

Each row operation is multiplication by an **elementary matrix** from the left. Step 1 is

$$E_1=\begin{pmatrix}1&0&0\\-2&1&0\\0&0&1\end{pmatrix},\qquad E_1^{-1}=\begin{pmatrix}1&0&0\\2&1&0\\0&0&1\end{pmatrix}.$$

$E_1^{-1}$ is exactly the matrix of the reverse operation $R_2\leftarrow R_2+2R_1$.

## How I would explain this in class

> I first subtract twice row 1 from row 2, then add row 1 to row 3, so the first column has zeros under the pivot. Then I swap rows 2 and 3 to get the upper-triangular matrix $\begin{pmatrix}1&2&-1\\0&3&2\\0&0&3\end{pmatrix}$. Each step can be undone: add back $2R_1$, subtract $R_1$, and swap again, in reverse order. Because every step is reversible, elimination never loses information.

## Related workbook topics

- [Exercise 15: Associativity of multiplication](problem_15_solution.md)
- [Exercise 3: When can matrices be multiplied?](problem_03_solution.md)
