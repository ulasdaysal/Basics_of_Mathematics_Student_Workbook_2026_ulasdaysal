# Exercise 13. Does Every Equation Add New Information?

## The question

Consider the system

$$x_1+x_2=10,\qquad x_2+x_3=8,\qquad x_1-x_3=2.$$

Solve it and check whether all three equations are independently necessary to describe the solution set. If one follows from the others, show this by calculation.

## Before calculating: what idea do we need?

Having three equations in three unknowns does not automatically mean we have three independent pieces of information. An equation is **redundant** if it is a linear combination of the other equations in the system—meaning it is automatically satisfied whenever the other equations hold.

During Gaussian elimination, a redundant equation reveals itself by collapsing into the identity $0 = 0$ (an all-zero row).

## 1. Showing directly that one equation follows from the others

Label the three equations:
- $(E_1): \quad x_1 + x_2 = 10$
- $(E_2): \quad x_2 + x_3 = 8$
- $(E_3): \quad x_1 - x_3 = 2$

Subtract the second equation $(E_2)$ from the first equation $(E_1)$:

$$(E_1) - (E_2): \quad (x_1 + x_2) - (x_2 + x_3) = 10 - 8 \implies x_1 - x_3 = 2.$$

This is **precisely the third equation $(E_3)$**! Equivalently, $(E_1) = (E_2) + (E_3)$. Therefore, the three equations are **not independently necessary**: any one of the three equations is a direct consequence of the other two and adds no new restriction on $(x_1, x_2, x_3)$.

## 2. Solving the system via Gaussian elimination

Let us also see how this redundancy appears in the augmented matrix:

$$\left[\begin{array}{ccc|c}
1 & 1 & 0 & 10 \\
0 & 1 & 1 & 8 \\
1 & 0 & -1 & 2
\end{array}\right].$$

**Step 1:** Eliminate $x_1$ from row 3 by performing $R_3 \leftarrow R_3 - R_1$:

$$\left[\begin{array}{ccc|c}
1 & 1 & 0 & 10 \\
0 & 1 & 1 & 8 \\
0 & -1 & -1 & -8
\end{array}\right].$$

**Step 2:** Eliminate $x_2$ from row 3 by performing $R_3 \leftarrow R_3 + R_2$:

$$\left[\begin{array}{ccc|c}
1 & 1 & 0 & 10 \\
0 & 1 & 1 & 8 \\
0 & 0 & 0 & 0
\end{array}\right].$$

Row 3 vanishes completely ($R_3 - R_1 + R_2 = 0$), confirming that the third equation is redundant.

## 3. Writing the parametric solution set

In the row echelon matrix, column 1 ($x_1$) and column 2 ($x_2$) have pivots, while **column 3 ($x_3$) has no pivot**. Thus, $x_3$ is a free variable.

Set $x_3 = t \in \mathbb{R}$ and solve the two independent equations $x_1 + x_2 = 10$ and $x_2 + x_3 = 8$:
- From the second row:
  $$x_2 = 8 - x_3 = 8 - t.$$
- Substitute $x_2 = 8 - t$ into the first row:
  $$x_1 = 10 - x_2 = 10 - (8 - t) = 2 + t.$$

Thus, the complete solution set is:

$$\begin{cases}
x_1 = 2 + t,\\
x_2 = 8 - t,\\
x_3 = t,
\end{cases} \quad t \in \mathbb{R}.$$

Because the third equation follows from the first two, the first two equations alone ($x_1 + x_2 = 10$ and $x_2 + x_3 = 8$) describe this exact same solution set.

## Quick verification

Substitute $(x_1, x_2, x_3) = (2+t, 8-t, t)$ into all three original equations:
- **Equation 1:** $x_1 + x_2 = (2 + t) + (8 - t) = 10$. ✓
- **Equation 2:** $x_2 + x_3 = (8 - t) + t = 8$. ✓
- **Equation 3:** $x_1 - x_3 = (2 + t) - t = 2$. ✓

Notice that $(2+t, 8-t, t)$ was derived using **only** the first two equations, yet it automatically satisfies the third equation for every $t \in \mathbb{R}$.

## A concrete example

Imagine three people—Alice ($x_1$), Bob ($x_2$), and Clara ($x_3$)—comparing how much money they have:
1. Alice and Bob together have $\$10$ ($x_1 + x_2 = 10$).
2. Bob and Clara together have $\$8$ ($x_2 + x_3 = 8$).
3. Alice has $\$2$ more than Clara ($x_1 - x_3 = 2$).

Statement 3 does not help you figure out how much money Clara has! Since Bob is the common partner in Statements 1 and 2, the $\$2$ difference between $(x_1 + x_2 = 10)$ and $(x_2 + x_3 = 8)$ *already* forces Alice to have $\$2$ more than Clara, whether Clara has $\$0$ ($t=0$, giving Alice $\$2$, Bob $\$8$, Clara $\$0$) or Clara has $\$3$ ($t=3$, giving Alice $\$5$, Bob $\$5$, Clara $\$3$).

## How I would explain this in class

> If you know $x_1 + x_2 = 10$ and $x_2 + x_3 = 8$, and you subtract the second equation from the first, $x_2$ cancels out and you immediately get $x_1 - x_3 = 2$. That means the third equation is already baked into the first two—it adds zero new information! In Gaussian elimination, that third row turns into $[0\;\;0\;\;0\mid 0]$, leaving $x_3 = t$ free and giving the infinite family of solutions $(2+t, 8-t, t)$.

## Related workbook topics

- [Exercise 4: Infinitely Many Solutions](problem_04_solution.md)
- [Exercise 14: A Small Change in the Right-Hand Side](problem_14_solution.md)
