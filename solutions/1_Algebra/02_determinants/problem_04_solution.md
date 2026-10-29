# Exercise 4. Triangular Matrix

## The question

Without expanding the determinant, compute

$$\det\begin{pmatrix}2&4&1\\0&-3&5\\0&0&7\end{pmatrix}.$$

State the rule for an arbitrary triangular matrix and explain it using this example.

## Before calculating: what idea do we need?

A matrix is **upper triangular** if all entries below the main diagonal are zero (lower triangular: all above are zero).

**Rule:** the determinant of a triangular matrix is the **product of its diagonal entries**:

$$\det\begin{pmatrix}a_{11}&*&*\\0&a_{22}&*\\0&0&a_{33}\end{pmatrix}=a_{11}a_{22}a_{33}.$$

This is the reason why elimination is used to compute determinants: it turns any matrix into a triangular one.

## 1. Apply the rule

$$\det\begin{pmatrix}2&4&1\\0&-3&5\\0&0&7\end{pmatrix}=2\cdot(-3)\cdot7=-42.$$

## 2. Why the rule works (explained on this example)

Expand along the **first column**. It has only one non-zero entry, the $2$:

$$\det=2\cdot\det\begin{pmatrix}-3&5\\0&7\end{pmatrix}.$$

The smaller matrix is again triangular. Expanding along its first column:

$$\det\begin{pmatrix}-3&5\\0&7\end{pmatrix}=-3\cdot7-5\cdot0=-21.$$

So $\det=2\cdot(-21)=-42$. At each step only the diagonal entry survives, because everything below it is zero. The entries above the diagonal ($4,1,5$) never matter.

Another view: in every term of the determinant we must take exactly one entry from each row and each column. The only choice that avoids every zero below the diagonal is the diagonal itself.

## 3. Meaning

- The matrix is invertible exactly when **no diagonal entry is zero**. Here all three are non-zero, so it is invertible.
- The negative sign means the transformation reverses orientation (because of the $-3$). The volume scaling factor is $|{-42}|=42$.

## 4. Quick verification

Sarrus' rule: down-right diagonals $2\cdot(-3)\cdot7+4\cdot5\cdot0+1\cdot0\cdot0=-42$. Down-left diagonals: $1\cdot(-3)\cdot0+2\cdot5\cdot0+4\cdot0\cdot7=0$. So $\det=-42-0=-42$. ✓

## 5. A concrete example

If we change the $7$ to $0$:

$$\det\begin{pmatrix}2&4&1\\0&-3&5\\0&0&0\end{pmatrix}=2\cdot(-3)\cdot0=0.$$

This makes sense, because the last row is the zero row, so the matrix is singular.

## How I would explain this in class

> For a triangular matrix I just multiply the diagonal: $2\cdot(-3)\cdot7=-42$. The reason is that expanding along the first column, only the diagonal entry has a non-zero value, and the smaller matrix is triangular again. The entries above the diagonal never matter. So a triangular matrix is invertible exactly when there is no zero on the diagonal.

## Related workbook topics

- [Exercise 5: Row operations](problem_05_solution.md)
- [Exercise 13: Determinant by elimination](problem_13_solution.md)
