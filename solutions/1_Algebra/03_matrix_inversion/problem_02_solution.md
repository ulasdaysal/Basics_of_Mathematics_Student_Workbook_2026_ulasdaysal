# Exercise 2. Formula for a 2×2 Matrix

## The question

Find the inverse of

$$A=\begin{pmatrix}3&2\\5&4\end{pmatrix}$$

using the formula for a $2\times2$ matrix. At the end, check the result by computing one product with $A$.

## Before calculating: what idea do we need?

For a $2\times2$ matrix

$$A=\begin{pmatrix}a&b\\c&d\end{pmatrix},$$

the explicit formula for the inverse is

$$A^{-1}=\frac{1}{\det A}\begin{pmatrix}d&-b\\-c&a\end{pmatrix}=\frac{1}{ad-bc}\begin{pmatrix}d&-b\\-c&a\end{pmatrix},$$

provided $\det A=ad-bc\neq0$.

To remember the matrix part:
- **swap** the main diagonal entries ($a\leftrightarrow d$),
- **change the signs** of the off-diagonal entries ($b\to -b$, $c\to -c$),
- **divide** every entry by the determinant $ad-bc$.

## 1. Compute the determinant

Identify the entries $a=3$, $b=2$, $c=5$, $d=4$:

$$\det A=3\cdot4-2\cdot5=12-10=2.$$

Because $\det A=2\neq0$, the inverse $A^{-1}$ exists.

## 2. Rearrange the entries

Swap the diagonal entries ($3$ and $4$) and negate the off-diagonal entries ($2$ and $5$):

$$\begin{pmatrix}d&-b\\-c&a\end{pmatrix}=\begin{pmatrix}4&-2\\-5&3\end{pmatrix}.$$

## 3. Divide by the determinant

Multiply the rearranged matrix by $\dfrac{1}{\det A}=\dfrac{1}{2}$:

$$A^{-1}=\frac{1}{2}\begin{pmatrix}4&-2\\-5&3\end{pmatrix}=\begin{pmatrix}2&-1\\-\frac{5}{2}&\frac{3}{2}\end{pmatrix}.$$

## 4. Why this formula works

When we multiply $\begin{pmatrix}a&b\\c&d\end{pmatrix}$ by $\begin{pmatrix}d&-b\\-c&a\end{pmatrix}$:
- the off-diagonal products become $a(-b)+b(a)=0$ and $c(d)+d(-c)=0$,
- the diagonal products both become $ad-bc=\det A$.

Dividing by $\det A$ turns the diagonal entries into $1$, producing $I$.

## Quick verification

Compute $AA^{-1}$ using the factored form $\frac{1}{2}\begin{pmatrix}4&-2\\-5&3\end{pmatrix}$:

$$AA^{-1}=\frac{1}{2}\begin{pmatrix}3&2\\5&4\end{pmatrix}\begin{pmatrix}4&-2\\-5&3\end{pmatrix}=\frac{1}{2}\begin{pmatrix}12-10 & -6+6\\20-20 & -10+12\end{pmatrix}=\frac{1}{2}\begin{pmatrix}2&0\\0&2\end{pmatrix}=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I.$$

The product is the identity matrix $I$. ✓

## A concrete example

Let us see how $A$ and $A^{-1}$ act on the basis vector $e_1=\begin{pmatrix}1\\0\end{pmatrix}$:

$$Ae_1=\begin{pmatrix}3&2\\5&4\end{pmatrix}\begin{pmatrix}1\\0\end{pmatrix}=\begin{pmatrix}3\\5\end{pmatrix}.$$

Now apply $A^{-1}$ to $\begin{pmatrix}3\\5\end{pmatrix}$:

$$A^{-1}\begin{pmatrix}3\\5\end{pmatrix}=\begin{pmatrix}2&-1\\-\frac{5}{2}&\frac{3}{2}\end{pmatrix}\begin{pmatrix}3\\5\end{pmatrix}=\begin{pmatrix}6-5\\-\frac{15}{2}+\frac{15}{2}\end{pmatrix}=\begin{pmatrix}1\\0\end{pmatrix}=e_1.$$

## How I would explain this in class

> First, I calculate the determinant: $3\cdot4 - 2\cdot5 = 12 - 10 = 2$. Since it isn't zero, the matrix is invertible. Next, I swap $3$ and $4$ on the main diagonal, put minus signs on $2$ and $5$, and divide everything by $2$. Multiplying the original matrix by our result gives $\frac{1}{2}\begin{pmatrix}2&0\\0&2\end{pmatrix}=I$, which proves the inverse is correct.

## Related workbook topics

- [Exercise 1: Definition of the Inverse](problem_01_solution.md)
- [Exercise 3: When Does the Inverse Not Exist?](problem_03_solution.md)
