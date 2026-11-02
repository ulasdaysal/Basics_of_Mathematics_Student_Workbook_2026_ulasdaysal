# Exercise 8. Two Systems with the Same Coefficient Matrix

## The question

Solve by elimination the two systems

$$\begin{cases}2x+y=5,\\x-y=1,\end{cases} \qquad \begin{cases}2x+y=1,\\x-y=4.\end{cases}$$

Compare the successive elimination steps. Which part of the calculation is the same in both cases, and why?

## Before calculating: what idea do we need?

In Gaussian elimination, **which row operations we perform** (which rows we swap, and what multiples we subtract) is dictated entirely by the **coefficient matrix $A$**, because our goal is to create zeros in the columns of $A$. The right-hand side vector $b$ is just a passenger that gets carried along by those exact same row operations.

## 1. Solving the first system by elimination

Write the augmented matrix for the first system:

$$\left[\begin{array}{cc|c}
2 & 1 & 5 \\
1 & -1 & 1
\end{array}\right].$$

**Step 1:** Swap row 1 and row 2 ($R_1 \leftrightarrow R_2$) to put a pivot of $1$ in the top-left corner:

$$\left[\begin{array}{cc|c}
1 & -1 & 1 \\
2 & 1 & 5
\end{array}\right].$$

**Step 2:** Eliminate $x$ from the second row by performing $R_2 \leftarrow R_2 - 2R_1$:

$$\left[\begin{array}{cc|c}
1 & -1 & 1 \\
0 & 3 & 3
\end{array}\right].$$

**Step 3:** Back-substitution:
- From row 2: $3y = 3 \implies y = 1$.
- From row 1: $x - y = 1 \implies x = 1 + y = 1 + 1 = 2$.

So the solution to the first system is $(x, y) = (2, 1)$.

## 2. Solving the second system by elimination

Write the augmented matrix for the second system:

$$\left[\begin{array}{cc|c}
2 & 1 & 1 \\
1 & -1 & 4
\end{array}\right].$$

**Step 1:** Swap row 1 and row 2 ($R_1 \leftrightarrow R_2$):

$$\left[\begin{array}{cc|c}
1 & -1 & 4 \\
2 & 1 & 1
\end{array}\right].$$

**Step 2:** Eliminate $x$ from the second row by performing $R_2 \leftarrow R_2 - 2R_1$:

$$\left[\begin{array}{cc|c}
1 & -1 & 4 \\
0 & 3 & 1 - 2(4)
\end{array}\right] = \left[\begin{array}{cc|c}
1 & -1 & 4 \\
0 & 3 & -7
\end{array}\right].$$

**Step 3:** Back-substitution:
- From row 2: $3y = -7 \implies y = -\frac{7}{3}$.
- From row 1: $x - y = 4 \implies x = 4 + y = 4 - \frac{7}{3} = \frac{5}{3}$.

So the solution to the second system is $(x, y) = \left(\frac{5}{3}, -\frac{7}{3}\right)$.

## 3. Comparing the elimination steps: what is the same and why?

Comparing the two calculations side by side:
1. **The sequence of row operations** ($R_1 \leftrightarrow R_2$, followed by $R_2 \leftarrow R_2 - 2R_1$) is **100% identical** in both systems.
2. **The left-hand side of the augmented matrix** transforms in the exact same way in both cases:
   $$\begin{pmatrix} 2 & 1 \\ 1 & -1 \end{pmatrix} \xrightarrow{R_1 \leftrightarrow R_2} \begin{pmatrix} 1 & -1 \\ 2 & 1 \end{pmatrix} \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \begin{pmatrix} 1 & -1 \\ 0 & 3 \end{pmatrix}.$$

**Why?** Because the row operations are chosen solely to eliminate entries in the coefficient matrix $A = \begin{pmatrix} 2 & 1 \\ 1 & -1 \end{pmatrix}$. The numbers on the right-hand side never influence which multiple of row 1 is subtracted from row 2; only the final arithmetic in the last column changes.

## Quick verification

Let us check both solutions in their original equations:
- **First system with $(x,y) = (2,1)$:**
  $$2(2) + 1 = 5 \quad \text{✓}, \qquad 2 - 1 = 1 \quad \text{✓}.$$
- **Second system with $(x,y) = \left(\frac{5}{3}, -\frac{7}{3}\right)$:**
  $$2\left(\frac{5}{3}\right) + \left(-\frac{7}{3}\right) = \frac{10 - 7}{3} = 1 \quad \text{✓}, \qquad \frac{5}{3} - \left(-\frac{7}{3}\right) = \frac{12}{3} = 4 \quad \text{✓}.$$

## A concrete example

Because the operations on $A$ are identical, mathematicians often solve both systems **simultaneously** in a single doubly-augmented matrix $[A \mid b_1 \;\; b_2]$:

$$\left[\begin{array}{cc|cc}
2 & 1 & 5 & 1 \\
1 & -1 & 1 & 4
\end{array}\right] \xrightarrow{R_1 \leftrightarrow R_2}
\left[\begin{array}{cc|cc}
1 & -1 & 1 & 4 \\
2 & 1 & 5 & 1
\end{array}\right] \xrightarrow{R_2 - 2R_1}
\left[\begin{array}{cc|cc}
1 & -1 & 1 & 4 \\
0 & 3 & 3 & -7
\end{array}\right].$$

This avoids reducing the coefficient matrix twice and shows clearly how $A$ governs the elimination process.

## How I would explain this in class

> Both systems share the same coefficient matrix $A = \begin{pmatrix} 2 & 1 \\ 1 & -1 \end{pmatrix}$. Since row operations are picked to make zeros in $A$, we do the exact same steps—swap rows 1 and 2, then subtract twice row 1 from row 2—and get the exact same upper triangular matrix $\begin{pmatrix} 1 & -1 \\ 0 & 3 \end{pmatrix}$ on the left. Only the right-hand column changes, which is why we can even tack both right-hand sides onto $A$ at once and reduce them together.

## Related workbook topics

- [Exercise 1: From a System to a Matrix](problem_01_solution.md)
- [Exercise 7: Choosing a Method Deliberately](problem_07_solution.md)
