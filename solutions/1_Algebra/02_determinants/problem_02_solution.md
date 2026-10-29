# Exercise 2. Determinant of a 3×3 Matrix

## The question

For

$$A=\begin{pmatrix}1&2&-1\\0&3&4\\2&1&5\end{pmatrix}$$

compute $\det A$ using Sarrus' rule, then perform one simple check using a determinant property.

## Before calculating: what idea do we need?

**Sarrus' rule** works only for $3\times3$ matrices. Copy the first two columns to the right of the matrix:

$$\begin{array}{ccc|cc}a&b&c&a&b\\d&e&f&d&e\\g&h&i&g&h\end{array}$$

Then

$$\det A=\underbrace{aei+bfg+cdh}_{\text{down-right diagonals}}-\underbrace{(ceg+afh+bdi)}_{\text{down-left diagonals}}.$$

For the check we use a **different** property: adding a multiple of one row to another does **not** change the determinant. This lets us create zeros and recompute quickly.

## 1. Sarrus' rule

$$\begin{array}{ccc|cc}1&2&-1&1&2\\0&3&4&0&3\\2&1&5&2&1\end{array}$$

Down-right diagonals:

$$1\cdot3\cdot5+2\cdot4\cdot2+(-1)\cdot0\cdot1=15+16+0=31.$$

Down-left diagonals:

$$(-1)\cdot3\cdot2+1\cdot4\cdot1+2\cdot0\cdot5=-6+4+0=-2.$$

Therefore

$$\det A=31-(-2)=33.$$

## 2. Check using a row operation

Apply $R_3\leftarrow R_3-2R_1$, which does not change the determinant:

$$R_3-2R_1=(2,1,5)-(2,4,-2)=(0,-3,7),\qquad A'=\begin{pmatrix}1&2&-1\\0&3&4\\0&-3&7\end{pmatrix}.$$

Now the first column is $(1,0,0)^T$, so expanding along it leaves one $2\times2$ determinant:

$$\det A'=1\cdot\det\begin{pmatrix}3&4\\-3&7\end{pmatrix}=21-(-12)=33.\ ✓$$

## 3. Meaning

$\det A=33\neq0$, so $A$ is invertible. Geometrically, $A$ maps the unit cube to a parallelepiped of volume $33$.

## 4. Common mistake

The minus sign in front of the second group of diagonals is often forgotten, or the $-1$ entry loses its sign. Here, forgetting the outer minus would give $31+(-2)=29$ instead of $33$. The independent check catches this kind of error.

## 5. A concrete example

Sarrus' rule does **not** extend to $4\times4$ matrices. For larger matrices we use row operations (as in the check above) or cofactor expansion.

## How I would explain this in class

> I write the first two columns again to the right, add the three down-right diagonal products ($31$) and subtract the three down-left ones ($-2$), so $\det A=33$. To check, I subtract twice row 1 from row 3. That doesn't change the determinant and creates a zero, and the reduced $2\times2$ determinant is again $33$.

## Related workbook topics

- [Exercise 3: Swapping two rows](problem_03_solution.md)
- [Exercise 5: Row operations](problem_05_solution.md)
