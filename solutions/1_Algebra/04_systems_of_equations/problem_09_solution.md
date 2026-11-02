# Exercise 9. A System from a Sum Condition

## The question

Find numbers $x,y$ satisfying

$$x+y=10,\qquad 2x+5y=32.$$

Solve the system and explain geometrically why the solution is unique.

## Before calculating: what idea do we need?

Each linear equation in two variables $x$ and $y$ represents a **straight line** in the Cartesian plane $\mathbb{R}^2$: every point $(x,y)$ on that line satisfies the equation, and every point off the line does not.

Therefore, solving a system of two linear equations in $x$ and $y$ means finding all points $(x,y)$ that lie on **both lines simultaneously**—that is, finding the **intersection** of the two lines. Two lines in a plane intersect in **exactly one point** if and only if they are **not parallel** (they have different slopes).

## 1. Solving the system by elimination

Write the system as an augmented matrix:

$$\left[\begin{array}{cc|c}
1 & 1 & 10 \\
2 & 5 & 32
\end{array}\right].$$

Subtract twice the first row from the second row ($R_2 \leftarrow R_2 - 2R_1$) to eliminate $x$:

$$\left[\begin{array}{cc|c}
1 & 1 & 10 \\
2 - 2(1) & 5 - 2(1) & 32 - 2(10)
\end{array}\right] = \left[\begin{array}{cc|c}
1 & 1 & 10 \\
0 & 3 & 12
\end{array}\right].$$

Now solve from bottom to top:
- From the second row:
  $$3y = 12 \implies y = 4.$$
- Substitute $y = 4$ into the first equation:
  $$x + 4 = 10 \implies x = 6.$$

Thus, the solution is $(x, y) = (6, 4)$.

## 2. Geometric explanation of uniqueness

Let us write each equation in slope-intercept form $y = mx + b$:
- **Line 1:** $x + y = 10 \implies y = -x + 10$, which has slope $m_1 = -1$.
- **Line 2:** $2x + 5y = 32 \implies y = -\frac{2}{5}x + \frac{32}{5}$, which has slope $m_2 = -\frac{2}{5}$.

Because the slopes are different ($m_1 = -1 \neq -\frac{2}{5} = m_2$), the two lines are **not parallel**. In Euclidean plane geometry, two non-parallel straight lines cross each other at **one and only one point**—here, the point $(6,4)$. Once two straight lines cross, they move steadily apart and can never meet a second time.

## Quick verification

Substitute $(x, y) = (6, 4)$ into both original conditions:
- **First condition (the sum):** $x + y = 6 + 4 = 10$. ✓
- **Second condition (the weighted sum):** $2x + 5y = 2(6) + 5(4) = 12 + 20 = 32$. ✓

Both conditions are satisfied.

## A concrete example

We can also interpret this problem as a classic mixture/coin problem:
Suppose you have **$10$ bills in total** ($x+y=10$), consisting of $\$2$ bills ($x$) and $\$5$ bills ($y$), and their **total value is $\$32$** ($2x+5y=32$).
- If all $10$ bills were $\$2$ bills, you would have $10 \times \$2 = \$20$ (which is $\$12$ short of $\$32$).
- Every time you swap one $\$2$ bill for one $\$5$ bill, the total count stays at $10$, and the total value increases by $\$5 - \$2 = \$3$.
- To gain the missing $\$12$, you must make exactly $\$12 / \$3 = 4$ swaps, giving $y = 4$ five-dollar bills and $x = 10 - 4 = 6$ two-dollar bills. Notice how the calculation $3y = 32 - 20 = 12$ in our elimination step is the exact algebraic version of this swap reasoning!

## How I would explain this in class

> Subtracting twice the first equation ($2x+2y=20$) from the second ($2x+5y=32$) immediately cancels $x$ and leaves $3y = 12$, so $y = 4$ and then $x = 10 - 4 = 6$. Geometrically, the first equation is a line with slope $-1$ and the second is a line with slope $-2/5$. Because their slopes are different, the lines aren't parallel, so they must cross at a single unique point $(6,4)$.

## Related workbook topics

- [Exercise 3: Inconsistent System](problem_03_solution.md)
- [Exercise 15: Classifying Three Systems](problem_15_solution.md)
