# Exercise 6. Transpose

## The question

For

$$A=\begin{pmatrix}1&2&3\\4&5&6\end{pmatrix},\qquad B=\begin{pmatrix}1&0\\2&1\\-1&3\end{pmatrix}$$

compute $A^T$, $B^T$, and $AB$. Then verify that

$$(AB)^T=B^TA^T.$$

## Before calculating: what idea do we need?

The **transpose** turns rows into columns:

$$(A^T)_{ij}=a_{ji}.$$

So an $m\times n$ matrix becomes $n\times m$.

Why does the order reverse in $(AB)^T=B^TA^T$? Look at sizes: $A$ is $2\times3$ and $B$ is $3\times2$. Then $B^T$ is $2\times3$ and $A^T$ is $3\times2$. The product $A^TB^T$ would be $(3\times2)(2\times3)=3\times3$, which cannot equal the $2\times2$ matrix $(AB)^T$. Only $B^TA^T$ has the right size. The computation will confirm it also has the right entries.

## 1. Transposes

$$A^T=\begin{pmatrix}1&4\\2&5\\3&6\end{pmatrix}\ (3\times2),\qquad B^T=\begin{pmatrix}1&2&-1\\0&1&3\end{pmatrix}\ (2\times3).$$

## 2. The product $AB$

$A$ is $2\times3$ and $B$ is $3\times2$, so $AB$ is $2\times2$:

$$AB=\begin{pmatrix}1\cdot1+2\cdot2+3\cdot(-1) & 1\cdot0+2\cdot1+3\cdot3\\ 4\cdot1+5\cdot2+6\cdot(-1) & 4\cdot0+5\cdot1+6\cdot3\end{pmatrix}=\begin{pmatrix}2&11\\8&23\end{pmatrix}.$$

Therefore

$$(AB)^T=\begin{pmatrix}2&8\\11&23\end{pmatrix}.$$

## 3. The product $B^TA^T$

$B^T$ is $2\times3$ and $A^T$ is $3\times2$, so $B^TA^T$ is $2\times2$:

$$B^TA^T=\begin{pmatrix}1\cdot1+2\cdot2+(-1)\cdot3 & 1\cdot4+2\cdot5+(-1)\cdot6\\ 0\cdot1+1\cdot2+3\cdot3 & 0\cdot4+1\cdot5+3\cdot6\end{pmatrix}=\begin{pmatrix}2&8\\11&23\end{pmatrix}.$$

## 4. Comparison

$$(AB)^T=\begin{pmatrix}2&8\\11&23\end{pmatrix}=B^TA^T.\ ✓$$

## 5. Why this works in general

$$\big((AB)^T\big)_{ij}=(AB)_{ji}=\sum_k a_{jk}b_{ki}=\sum_k (B^T)_{ik}(A^T)_{kj}=(B^TA^T)_{ij}.$$

The same products appear, but to write them as "row times column" we must put $B^T$ first. This is like taking off socks and shoes: the last thing put on comes off first.

## 6. Quick verification

- Entry $(1,2)$ of $B^TA^T$ uses row 1 of $B^T$ = column 1 of $B$, and column 2 of $A^T$ = row 2 of $A$. That is exactly entry $(2,1)$ of $AB$, which is $8$. ✓
- Sizes: $(AB)^T$ is $2\times2$ and $B^TA^T$ is $2\times2$. ✓

## 7. A concrete example

$A^TB^T$ *is* defined here, but it is $3\times3$:

$$A^TB^T=\begin{pmatrix}1&6&11\\2&9&13\\3&12&15\end{pmatrix},$$

which clearly cannot equal the $2\times2$ matrix $(AB)^T$. So the order reversal is not optional.

## How I would explain this in class

> Transposing swaps rows and columns, so $A^T$ is $3\times2$ and $B^T$ is $2\times3$. I computed $AB=\begin{pmatrix}2&11\\8&23\end{pmatrix}$, so $(AB)^T=\begin{pmatrix}2&8\\11&23\end{pmatrix}$, and $B^TA^T$ gives exactly the same matrix. The order must reverse because a row of $AB$ comes from a row of $A$, and after transposing it becomes a column, which must sit on the right.

## Related workbook topics

- [Exercise 1: Matrix size and entries](problem_01_solution.md)
- [Exercise 3: When can matrices be multiplied?](problem_03_solution.md)
