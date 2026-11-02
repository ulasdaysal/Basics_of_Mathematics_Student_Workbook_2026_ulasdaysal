# Exercise 15. Classifying Three Systems

## The question

For each of the following systems, perform only as much elimination as necessary to recognize its type:

1. $\begin{cases}x+y=2,\\x-y=0,\end{cases}$
2. $\begin{cases}x+y=2,\\2x+2y=4,\end{cases}$
3. $\begin{cases}x+y=2,\\2x+2y=5.\end{cases}$

For each, justify the classification: one solution, infinitely many solutions, or no solution.

## Before calculating: what idea do we need?

For a $2\times 2$ linear system, **one single elimination step** (eliminating $x$ from the second equation) brings the augmented matrix into row echelon form:

$$\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & b & c
\end{array}\right].$$

We do not even need to back-substitute to classify the system! Everything is decided by the second row $[0\;\;b\mid c]$:
1. **$b \neq 0$:** The second column also gets a pivot $\implies$ **2 pivots for 2 variables (no free variables)** $\implies$ **exactly one solution**.
2. **$b = 0$ and $c = 0$:** The second row is $0 = 0$ $\implies$ **1 pivot for 2 variables (1 free variable)** $\implies$ **infinitely many solutions**.
3. **$b = 0$ and $c \neq 0$:** The second row is the contradiction $0 = c$ $\implies$ **inconsistent** $\implies$ **no solution**.

## 1. System 1: $\begin{cases}x+y=2,\\x-y=0\end{cases}$

Write the augmented matrix and subtract row 1 from row 2 ($R_2 \leftarrow R_2 - R_1$):

$$\left[\begin{array}{cc|c}
1 & 1 & 2 \\
1 & -1 & 0
\end{array}\right] \xrightarrow{R_2 \leftarrow R_2 - R_1}
\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & -2 & -2
\end{array}\right].$$

- **Classification:** **Exactly one solution.**
- **Justification:** After eliminating $x$ from the second row, the coefficient of $y$ is $-2 \neq 0$. Thus, both columns have non-zero pivots ($1$ and $-2$), there is no contradiction row, and there are $2 - 2 = 0$ free variables.

## 2. System 2: $\begin{cases}x+y=2,\\2x+2y=4\end{cases}$

Write the augmented matrix and subtract twice row 1 from row 2 ($R_2 \leftarrow R_2 - 2R_1$):

$$\left[\begin{array}{cc|c}
1 & 1 & 2 \\
2 & 2 & 4
\end{array}\right] \xrightarrow{R_2 \leftarrow R_2 - 2R_1}
\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & 0 & 0
\end{array}\right].$$

- **Classification:** **Infinitely many solutions.**
- **Justification:** Elimination produces the zero row $[0\;\;0\mid 0]$ ($0 = 0$). There is no contradiction, so the system is consistent, and only column 1 ($x$) has a pivot while column 2 ($y$) has no pivot. Since $y$ is a free variable that can take any real value, there are infinitely many solutions.

## 3. System 3: $\begin{cases}x+y=2,\\2x+2y=5\end{cases}$

Write the augmented matrix and subtract twice row 1 from row 2 ($R_2 \leftarrow R_2 - 2R_1$):

$$\left[\begin{array}{cc|c}
1 & 1 & 2 \\
2 & 2 & 5
\end{array}\right] \xrightarrow{R_2 \leftarrow R_2 - 2R_1}
\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & 0 & 1
\end{array}\right].$$

- **Classification:** **No solution (inconsistent).**
- **Justification:** Elimination produces the row $[0\;\;0\mid 1]$, which represents the contradictory equation $0x + 0y = 1$ ($0 = 1$). Because no pair $(x,y)$ can satisfy $0 = 1$, the system has no solution.

## Quick verification

Let us verify the three classifications directly from the equations:
- **System 1:** From $-2y = -2$ we get $y = 1$ and $x = 1$, which is the unique point $(1,1)$ satisfying $1+1=2$ and $1-1=0$. ✓
- **System 2:** Dividing the second equation $2x+2y=4$ by $2$ gives $x+y=2$, which is identical to the first equation; every point $(2-t, t)$ for $t \in \mathbb{R}$ is a solution. ✓
- **System 3:** Dividing the second equation $2x+2y=5$ by $2$ gives $x+y=2.5$, which directly contradicts the first equation $x+y=2$. ✓

## A concrete example

Geometrically, all three systems start with the exact same first line $L_1: x + y = 2$ (which has slope $-1$) and pair it with three different second lines $L_2$:

| System | Second line $L_2$ | Geometric relationship to $L_1$ | Number of intersection points |
| :--- | :--- | :--- | :--- |
| **1** | $x - y = 0$ (slope $+1$) | **Intersecting** (perpendicular lines) | **1** (at $(1,1)$) |
| **2** | $2x + 2y = 4$ (slope $-1$, same intercept) | **Coincident** (the exact same line) | **Infinitely many** (every point on $L_1$) |
| **3** | $2x + 2y = 5$ (slope $-1$, different intercept) | **Parallel and distinct** | **0** (never meet) |

## How I would explain this in class

> One single row operation tells the whole story for each $2\times 2$ system. After clearing $x$ from the second row, look at what is left in row 2: in System 1 we get $[0\;\;-2\mid -2]$, which has a non-zero pivot for $y$, so there is **one solution**. In System 2 we get $[0\;\;0\mid 0]$ ($0=0$), leaving $y$ as a free variable, so there are **infinitely many solutions**. In System 3 we get $[0\;\;0\mid 1]$ ($0=1$), an outright contradiction, so there is **no solution**.

## Related workbook topics

- [Exercise 3: Inconsistent System](problem_03_solution.md)
- [Exercise 5: Row Echelon Form and Number of Solutions](problem_05_solution.md)
