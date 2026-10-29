# Exercise 1. Matrix Size and Entries

## The question

We are given

$$A=\begin{pmatrix}2&-1&3\\0&4&5\end{pmatrix},\qquad B=\begin{pmatrix}1&0\\-2&3\\4&1\end{pmatrix}.$$

We want to:

1. State the sizes of $A$ and $B$.
2. Read off the entries $a_{12}$, $a_{23}$, $b_{21}$, $b_{32}$.
3. Write the second row of $A$ and the first column of $B$ as vectors.

## Before calculating: what idea do we need?

A matrix is a rectangular table of numbers. Everything about it is described by **rows** (horizontal) and **columns** (vertical).

- The **size** $m\times n$ means $m$ rows and $n$ columns, always in the order *rows first, columns second*.
- The entry $a_{ij}$ is in **row $i$** and **column $j$**. Again: row first, column second.

This convention is used for every later operation (multiplication, transpose, etc.), so it is worth being precise.

## 1. Sizes of the matrices

$A$ has 2 rows and 3 columns, and $B$ has 3 rows and 2 columns:

$$A \in \mathbb{R}^{2\times 3},\qquad B\in\mathbb{R}^{3\times 2}.$$

The two matrices have "swapped" shapes. They are **not** the same size, even though both contain 6 numbers.

## 2. Reading off entries

We go to the row given by the first index, then to the column given by the second index.

| Entry | Row | Column | Value |
|---|---|---|---|
| $a_{12}$ | 1 | 2 | $-1$ |
| $a_{23}$ | 2 | 3 | $5$ |
| $b_{21}$ | 2 | 1 | $-2$ |
| $b_{32}$ | 3 | 2 | $1$ |

## 3. Rows and columns as vectors

The second row of $A$ is a **row vector** with 3 entries:

$$r_2(A)=\begin{pmatrix}0&4&5\end{pmatrix}.$$

The first column of $B$ is a **column vector** with 3 entries:

$$c_1(B)=\begin{pmatrix}1\\-2\\4\end{pmatrix}.$$

Both have length 3. This is not a coincidence: the number of columns of $A$ equals the number of rows of $B$, which is exactly what makes the product $AB$ possible (see Exercise 3).

## 4. Common mistake

Reading $a_{12}$ as "row 2, column 1" would give $0$ instead of $-1$. The order of the indices matters. $a_{12}\neq a_{21}$ in general.

## 5. Quick verification

- Counting entries: $2\cdot 3=6$ numbers in $A$ and $3\cdot 2=6$ numbers in $B$. ✓
- $a_{23}$ must exist only if $A$ has at least 2 rows and 3 columns, which it does. ✓
- $b_{32}$ must exist only if $B$ has at least 3 rows and 2 columns, which it does. ✓
- There is no $b_{23}$, because $B$ has only 2 columns. This confirms we did not confuse the order.

## 6. A concrete example

The second row of $A$ times the first column of $B$ (entry by entry, then summed) is

$$0\cdot 1+4\cdot(-2)+5\cdot 4=0-8+20=12.$$

This number is exactly the entry $(AB)_{21}$. So reading rows and columns correctly is the first step of matrix multiplication.

## How I would explain this in class

> A matrix is described by rows and columns, and we always say rows first. $A$ is $2\times 3$ and $B$ is $3\times 2$. To read $a_{ij}$ I go to row $i$ and then column $j$, so $a_{12}=-1$, $a_{23}=5$, $b_{21}=-2$, $b_{32}=1$. The second row of $A$ is $(0,4,5)$ and the first column of $B$ is $(1,-2,4)^T$. They have the same length, which is why we can multiply them.

## Related workbook topics

- [Exercise 3: When can matrices be multiplied?](problem_03_solution.md)
- [Exercise 6: Transpose](problem_06_solution.md)
