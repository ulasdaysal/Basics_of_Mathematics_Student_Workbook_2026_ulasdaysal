# Exercise 2. Gaussian Elimination — One Solution

## The question

Solve using Gaussian elimination:

$$\begin{cases}x+y+z=6,\\2x-y+z=3,\\x+2y-z=2.\end{cases}$$

After solving, substitute the result into all equations and check consistency.

## Before calculating: what idea do we need?

**Gaussian elimination** transforms a coupled system into an **upper triangular** (staircase) system that is easy to solve from bottom to top. We are allowed to add a multiple of one equation (or row) to another without changing the set of solutions, because if two quantities are equal, adding the same thing to both sides keeps them equal.

Our strategy has two phases:
1. **Forward elimination:** Use the first row to eliminate $x$ from rows 2 and 3, then use the new second row to eliminate $y$ from row 3.
2. **Back-substitution:** Read off $z$ from the bottom equation, substitute it upward to find $y$, and finally find $x$.

## 1. Setting up the augmented matrix

We write the coefficients and the right-hand side in an augmented matrix $[A\mid b]$:

$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
2 & -1 & 1 & 3 \\
1 & 2 & -1 & 2
\end{array}\right].$$

## 2. Forward elimination to row echelon form

**Step 1:** Eliminate $x$ (column 1) below the first pivot $1$ in position $(1,1)$.
Perform $R_2 \leftarrow R_2 - 2R_1$ and $R_3 \leftarrow R_3 - R_1$:

$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
2-2(1) & -1-2(1) & 1-2(1) & 3-2(6) \\
1-1 & 2-1 & -1-1 & 2-6
\end{array}\right] = \left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & -3 & -1 & -9 \\
0 & 1 & -2 & -4
\end{array}\right].$$

**Step 2:** Swap $R_2$ and $R_3$ ($R_2 \leftrightarrow R_3$) so that the second pivot is $1$, avoiding fractions:

$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & -3 & -1 & -9
\end{array}\right].$$

**Step 3:** Eliminate $y$ (column 2) below the second pivot.
Perform $R_3 \leftarrow R_3 + 3R_2$:

$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & -3+3(1) & -1+3(-2) & -9+3(-4)
\end{array}\right] = \left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & 0 & -7 & -21
\end{array}\right].$$

## 3. Back-substitution

Translate the staircase matrix back into equations:

$$\begin{cases}
x + y + z = 6,\\
y - 2z = -4,\\
-7z = -21.
\end{cases}$$

Now solve from the bottom up:
- From the third equation:
  $$z = \frac{-21}{-7} = 3.$$
- Substitute $z=3$ into the second equation:
  $$y - 2(3) = -4 \implies y - 6 = -4 \implies y = 2.$$
- Substitute $y=2$ and $z=3$ into the first equation:
  $$x + 2 + 3 = 6 \implies x = 1.$$

So the unique solution is $(x, y, z) = (1, 2, 3)$.

## Quick verification

Substitute $(x, y, z) = (1, 2, 3)$ into all three original equations:

- **Equation 1:** $x + y + z = 1 + 2 + 3 = 6$. ✓
- **Equation 2:** $2x - y + z = 2(1) - 2 + 3 = 2 - 2 + 3 = 3$. ✓
- **Equation 3:** $x + 2y - z = 1 + 2(2) - 3 = 1 + 4 - 3 = 2$. ✓

Every equation holds, confirming consistency and the accuracy of our arithmetic.

## A concrete example

Geometrically, each equation in $x, y, z$ describes a flat plane in three-dimensional space $\mathbb{R}^3$:
- Plane 1 ($x+y+z=6$) and Plane 2 ($2x-y+z=3$) are non-parallel, so they intersect along a line.
- Plane 3 ($x+2y-z=2$) is not parallel to that line of intersection; it slices across the line at a single point, namely $(1,2,3)$.

In the row echelon matrix, this geometric fact shows up as **three non-zero pivots** ($1, 1, -7$) in all three variable columns—leaving zero free variables and no contradiction.

## How I would explain this in class

> We write the system as an augmented matrix and use the top-left $1$ to clear out the $x$-column below it. Next, we swap rows 2 and 3 to put a clean $1$ in the middle pivot spot, avoiding fractions, and clear out the $y$-entry below it. That leaves $-7z = -21$ at the bottom, giving $z=3$ immediately. Climbing back up the staircase gives $y=2$ and $x=1$, and plugging $(1,2,3)$ into the original three equations confirms that all three balance.

## Related workbook topics

- [Exercise 1: From a System to a Matrix](problem_01_solution.md)
- [Exercise 5: Row Echelon Form and Number of Solutions](problem_05_solution.md)
