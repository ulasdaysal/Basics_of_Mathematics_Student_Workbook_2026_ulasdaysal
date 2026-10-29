# Exercise 5. Matrix Times Vector

## The question

Let

$$A=\begin{pmatrix}2&-1\\1&3\end{pmatrix},\qquad x=\begin{pmatrix}4\\2\end{pmatrix}.$$

Compute $Ax$, then express $Ax$ as a linear combination of the columns of $A$ with coefficients from $x$.

## Before calculating: what idea do we need?

There are two equivalent ways to see $Ax$:

1. **Row view:** each entry of $Ax$ is a row of $A$ dotted with $x$.
2. **Column view:** $Ax$ is a combination of the columns of $A$, weighted by the entries of $x$:
$$A\begin{pmatrix}x_1\\x_2\end{pmatrix}=x_1\,a_1+x_2\,a_2,$$
where $a_1,a_2$ are the columns of $A$.

The row view is good for computing. The column view explains what the result *means*: $Ax$ always lies in the set of combinations of the columns of $A$.

## 1. Row view: compute $Ax$

$$Ax=\begin{pmatrix}2\cdot4+(-1)\cdot2\\1\cdot4+3\cdot2\end{pmatrix}=\begin{pmatrix}8-2\\4+6\end{pmatrix}=\begin{pmatrix}6\\10\end{pmatrix}.$$

## 2. Column view: linear combination of columns

The columns of $A$ are

$$a_1=\begin{pmatrix}2\\1\end{pmatrix},\qquad a_2=\begin{pmatrix}-1\\3\end{pmatrix}.$$

Using the coefficients $x_1=4$, $x_2=2$:

$$Ax=4\begin{pmatrix}2\\1\end{pmatrix}+2\begin{pmatrix}-1\\3\end{pmatrix}=\begin{pmatrix}8\\4\end{pmatrix}+\begin{pmatrix}-2\\6\end{pmatrix}=\begin{pmatrix}6\\10\end{pmatrix}.$$

## 3. Why the two views agree

Write out the row view symbolically:

$$Ax=\begin{pmatrix}a_{11}x_1+a_{12}x_2\\a_{21}x_1+a_{22}x_2\end{pmatrix}=x_1\begin{pmatrix}a_{11}\\a_{21}\end{pmatrix}+x_2\begin{pmatrix}a_{12}\\a_{22}\end{pmatrix}.$$

It is the same sum of products, only grouped differently: by rows in the first view, by columns in the second.

## 4. Meaning

The vector $x$ is a "recipe": take 4 copies of the first column and 2 copies of the second column. A matrix therefore sends the standard basis vectors to its columns:

$$Ae_1=a_1,\qquad Ae_2=a_2,$$

and every other vector is sent to the matching combination of these columns.

## 5. Quick verification

Both methods gave $\begin{pmatrix}6\\10\end{pmatrix}$. ✓

Also, by linearity, $Ax=A(4e_1+2e_2)=4Ae_1+2Ae_2=4a_1+2a_2$, which is exactly the column view.

## 6. A concrete example

If $x=\begin{pmatrix}1\\0\end{pmatrix}$, then $Ax=\begin{pmatrix}2\\1\end{pmatrix}=a_1$, just the first column. If $x=\begin{pmatrix}1\\1\end{pmatrix}$, then $Ax=a_1+a_2=\begin{pmatrix}1\\4\end{pmatrix}$.

## How I would explain this in class

> I can compute $Ax$ row by row: $(2\cdot4-1\cdot2,\ 1\cdot4+3\cdot2)=(6,10)$. But a better way to think about it is that $x$ tells me how much of each column to take: 4 times the first column plus 2 times the second column, which again gives $(6,10)$. So $Ax$ is always a linear combination of the columns of $A$.

## Related workbook topics

- [Exercise 10: Columns of a matrix product](problem_10_solution.md)
- [Exercise 9: Composing transformations](problem_09_solution.md)
