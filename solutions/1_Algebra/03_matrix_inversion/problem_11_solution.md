# Exercise 11. Parameter and Invertibility

## The question

For

$$A(t)=\begin{pmatrix}1&t\\t&1\end{pmatrix}$$

find all $t$ for which the matrix is invertible, and then give a formula for $A(t)^{-1}$. Explain what happens to this formula at the excluded values.

## Before calculating: what idea do we need?

When a matrix depends on a parameter $t$, its determinant also becomes a function of $t$.
- A square matrix $A(t)$ is invertible **if and only if** $\det A(t)\neq0$.
- Solving the equation $\det A(t)=0$ tells us the exact parameter values that must be **excluded**.
- For all other values of $t$, the standard $2\times2$ inverse formula gives $A(t)^{-1}$ as a function of $t$.

## 1. Compute the determinant and find the invertible values of $t$

Calculate $\det A(t)$:

$$\det A(t) = 1\cdot1 - t\cdot t = 1 - t^2 = (1-t)(1+t).$$

Set the determinant non-zero to find when $A(t)$ is invertible:

$$1 - t^2 \neq 0 \quad\Longleftrightarrow\quad t^2 \neq 1 \quad\Longleftrightarrow\quad t\neq 1 \text{ and } t\neq -1.$$

Thus, $A(t)$ is invertible for all real numbers $t\in\mathbb{R}\setminus\{-1,1\}$.

## 2. Give the formula for $A(t)^{-1}$

For $t\neq\pm1$, apply the $2\times2$ inverse formula (swap the diagonal $1$'s, negate the off-diagonal $t$'s, and divide by $\det A(t)=1-t^2$):

$$A(t)^{-1}=\frac{1}{1-t^2}\begin{pmatrix}1&-t\\-t&1\end{pmatrix}=\begin{pmatrix}\dfrac{1}{1-t^2}&\dfrac{-t}{1-t^2}\\[8pt]\dfrac{-t}{1-t^2}&\dfrac{1}{1-t^2}\end{pmatrix}.$$

## 3. What happens at the excluded values $t=1$ and $t=-1$?

Look at the formula and the matrix itself when $t=\pm1$:
- **In the formula:** The denominator $1-t^2$ becomes $1-(\pm1)^2 = 0$. Every entry of $A(t)^{-1}$ involves **division by zero**, so the expression is undefined (and as $t\to\pm1$, the entries blow up to $\pm\infty$).
- **In the matrix $A(t)$:**
  - At $t=1$, $A(1)=\begin{pmatrix}1&1\\1&1\end{pmatrix}$, where Row 2 equals Row 1 ($R_2=R_1$).
  - At $t=-1$, $A(-1)=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}$, where Row 2 is the negative of Row 1 ($R_2=-R_1$).

In both excluded cases, the two rows become linearly dependent, collapsing the plane onto a line.

## Quick verification

Multiply $A(t)$ by $A(t)^{-1}$ for $t\neq\pm1$:

$$A(t)A(t)^{-1}=\frac{1}{1-t^2}\begin{pmatrix}1&t\\t&1\end{pmatrix}\begin{pmatrix}1&-t\\-t&1\end{pmatrix}=\frac{1}{1-t^2}\begin{pmatrix}1-t^2 & -t+t\\t-t & -t^2+1\end{pmatrix}=\frac{1}{1-t^2}\begin{pmatrix}1-t^2&0\\0&1-t^2\end{pmatrix}=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I.$$

The product simplifies cleanly to $I$ for every $t\neq\pm1$. ✓

## A concrete example

Let us plug in two specific allowed values of $t$:
- **$t=0$:** $A(0)=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I$, and the formula gives $A(0)^{-1}=\frac{1}{1-0}\begin{pmatrix}1&0\\0&1\end{pmatrix}=I$.
- **$t=2$:** $A(2)=\begin{pmatrix}1&2\\2&1\end{pmatrix}$, and the formula gives

$$A(2)^{-1}=\frac{1}{1-4}\begin{pmatrix}1&-2\\-2&1\end{pmatrix}=-\frac{1}{3}\begin{pmatrix}1&-2\\-2&1\end{pmatrix}=\begin{pmatrix}-\frac{1}{3}&\frac{2}{3}\\\frac{2}{3}&-\frac{1}{3}\end{pmatrix}.$$

Checking $A(2)A(2)^{-1}$ gives $-\frac{1}{3}\begin{pmatrix}-3&0\\0&-3\end{pmatrix}=I$.

## How I would explain this in class

> To see when $A(t)$ is invertible, we compute its determinant: $1-t^2$. This is non-zero whenever $t\neq1$ and $t\neq-1$. For all other $t$, the $2\times2$ formula gives $A(t)^{-1}=\frac{1}{1-t^2}\begin{pmatrix}1&-t\\-t&1\end{pmatrix}$. At the excluded values $t=\pm1$, the denominator $1-t^2$ hits zero—so the formula divides by zero—and the two rows of $A(t)$ become identical or opposite, making the matrix singular.

## Related workbook topics

- [Exercise 2: Formula for a 2×2 Matrix](problem_02_solution.md)
- [Exercise 3: When Does the Inverse Not Exist?](problem_03_solution.md)
