# Exercise 3. Inconsistent System

## The question

Solve or show that the system is inconsistent:

$$\begin{cases}x+2y=3,\\2x+4y=7.\end{cases}$$

Show how the contradiction appears in the matrix after elimination and interpret it in terms of equations.

## Before calculating: what idea do we need?

A system of equations is **inconsistent** (has no solution) when its requirements contradict one another. Gaussian elimination detects this automatically without any guesswork: if elimination produces a row with **all zeros on the left (coefficient) side** and a **non-zero number on the right-hand side**,

$$\left[\begin{array}{cc|c} 0 & 0 & c \end{array}\right] \quad \text{with } c \neq 0,$$

that row translates to the impossible equation $0 = c$. Since no choice of variables can make $0$ equal a non-zero number, no solution exists.

## 1. Elimination on the augmented matrix

Write the augmented matrix of the system:

$$\left[\begin{array}{cc|c}
1 & 2 & 3 \\
2 & 4 & 7
\end{array}\right].$$

To eliminate $x$ from the second row, subtract twice the first row from the second row ($R_2 \leftarrow R_2 - 2R_1$):

$$\left[\begin{array}{cc|c}
1 & 2 & 3 \\
2 - 2(1) & 4 - 2(2) & 7 - 2(3)
\end{array}\right] = \left[\begin{array}{cc|c}
1 & 2 & 3 \\
0 & 0 & 1
\end{array}\right].$$

## 2. How the contradiction appears and what it means

Look at the second row of the reduced matrix:

$$\left[\begin{array}{cc|c} 0 & 0 & 1 \end{array}\right].$$

Rewriting this row as an equation in $x$ and $y$ gives:

$$0x + 0y = 1 \implies 0 = 1.$$

This is a direct contradiction. Because row operations are reversible, the original system is logically equivalent to the reduced system

$$\begin{cases} x + 2y = 3, \\ 0 = 1. \end{cases}$$

Since $0 = 1$ is false for every pair $(x,y) \in \mathbb{R}^2$, the system is **inconsistent** (it has **no solution**).

## 3. Interpretation in terms of the original equations

Why did both $x$ and $y$ vanish at the same time? Look at the left-hand sides of the two original equations:
- The left-hand side of the second equation is $2x + 4y = 2(x + 2y)$, which is **exact twice** the left-hand side of the first equation.
- If $x + 2y = 3$ is true, then doubling the expression must give $2(x+2y) = 2(3) = 6$.
- However, the second equation demands that $2x + 4y = 7$.

The quantity $2x+4y$ cannot equal both $6$ and $7$ at the same time.

## Quick verification

Let us verify the inconsistency geometrically by putting both equations in slope-intercept form ($y = mx + b$):

- First line: $x + 2y = 3 \implies y = -\frac{1}{2}x + \frac{3}{2}$.
- Second line: $2x + 4y = 7 \implies y = -\frac{1}{2}x + \frac{7}{4}$.

Both lines have the exact same slope $m = -\frac{1}{2}$, but different $y$-intercepts ($\frac{3}{2} = 1.5$ vs. $\frac{7}{4} = 1.75$). Distinct parallel lines in the plane never intersect, so there is no common point $(x,y)$. ✓

## A concrete example

Imagine a store where:
- Today, $1$ notebook and $2$ pens cost $\$3$ ($x + 2y = 3$).
- Later the same day, with unchanged prices, someone claims that $2$ notebooks and $4$ pens cost $\$7$ ($2x + 4y = 7$).

Buying two identical bundles of $(1\text{ notebook} + 2\text{ pens})$ must cost $2 \times \$3 = \$6$, not $\$7$. The two receipts contradict each other, so no fixed unit prices $(x,y)$ can fit both statements.

## How I would explain this in class

> When we subtract twice the first row from the second row to eliminate $x$, the $y$-term disappears at the exact same moment because the coefficients $(2,4)$ are proportional to $(1,2)$. That leaves the row $[0\;\;0\mid 1]$, which says $0x + 0y = 1$, or $0=1$. In terms of the equations, if $x+2y$ is $3$, then $2x+4y$ has to be $6$, so asking it to be $7$ is impossible—geometrically, we have two parallel lines that never meet.

## Related workbook topics

- [Exercise 6: A System with a Parameter — Which Cases Actually Occur?](problem_06_solution.md)
- [Exercise 15: Classifying Three Systems](problem_15_solution.md)
