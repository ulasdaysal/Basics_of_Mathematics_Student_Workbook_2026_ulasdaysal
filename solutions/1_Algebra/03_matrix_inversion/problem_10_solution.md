# Exercise 10. Inverse of a Diagonal Matrix

## The question

Given

$$D=\begin{pmatrix}2&0&0\\0&-3&0\\0&0&5\end{pmatrix},\qquad E=\begin{pmatrix}2&0&0\\0&0&0\\0&0&5\end{pmatrix}.$$

Without using Gauss–Jordan elimination, decide which matrix is invertible. For the invertible matrix, give the inverse and check the result by multiplication.

## Before calculating: what idea do we need?

A **diagonal matrix** has non-zero entries only on its main diagonal:

$$\operatorname{diag}(d_1,d_2,d_3)=\begin{pmatrix}d_1&0&0\\0&d_2&0\\0&0&d_3\end{pmatrix}.$$

When we multiply a vector $(x,y,z)^T$ by this matrix, each coordinate is scaled independently: $(d_1x, d_2y, d_3z)^T$.
- To undo this scaling, we simply divide each coordinate by $d_i$, which requires **every diagonal entry to be non-zero** ($d_1\neq0$, $d_2\neq0$, $d_3\neq0$).
- If even a single diagonal entry is $0$, that coordinate is wiped out ($0\cdot y=0$) and can never be recovered.

## 1. Decide which matrix is invertible

- Look at $D=\operatorname{diag}(2,-3,5)$: all three diagonal entries ($2$, $-3$, and $5$) are non-zero, and $\det D = 2\cdot(-3)\cdot5 = -30\neq0$. Therefore, **$D$ is invertible**.
- Look at $E=\operatorname{diag}(2,0,5)$: the middle diagonal entry is $0$ (in Fact, Row 2 and Column 2 are all zeros), and $\det E = 2\cdot0\cdot5 = 0$. Therefore, **$E$ is not invertible**.

## 2. Write down $D^{-1}$ directly

To invert an invertible diagonal matrix, replace each diagonal entry with its reciprocal:

$$D^{-1}=\begin{pmatrix}\frac{1}{2}&0&0\\0&-\frac{1}{3}&0\\0&0&\frac{1}{5}\end{pmatrix}.$$

No row reduction is needed because the three coordinates never mix with one another.

## 3. Why $E$ cannot be inverted

When $E$ acts on any vector $(x,y,z)^T$, it gives

$$E\begin{pmatrix}x\\y\\z\end{pmatrix}=\begin{pmatrix}2x\\0\\5z\end{pmatrix}.$$

The second coordinate $y$ is completely erased. No matrix can multiply $(2x,0,5z)^T$ and magically reconstruct what $y$ used to be.

## Quick verification

Multiply $D$ and $D^{-1}$ (for diagonal matrices, we just multiply the corresponding diagonal entries):

$$DD^{-1}=\begin{pmatrix}2&0&0\\0&-3&0\\0&0&5\end{pmatrix}\begin{pmatrix}\frac{1}{2}&0&0\\0&-\frac{1}{3}&0\\0&0&\frac{1}{5}\end{pmatrix}=\begin{pmatrix}2\cdot\frac{1}{2}&0&0\\0&(-3)\cdot\left(-\frac{1}{3}\right)&0\\0&0&5\cdot\frac{1}{5}\end{pmatrix}=\begin{pmatrix}1&0&0\\0&1&0\\0&0&1\end{pmatrix}=I_3.$$

The product is the $3\times3$ identity matrix. ✓

## A concrete example

Take two different vectors in $\mathbb{R}^3$ that differ only in their second coordinate:

$$u=\begin{pmatrix}1\\4\\1\end{pmatrix},\qquad v=\begin{pmatrix}1\\99\\1\end{pmatrix}.$$

Under $E$, both vectors collapse to the exact same output:

$$Eu=\begin{pmatrix}2\\0\\5\end{pmatrix}=Ev.$$

Under $D$, however, $Du=\begin{pmatrix}2\\-12\\5\end{pmatrix}$ and $Dv=\begin{pmatrix}2\\-297\\5\end{pmatrix}$ stay distinct, and applying $D^{-1}$ recovers $u$ and $v$ immediately.

## How I would explain this in class

> A diagonal matrix scales each coordinate axis separately, so it is invertible if and only if every number on its main diagonal is non-zero. That means $D$ is invertible because $2, -3, 5$ are all non-zero, while $E$ is not invertible because of the $0$ in the middle of its diagonal. To get $D^{-1}$, we just take the reciprocal of each diagonal entry: $\operatorname{diag}(1/2, -1/3, 1/5)$.

## Related workbook topics

- [Exercise 3: When Does the Inverse Not Exist?](problem_03_solution.md)
- [Exercise 8: Inverse of a Transformation](problem_08_solution.md)
