# Exercise 3. When Does the Inverse Not Exist?

## The question

For

$$A=\begin{pmatrix}2&4\\1&2\end{pmatrix}$$

explain in two ways why $A^{-1}$ does not exist: using the determinant and using dependence between the rows.

## Before calculating: what idea do we need?

A matrix fails to have an inverse (is **singular**) when it collapses space and loses information. We can see this collapse in two equivalent ways:

1. **Via the determinant:** In the $2\times2$ inverse formula, we must divide by $\det A = ad-bc$. If $\det A=0$, division by zero is impossible, and the area scaling factor of the transformation is $0$.
2. **Via row dependence:** If one row is a scalar multiple of another, the two equations in $Ax=b$ are redundant (or contradictory), and row reduction produces a row of zeros instead of the identity matrix $I$.

## 1. First explanation: using the determinant

Compute the determinant of $A$:

$$\det A = 2\cdot2 - 4\cdot1 = 4 - 4 = 0.$$

Because $\det A=0$:
- the $2\times2$ inverse formula $\dfrac{1}{\det A}\begin{pmatrix}d&-b\\-c&a\end{pmatrix}$ would require dividing by $0$,
- for any candidate matrix $B$, the multiplicative property of determinants gives $\det(AB)=(\det A)(\det B)=0\cdot\det B=0$, which can never equal $\det I=1$.

Thus $A^{-1}$ does not exist.

## 2. Second explanation: using row dependence

Compare the two rows of $A$:

$$R_1 = (2,\; 4), \qquad R_2 = (1,\; 2).$$

Notice that the first row is exactly twice the second row:

$$R_1 = 2R_2 \quad\Longleftrightarrow\quad R_1 - 2R_2 = (0,\; 0).$$

Because the rows are linearly dependent:
- during elimination, subtracting $2R_2$ from $R_1$ creates a zero row $(0,0)$, so $A$ can never be row-reduced to the identity matrix $I$,
- in a system $Ax=b$, the first equation $2x_1+4x_2=b_1$ is just $2(x_1+2x_2)=b_1$, so it gives no new information about $x_1$ and $x_2$ beyond the second equation $x_1+2x_2=b_2$.

## 3. How the two explanations connect

The determinant and row dependence are two sides of the same coin:

$$\frac{a}{c}=\frac{b}{d} \quad\Longleftrightarrow\quad ad=bc \quad\Longleftrightarrow\quad ad-bc=0.$$

Saying that the rows are proportional ($(2,4)=2\cdot(1,2)$) is algebraically identical to saying that the cross-products in the determinant cancel out ($2\cdot2-4\cdot1=0$).

## Quick verification

Try to solve $Ax=\begin{pmatrix}0\\0\end{pmatrix}$:

$$\begin{pmatrix}2&4\\1&2\end{pmatrix}\begin{pmatrix}-2\\1\end{pmatrix}=\begin{pmatrix}2(-2)+4(1)\\1(-2)+2(1)\end{pmatrix}=\begin{pmatrix}0\\0\end{pmatrix}.$$

If $A^{-1}$ existed, multiplying $Ax=0$ on the left by $A^{-1}$ would force $x=A^{-1}0=0$. Since the non-zero vector $x=(-2,1)^T$ is sent to $(0,0)^T$, $A$ cannot have an inverse. ✓

## A concrete example

Take two different input vectors, $u=\begin{pmatrix}1\\0\end{pmatrix}$ and $v=\begin{pmatrix}-1\\1\end{pmatrix}$:

$$Au=\begin{pmatrix}2&4\\1&2\end{pmatrix}\begin{pmatrix}1\\0\end{pmatrix}=\begin{pmatrix}2\\1\end{pmatrix},\qquad Av=\begin{pmatrix}2&4\\1&2\end{pmatrix}\begin{pmatrix}-1\\1\end{pmatrix}=\begin{pmatrix}-2+4\\-1+2\end{pmatrix}=\begin{pmatrix}2\\1\end{pmatrix}.$$

Both $u$ and $v$ land on the exact same output $(2,1)^T$. If someone gives us the output $(2,1)^T$, there is no unique way to go backward and tell whether it came from $(1,0)^T$, $(-1,1)^T$, or another vector on the line $x_1+2x_2=1$.

## How I would explain this in class

> We can see $A$ is not invertible in two ways. First, its determinant is $2\cdot2 - 4\cdot1 = 0$, so the inverse formula would divide by zero. Second, the first row $(2,4)$ is just $2$ times the second row $(1,2)$. That means both rows give the exact same relationship between the variables, squashing the whole plane onto a single line so we can never uniquely reverse the transformation.

## Related workbook topics

- [Exercise 2: Formula for a 2×2 Matrix](problem_02_solution.md)
- [Exercise 11: Parameter and Invertibility](problem_11_solution.md)
