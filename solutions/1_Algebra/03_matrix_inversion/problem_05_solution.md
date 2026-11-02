# Exercise 5. A 3×3 Matrix

## The question

Use Gauss–Jordan elimination to find the inverse of

$$A=\begin{pmatrix}1&1&0\\0&1&1\\1&0&1\end{pmatrix}.$$

Check the result by multiplication.

## Before calculating: what idea do we need?

For a $3\times3$ matrix, there is no one-line swap-and-negate formula like in the $2\times2$ case. Instead, we use **Gauss–Jordan elimination**:

$$[A\mid I_3] \;\xrightarrow{\text{row operations}}\; [I_3\mid A^{-1}].$$

We work column by column from left to right:
1. get a pivot of $1$ on the diagonal,
2. clear all entries below (and above) that pivot to $0$.

## 1. Set up $[A\mid I_3]$ and clear Column 1

Write the $3\times3$ augmented matrix:

$$\left(\begin{array}{ccc|ccc}1&1&0&1&0&0\\0&1&1&0&1&0\\1&0&1&0&0&1\end{array}\right).$$

Eliminate the $1$ at the bottom of Column 1 using $R_3 \leftarrow R_3 - R_1$:

$$\left(\begin{array}{ccc|ccc}1&1&0&1&0&0\\0&1&1&0&1&0\\0&-1&1&-1&0&1\end{array}\right).$$

## 2. Clear below the pivot in Column 2

The second pivot (Row 2, Column 2) is already $1$. Eliminate the $-1$ below it using $R_3 \leftarrow R_3 + R_2$:

$$\left(\begin{array}{ccc|ccc}1&1&0&1&0&0\\0&1&1&0&1&0\\0&0&2&-1&1&1\end{array}\right).$$

## 3. Scale the pivot in Column 3 and eliminate upward

Divide Row 3 by $2$ ($R_3 \leftarrow \frac{1}{2}R_3$) so the third pivot becomes $1$:

$$\left(\begin{array}{ccc|ccc}1&1&0&1&0&0\\0&1&1&0&1&0\\0&0&1&-\frac{1}{2}&\frac{1}{2}&\frac{1}{2}\end{array}\right).$$

Now eliminate the $1$ above the third pivot using $R_2 \leftarrow R_2 - R_3$:

$$\left(\begin{array}{ccc|ccc}1&1&0&1&0&0\\0&1&0&\frac{1}{2}&\frac{1}{2}&-\frac{1}{2}\\0&0&1&-\frac{1}{2}&\frac{1}{2}&\frac{1}{2}\end{array}\right).$$

Finally, eliminate the $1$ above the second pivot using $R_1 \leftarrow R_1 - R_2$:

$$\left(\begin{array}{ccc|ccc}1&0&0&\frac{1}{2}&-\frac{1}{2}&\frac{1}{2}\\0&1&0&\frac{1}{2}&\frac{1}{2}&-\frac{1}{2}\\0&0&1&-\frac{1}{2}&\frac{1}{2}&\frac{1}{2}\end{array}\right).$$

## 4. Read off the inverse

The left half is now $I_3$, so the right half is $A^{-1}$:

$$A^{-1}=\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}&\frac{1}{2}\\\frac{1}{2}&\frac{1}{2}&-\frac{1}{2}\\-\frac{1}{2}&\frac{1}{2}&\frac{1}{2}\end{pmatrix}=\frac{1}{2}\begin{pmatrix}1&-1&1\\1&1&-1\\-1&1&1\end{pmatrix}.$$

## Quick verification

Multiply $A$ by $A^{-1}$, keeping the factor $\frac{1}{2}$ in front for clean arithmetic:

$$AA^{-1}=\frac{1}{2}\begin{pmatrix}1&1&0\\0&1&1\\1&0&1\end{pmatrix}\begin{pmatrix}1&-1&1\\1&1&-1\\-1&1&1\end{pmatrix}=\frac{1}{2}\begin{pmatrix}1+1+0 & -1+1+0 & 1-1+0\\0+1-1 & 0+1+1 & 0-1+1\\1+0-1 & -1+0+1 & 1+0+1\end{pmatrix}=\frac{1}{2}\begin{pmatrix}2&0&0\\0&2&0\\0&0&2\end{pmatrix}=I_3.$$

Every entry matches the $3\times3$ identity matrix. ✓

## A concrete example

Look at what $A$ does to a vector $x=(x_1,x_2,x_3)^T$:

$$Ax=\begin{pmatrix}x_1+x_2\\x_2+x_3\\x_1+x_3\end{pmatrix}=\begin{pmatrix}s_1\\s_2\\s_3\end{pmatrix}.$$

Each output component is the sum of two input components! How do we recover $x_1$ from the pairwise sums $s_1,s_2,s_3$? Add the two sums that contain $x_1$ ($s_1$ and $s_3$) and subtract the sum that doesn't ($s_2$):

$$s_1 - s_2 + s_3 = (x_1+x_2) - (x_2+x_3) + (x_1+x_3) = 2x_1 \quad\Longrightarrow\quad x_1 = \frac{1}{2}(s_1 - s_2 + s_3).$$

That coefficient pattern $\frac{1}{2}(1, -1, 1)$ is the exact first row of $A^{-1}$!

## How I would explain this in class

> We set up the $3\times6$ augmented matrix $[A\mid I_3]$. First we subtract Row 1 from Row 3, then add Row 2 to Row 3 to get upper-triangular form with $2$ in the bottom-right corner. After dividing Row 3 by $2$, we work back upward—subtracting Row 3 from Row 2, and Row 2 from Row 1—until $I_3$ appears on the left. Factoring out $\frac{1}{2}$ makes checking $AA^{-1}=I_3$ super fast.

## Related workbook topics

- [Exercise 4: Gauss–Jordan](problem_04_solution.md)
- [Exercise 10: Inverse of a Diagonal Matrix](problem_10_solution.md)
