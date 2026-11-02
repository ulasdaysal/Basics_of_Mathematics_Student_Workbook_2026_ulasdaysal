# Exercise 9. Matrix Equation

## The question

Given

$$A=\begin{pmatrix}1&2\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}3&1\\2&4\end{pmatrix}.$$

Solve the equation $AX=B$ for $X$. Before calculating, decide on which side of the equation $A^{-1}$ must be used. Then check the result by computing $AX$.

## Before calculating: what idea do we need?

Matrix multiplication is **not commutative** ($AB\neq BA$ in general). Because of this, we must be careful about **which side** we multiply by $A^{-1}$:

- In $AX=B$, the matrix $A$ sits on the **left** of $X$.
- To cancel $A$ next to $X$, we must multiply both sides on the **left** by $A^{-1}$:

$$A^{-1}(AX)=A^{-1}B \quad\Longrightarrow\quad (A^{-1}A)X=A^{-1}B \quad\Longrightarrow\quad IX=A^{-1}B \quad\Longrightarrow\quad X=A^{-1}B.$$

If we mistakenly multiplied on the right ($AXA^{-1}=BA^{-1}$), $A$ and $A^{-1}$ would be separated by $X$ and would not cancel!

## 1. Find the inverse $A^{-1}$

Compute the determinant of $A=\begin{pmatrix}1&2\\0&1\end{pmatrix}$:

$$\det A = 1\cdot1 - 2\cdot0 = 1.$$

Using the $2\times2$ inverse formula, swap the diagonal entries ($1$ and $1$) and negate the off-diagonal entries ($2$ and $0$):

$$A^{-1}=\begin{pmatrix}1&-2\\0&1\end{pmatrix}.$$

## 2. Multiply on the left to find $X=A^{-1}B$

Compute the product $A^{-1}B$:

$$X=A^{-1}B=\begin{pmatrix}1&-2\\0&1\end{pmatrix}\begin{pmatrix}3&1\\2&4\end{pmatrix}=\begin{pmatrix}1\cdot3+(-2)\cdot2 & 1\cdot1+(-2)\cdot4\\0\cdot3+1\cdot2 & 0\cdot1+1\cdot4\end{pmatrix}.$$

Simplifying each entry gives

$$X=\begin{pmatrix}3-4 & 1-8\\0+2 & 0+4\end{pmatrix}=\begin{pmatrix}-1&-7\\2&4\end{pmatrix}.$$

## 3. Why multiplying on the right would give the wrong answer

Suppose someone wrote $BA^{-1}$ instead of $A^{-1}B$:

$$BA^{-1}=\begin{pmatrix}3&1\\2&4\end{pmatrix}\begin{pmatrix}1&-2\\0&1\end{pmatrix}=\begin{pmatrix}3&-5\\2&0\end{pmatrix}.$$

If we test this matrix in $AX$, we get $\begin{pmatrix}1&2\\0&1\end{pmatrix}\begin{pmatrix}3&-5\\2&0\end{pmatrix}=\begin{pmatrix}7&-5\\2&0\end{pmatrix}\neq B$. Order matters!

## Quick verification

Check our solution $X=\begin{pmatrix}-1&-7\\2&4\end{pmatrix}$ by computing $AX$:

$$AX=\begin{pmatrix}1&2\\0&1\end{pmatrix}\begin{pmatrix}-1&-7\\2&4\end{pmatrix}=\begin{pmatrix}-1+4 & -7+8\\0+2 & 0+4\end{pmatrix}=\begin{pmatrix}3&1\\2&4\end{pmatrix}=B.$$

The product equals $B$. ✓

## A concrete example

Solving $AX=B$ for a $2\times2$ matrix $X=\begin{pmatrix}x_1&x_2\end{pmatrix}$ is the same as solving two vector systems at the same time:
- $Ax_1 = \begin{pmatrix}3\\2\end{pmatrix}$ gives the first column $x_1 = A^{-1}\begin{pmatrix}3\\2\end{pmatrix} = \begin{pmatrix}-1\\2\end{pmatrix}$,
- $Ax_2 = \begin{pmatrix}1\\4\end{pmatrix}$ gives the second column $x_2 = A^{-1}\begin{pmatrix}1\\4\end{pmatrix} = \begin{pmatrix}-7\\4\end{pmatrix}$.

Putting the two columns side by side produces $X=\begin{pmatrix}-1&-7\\2&4\end{pmatrix}$.

## How I would explain this in class

> Because $A$ is on the left of $X$ in $AX=B$, we must multiply both sides on the left by $A^{-1}$ so that $A^{-1}A$ cancels to $I$, leaving $X=A^{-1}B$. Since $A=\begin{pmatrix}1&2\\0&1\end{pmatrix}$ has determinant $1$, its inverse is simply $\begin{pmatrix}1&-2\\0&1\end{pmatrix}$. Multiplying $A^{-1}B$ gives $X=\begin{pmatrix}-1&-7\\2&4\end{pmatrix}$, and checking $AX$ recovers $B$.

## Related workbook topics

- [Exercise 6: Solving a System Using the Inverse](problem_06_solution.md)
- [Exercise 7: Inverse of a Product](problem_07_solution.md)
