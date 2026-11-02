# Exercise 14. A Small Change in the Right-Hand Side

## The question

Compare the systems

$$\begin{cases}x+y=2,\\2x-y=1,\\3x=3\end{cases} \quad \text{and} \quad \begin{cases}x+y=2,\\2x-y=1,\\3x=3.1.\end{cases}$$

Check the consistency of each system and explain why a small change in one number can change the type of the system.

## Before calculating: what idea do we need?

Here we have **three equations in only two unknowns** ($x$ and $y$)—an **overdetermined** system.
- Usually, two independent equations are already enough to lock $(x,y)$ down to a single point in the plane.
- Once $(x,y)$ is locked down by the first two equations, the third equation is a **compatibility test**: either the locked-down point happens to satisfy the third equation (making the system **consistent** with a unique solution), or it misses by even a tiny amount (making the system **inconsistent** with no solution).

## 1. Checking the consistency of the first system

Look at the first two equations of both systems:

$$\begin{cases}
x + y = 2,\\
2x - y = 1.
\end{cases}$$

Adding the first equation and the second equation eliminates $y$:

$$(x + y) + (2x - y) = 2 + 1 \implies 3x = 3.$$

In the **first system**, the third equation is literally $3x = 3$, which matches the sum of the first two equations! Let us also write the full elimination on the augmented matrix of the first system:

$$\left[\begin{array}{cc|c}
1 & 1 & 2 \\
2 & -1 & 1 \\
3 & 0 & 3
\end{array}\right]
\xrightarrow{\substack{R_2 \leftarrow R_2 - 2R_1 \\ R_3 \leftarrow R_3 - 3R_1}}
\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & -3 & -3 \\
0 & -3 & -3
\end{array}\right]
\xrightarrow{R_3 \leftarrow R_3 - R_2}
\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & -3 & -3 \\
0 & 0 & 0
\end{array}\right].$$

Because the bottom row is $[0\;\;0\mid 0]$ ($0 = 0$), the **first system is consistent** and has the unique solution:
- From row 2: $-3y = -3 \implies y = 1$.
- From row 1: $x + 1 = 2 \implies x = 1$.

So $(x, y) = (1, 1)$ satisfies all three equations of the first system.

## 2. Checking the consistency of the second system

Now perform the exact same elimination steps on the **second system**, where $3$ is replaced by $3.1$:

$$\left[\begin{array}{cc|c}
1 & 1 & 2 \\
2 & -1 & 1 \\
3 & 0 & 3.1
\end{array}\right]
\xrightarrow{\substack{R_2 \leftarrow R_2 - 2R_1 \\ R_3 \leftarrow R_3 - 3R_1}}
\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & -3 & -3 \\
0 & -3 & -2.9
\end{array}\right]
\xrightarrow{R_3 \leftarrow R_3 - R_2}
\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & -3 & -3 \\
0 & 0 & 0.1
\end{array}\right].$$

The bottom row is $[0\;\;0\mid 0.1]$, which translates to the contradiction

$$0x + 0y = 0.1 \iff 0 = 0.1.$$

Therefore, the **second system is inconsistent** and has **no solution**.

## 3. Why a small change in one number changes the type of the system

1. **Algebraic reason:** The left-hand side of the third equation is an exact linear combination of the first two left-hand sides:
   $$3x = (x + y) + (2x - y).$$
   Therefore, for *any* solution of the first two equations ($x+y=2$ and $2x-y=1$), the expression $3x$ is **forced** to equal $2 + 1 = 3$. Changing the right-hand side of the third equation from $3$ to $3.1$ (or to $3 + \varepsilon$ for any $\varepsilon \neq 0$, no matter how tiny) creates the impossible demand $3 = 3.1$.
2. **Geometric reason:** Each equation describes a line in the plane $\mathbb{R}^2$. The first two lines $x+y=2$ and $2x-y=1$ cross at the single point $(1,1)$. For the three-line system to have a solution, the third line must pass through that exact intersection point $(1,1)$. In the first system, the vertical line $3x = 3$ ($x = 1$) passes right through $(1,1)$; in the second system, the vertical line $3x = 3.1$ ($x = 1.033\dots$) shifts slightly to the right and misses $(1,1)$, leaving no point common to all three lines.

## Quick verification

Since the first two equations uniquely force $(x,y) = (1,1)$, we can simply plug $(1,1)$ into the third equation of each system:
- **First system:** $3x = 3(1) = 3 = 3$. ✓ (Consistent)
- **Second system:** $3x = 3(1) = 3 \neq 3.1$. ✓ (Inconsistent by $0.1$)

## A concrete example

This sensitivity occurs constantly in real-world scientific measurements:
Suppose $x = 1\text{ kg}$ and $y = 1\text{ kg}$ are the true masses of two weights.
- Measurement 1 weighs $x + y = 2\text{ kg}$.
- Measurement 2 weighs $2x - y = 1\text{ kg}$.
- Measurement 3 weighs three copies of $x$, and due to a tiny sensor rounding error of $0.1\text{ kg}$, records $3x = 3.1\text{ kg}$.

Even though the measurement error is only $0.1\text{ kg}$, the exact algebraic system with $3.1$ becomes strictly inconsistent because two exact measurements already determined $x=1$ with zero degrees of freedom left over.

## How I would explain this in class

> Notice that adding the first two equations $(x+y=2)$ and $(2x-y=1)$ gives $3x = 3$. That means the first two equations already lock the solution at $(x,y)=(1,1)$ and force $3x$ to be $3$. In the first system, the third equation agrees ($3x=3$), so all three lines meet at $(1,1)$. In the second system, changing $3$ to $3.1$ shifts the third line slightly to $x = 3.1/3$, so it misses the intersection point $(1,1)$ of the first two lines and the system has no solution.

## Related workbook topics

- [Exercise 3: Inconsistent System](problem_03_solution.md)
- [Exercise 13: Does Every Equation Add New Information?](problem_13_solution.md)
