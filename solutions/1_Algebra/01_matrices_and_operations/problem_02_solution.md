# Exercise 2. Addition and Scalar Multiplication

## The question

For

$$A=\begin{pmatrix}1&2\\-1&3\end{pmatrix},\qquad B=\begin{pmatrix}4&-2\\0&5\end{pmatrix}$$

compute

$$A+B,\qquad A-B,\qquad 3A-2B,$$

and explain why matrix addition is possible only for matrices of the same size.

## Before calculating: what idea do we need?

Addition and scalar multiplication are **entry-by-entry** operations:

- $(A+B)_{ij}=a_{ij}+b_{ij}$: add the numbers that sit in the same position.
- $(cA)_{ij}=c\,a_{ij}$: multiply every entry by the number $c$.

So we just need to work position by position. No rows-times-columns is involved here.

## 1. Sum $A+B$

$$A+B=\begin{pmatrix}1+4&2+(-2)\\-1+0&3+5\end{pmatrix}=\begin{pmatrix}5&0\\-1&8\end{pmatrix}.$$

## 2. Difference $A-B$

$$A-B=\begin{pmatrix}1-4&2-(-2)\\-1-0&3-5\end{pmatrix}=\begin{pmatrix}-3&4\\-1&-2\end{pmatrix}.$$

## 3. Linear combination $3A-2B$

First scale each matrix:

$$3A=\begin{pmatrix}3&6\\-3&9\end{pmatrix},\qquad 2B=\begin{pmatrix}8&-4\\0&10\end{pmatrix}.$$

Then subtract entry by entry:

$$3A-2B=\begin{pmatrix}3-8&6-(-4)\\-3-0&9-10\end{pmatrix}=\begin{pmatrix}-5&10\\-3&-1\end{pmatrix}.$$

## 4. Why must the sizes be equal?

Addition pairs each entry of $A$ with the entry of $B$ **in the same position**. If the sizes differ, some positions exist in one matrix but not in the other. For example, with

$$\begin{pmatrix}1&2\\3&4\end{pmatrix}+\begin{pmatrix}1&2&3\\4&5&6\end{pmatrix},$$

the entry in row 1, column 3 has no partner in the first matrix. There is no sensible way to fill it in, so the sum is **undefined**.

## 5. Quick verification

- $(A+B)+(A-B)$ should equal $2A$:
$$\begin{pmatrix}5&0\\-1&8\end{pmatrix}+\begin{pmatrix}-3&4\\-1&-2\end{pmatrix}=\begin{pmatrix}2&4\\-2&6\end{pmatrix}=2A.\ ✓$$
- Check $3A-2B$ another way, using the results already found. Since $\tfrac12(A+B)+\tfrac52(A-B)=3A-2B$:
$$\tfrac12\begin{pmatrix}5&0\\-1&8\end{pmatrix}+\tfrac52\begin{pmatrix}-3&4\\-1&-2\end{pmatrix}=\begin{pmatrix}2.5-7.5&0+10\\-0.5-2.5&4-5\end{pmatrix}=\begin{pmatrix}-5&10\\-3&-1\end{pmatrix}.\ ✓$$

## 6. A concrete example

Think of $A$ and $B$ as tables of scores in two rounds of a game (rows = players, columns = games). $A+B$ is the total score table. Adding a $2\times2$ table to a $2\times3$ table would mean adding a score for a game that one round never had, which makes no sense.

## How I would explain this in class

> Addition and scalar multiplication work position by position. I add matching entries and get $A+B=\begin{pmatrix}5&0\\-1&8\end{pmatrix}$, $A-B=\begin{pmatrix}-3&4\\-1&-2\end{pmatrix}$, and after scaling, $3A-2B=\begin{pmatrix}-5&10\\-3&-1\end{pmatrix}$. Because each entry needs a partner in the same position, both matrices must have exactly the same size.

## Related workbook topics

- [Exercise 1: Matrix size and entries](problem_01_solution.md)
- [Exercise 3: When can matrices be multiplied?](problem_03_solution.md)
