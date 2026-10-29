# Exercise 10. Columns of a Matrix Product

## The question

Given

$$A=\begin{pmatrix}1&2&0\\0&1&1\end{pmatrix},\qquad B=\begin{pmatrix}1&2\\-1&0\\3&1\end{pmatrix},$$

with columns of $B$ denoted $b_1,b_2$:

1. Compute $Ab_1$ and $Ab_2$.
2. Compute $AB$.
3. Explain why the columns of $AB$ are exactly $Ab_1$ and $Ab_2$.

## Before calculating: what idea do we need?

From Exercise 5 we know how a matrix acts on **one** vector. A matrix $B$ is just several column vectors placed side by side:

$$B=\begin{pmatrix}|&|\\b_1&b_2\\|&|\end{pmatrix}.$$

The entry $(AB)_{ij}$ uses only row $i$ of $A$ and **column $j$ of $B$**. So column $j$ of $AB$ depends only on $b_j$. This suggests the **column rule**:

$$AB=\begin{pmatrix}|&|\\Ab_1&Ab_2\\|&|\end{pmatrix}.$$

## 1. Matrix-vector products

$$b_1=\begin{pmatrix}1\\-1\\3\end{pmatrix},\qquad Ab_1=\begin{pmatrix}1\cdot1+2\cdot(-1)+0\cdot3\\0\cdot1+1\cdot(-1)+1\cdot3\end{pmatrix}=\begin{pmatrix}-1\\2\end{pmatrix}.$$

$$b_2=\begin{pmatrix}2\\0\\1\end{pmatrix},\qquad Ab_2=\begin{pmatrix}1\cdot2+2\cdot0+0\cdot1\\0\cdot2+1\cdot0+1\cdot1\end{pmatrix}=\begin{pmatrix}2\\1\end{pmatrix}.$$

## 2. The full product $AB$

$A$ is $2\times3$ and $B$ is $3\times2$, so $AB$ is $2\times2$. Computing each entry as row times column:

$$AB=\begin{pmatrix}1-2+0 & 2+0+0\\ 0-1+3 & 0+0+1\end{pmatrix}=\begin{pmatrix}-1&2\\2&1\end{pmatrix}.$$

## 3. Comparison

$$\text{column 1 of }AB=\begin{pmatrix}-1\\2\end{pmatrix}=Ab_1,\qquad \text{column 2 of }AB=\begin{pmatrix}2\\1\end{pmatrix}=Ab_2.\ ✓$$

## 4. Why this always happens

The first column of $AB$ consists of the entries $(AB)_{11}$ and $(AB)_{21}$:

$$(AB)_{11}=(\text{row 1 of }A)\cdot b_1,\qquad (AB)_{21}=(\text{row 2 of }A)\cdot b_1.$$

That is exactly the row-by-row computation of $Ab_1$. The same holds for every column. So

> **multiplying $A$ by a matrix $B$ = multiplying $A$ by each column of $B$ separately.**

Combining with Exercise 5: each column of $AB$ is a linear combination of the columns of $A$, with weights taken from the matching column of $B$.

## 5. Quick verification

Column view of $Ab_1$, using the columns of $A$, $a_1=(1,0)^T$, $a_2=(2,1)^T$, $a_3=(0,1)^T$:

$$Ab_1=1\,a_1-1\,a_2+3\,a_3=\begin{pmatrix}1-2+0\\0-1+3\end{pmatrix}=\begin{pmatrix}-1\\2\end{pmatrix}.\ ✓$$

## 6. A concrete example

If we only need the second column of $AB$, we don't have to compute the whole product: $Ab_2=(2,1)^T$ is enough. This saves work in large computations, and it is how computers often organise matrix multiplication.

## How I would explain this in class

> A matrix $B$ is a list of columns. Column $j$ of $AB$ only uses column $j$ of $B$, so it must be $Ab_j$. I computed $Ab_1=(-1,2)$ and $Ab_2=(2,1)$, and the full product is $AB=\begin{pmatrix}-1&2\\2&1\end{pmatrix}$, whose columns are exactly these two vectors. So multiplying by a matrix means multiplying by each of its columns.

## Related workbook topics

- [Exercise 5: Matrix times vector](problem_05_solution.md)
- [Exercise 15: Associativity](problem_15_solution.md)
