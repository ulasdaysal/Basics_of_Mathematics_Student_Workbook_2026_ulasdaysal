# Exercise 15. Two Methods for Solving the Same System

## The question

For

$$A=\begin{pmatrix}2&1\\1&3\end{pmatrix},\qquad b=\begin{pmatrix}7\\8\end{pmatrix}$$

solve $Ax=b$ in two ways:

1. using $A^{-1}b$,
2. using Gaussian elimination.

Compare both solutions, the number of essential steps, and state which method was simpler in this example.

## Before calculating: what idea do we need?

We have two standard tools for solving an invertible linear system $Ax=b$:
1. **The inverse method ($x=A^{-1}b$):** First compute the entire inverse matrix $A^{-1}$, then multiply it by $b$.
2. **Gaussian elimination (row reduction on $[A\mid b]$):** Row-reduce the augmented matrix directly to upper-triangular (echelon) form and use back-substitution.

Both methods must produce the exact same unique solution $x$, because $Ax=b$ has only one solution when $\det A\neq0$.

## 1. Method 1: Solve using $x=A^{-1}b$

**Step 1a (Determinant):**

$$\det A = 2\cdot3 - 1\cdot1 = 6 - 1 = 5.$$

**Step 1b (Form $A^{-1}$):** Swap the diagonal entries ($2$ and $3$), negate the off-diagonal entries ($1$ and $1$), and divide by $5$:

$$A^{-1}=\frac{1}{5}\begin{pmatrix}3&-1\\-1&2\end{pmatrix}.$$

**Step 1c (Multiply $A^{-1}b$):**

$$x=A^{-1}b=\frac{1}{5}\begin{pmatrix}3&-1\\-1&2\end{pmatrix}\begin{pmatrix}7\\8\end{pmatrix}=\frac{1}{5}\begin{pmatrix}21-8\\-7+16\end{pmatrix}=\frac{1}{5}\begin{pmatrix}13\\9\end{pmatrix}=\begin{pmatrix}\frac{13}{5}\\\frac{9}{5}\end{pmatrix}.$$

## 2. Method 2: Solve using Gaussian elimination

Set up the augmented matrix $[A\mid b]$:

$$\left(\begin{array}{cc|c}2&1&7\\1&3&8\end{array}\right).$$

**Step 2a (Swap rows to get a pivot of $1$ in the top-left):** Swap $R_1\leftrightarrow R_2$ so we avoid fractions during elimination:

$$\left(\begin{array}{cc|c}1&3&8\\2&1&7\end{array}\right).$$

**Step 2b (Eliminate $x_1$ from Row 2):** Replace $R_2 \leftarrow R_2 - 2R_1$:

$$\left(\begin{array}{cc|c}1&3&8\\2-2(1)&1-2(3)&7-2(8)\end{array}\right)=\left(\begin{array}{cc|c}1&3&8\\0&-5&-9\end{array}\right).$$

**Step 2c (Back-substitution):**
- From Row 2: $-5x_2 = -9 \implies x_2 = \dfrac{9}{5}$.
- From Row 1: $x_1 = 8 - 3x_2 = 8 - 3\left(\dfrac{9}{5}\right) = \dfrac{40-27}{5} = \dfrac{13}{5}$.

So once again,

$$x=\begin{pmatrix}\frac{13}{5}\\\frac{9}{5}\end{pmatrix}.$$

## 3. Comparison of the two methods

- **Agreement of solutions:** Both methods give the exact same vector $x=\left(\frac{13}{5},\frac{9}{5}\right)^T$.
- **Number of essential steps:**
  - For this **single $2\times2$ system**, Method 1 ($x=A^{-1}b$) requires 1 determinant calculation ($2\cdot3-1\cdot1=5$), swapping/negating entries, and 1 matrix-vector product ($4$ multiplications and $2$ additions).
  - Method 2 (Gaussian elimination) requires 1 row swap, 1 row elimination ($R_2-2R_1$), and back-substitution with fractions ($8 - \frac{27}{5}$).
- **Which method was simpler here, and when does that change?**
  - **For a $2\times2$ system**, $x=A^{-1}b$ is slightly more direct (or equally fast) because we have the instant $2\times2$ shortcut formula for $A^{-1}$ and we can keep $\frac{1}{5}$ factored out until the very last step.
  - **Also, if we have multiple right-hand sides** $b^{(1)}, b^{(2)}, \dots$ with the **same** matrix $A$ (for instance, notice that we already inverted this exact matrix $A=\begin{pmatrix}2&1\\1&3\end{pmatrix}$ back in Exercise 6!), then $x=A^{-1}b$ is much faster because $A^{-1}$ is already known.
  - **For $3\times3$ and larger systems with a single vector $b$**, Gaussian elimination is much simpler and faster because finding $A^{-1}$ requires reducing $[A\mid I_n]$ (which has $n$ columns on the right instead of just $1$ column $b$).

## Quick verification

Substitute $x=\begin{pmatrix}\frac{13}{5}\\\frac{9}{5}\end{pmatrix}$ back into the original system $Ax=b$:

$$Ax=\begin{pmatrix}2&1\\1&3\end{pmatrix}\begin{pmatrix}\frac{13}{5}\\\frac{9}{5}\end{pmatrix}=\begin{pmatrix}\frac{26+9}{5}\\\frac{13+27}{5}\end{pmatrix}=\begin{pmatrix}\frac{35}{5}\\\frac{40}{5}\end{pmatrix}=\begin{pmatrix}7\\8\end{pmatrix}=b.$$

Both equations are satisfied! ✓

## A concrete example

Compare solving $Ax=b$ here with Exercise 6, where we had the **same** matrix $A=\begin{pmatrix}2&1\\1&3\end{pmatrix}$ and $b^{(1)}=\begin{pmatrix}5\\7\end{pmatrix}$:
- Once $A^{-1}=\frac{1}{5}\begin{pmatrix}3&-1\\-1&2\end{pmatrix}$ is computed once, we can solve for any new vector $b=\begin{pmatrix}b_1\\b_2\end{pmatrix}$ in one line:

$$x=\frac{1}{5}\begin{pmatrix}3b_1-b_2\\-b_1+2b_2\end{pmatrix}.$$

Plugging in $b_1=5,b_2=7$ immediately gave $\frac{1}{5}(8,9)^T$ in Exercise 6, and plugging in $b_1=7,b_2=8$ immediately gives $\frac{1}{5}(13,9)^T$ here.

## How I would explain this in class

> Both $x=A^{-1}b$ and Gaussian elimination give the same solution $x=(13/5, 9/5)^T$. For this $2\times2$ example, $x=A^{-1}b$ is slightly cleaner because the $2\times2$ inverse formula is instant and lets us save the division by $5$ for the very end—especially since we already found $A^{-1}$ in Exercise 6! However, for $3\times3$ or larger matrices with only one right-hand side $b$, Gaussian elimination on $[A\mid b]$ takes far fewer steps than finding the full inverse $A^{-1}$.

## Related workbook topics

- [Exercise 5: A 3×3 Matrix](problem_05_solution.md)
- [Exercise 6: Solving a System Using the Inverse](problem_06_solution.md)
