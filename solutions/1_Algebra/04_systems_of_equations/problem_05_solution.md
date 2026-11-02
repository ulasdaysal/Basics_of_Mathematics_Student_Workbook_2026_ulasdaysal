# Exercise 5. Row Echelon Form and Number of Solutions

## The question

For the augmented matrix

$$\left[\begin{array}{ccc|c}1&2&-1&3\\0&1&2&1\\0&0&0&0\end{array}\right]$$

determine the number of solutions and write them in parametric form. Explain how you know how many variables may be chosen freely.

## Before calculating: what idea do we need?

When an augmented matrix is already in **row echelon form (REF)**, all the heavy lifting of Gaussian elimination is done. We can immediately read off the structure of the solution set in two steps:
1. **Consistency check:** Look for any contradiction row $[0\;\;0\;\;0\mid c]$ with $c \neq 0$. If none exists, the system is **consistent**.
2. **Counting free variables:** Each non-zero row has a **leading entry (pivot)**—its first non-zero number from the left. Every variable column that contains a pivot is determined by back-substitution; every variable column **without a pivot** can be chosen freely.

$$\text{Number of free variables} = (\text{total number of unknowns}) - (\text{number of pivots}).$$

## 1. Determining consistency and counting free variables

Let the three unknowns corresponding to the three columns on the left be $x_1, x_2, x_3$ (or $x, y, z$).

1. **Row 3** is $[0\;\;0\;\;0\mid 0]$, which reads $0 = 0$. There is no contradictory row $[0\;\;0\;\;0\mid c]$ with $c \neq 0$, so the system is **consistent**.
2. **Pivots:**
   - Row 1 has its leading non-zero entry $1$ in **column 1** ($x$).
   - Row 2 has its leading non-zero entry $1$ in **column 2** ($y$).
   - Row 3 has no pivot.
3. **Free variables:** There are $3$ unknowns in total and $2$ pivots. Therefore,
   $$3 - 2 = 1 \text{ variable may be chosen freely.}$$
   Specifically, **column 3 ($z$)** has no pivot, so $z$ is the single free variable. Because $z$ can be any real number, the system has **infinitely many solutions**.

## 2. Back-substitution to parametric form

Write the two non-zero rows as equations in $x, y, z$:

$$\begin{cases}
x + 2y - z = 3,\\
y + 2z = 1.
\end{cases}$$

Assign a real parameter $t \in \mathbb{R}$ to the free variable:

$$z = t.$$

Now solve for the pivot variables from bottom to top:
- From the second equation:
  $$y = 1 - 2z = 1 - 2t.$$
- Substitute $y = 1 - 2t$ and $z = t$ into the first equation:
  $$x = 3 - 2y + z = 3 - 2(1 - 2t) + t = 3 - 2 + 4t + t = 1 + 5t.$$

## 3. Writing the complete solution set

In parametric form, the solutions are:

$$\begin{cases}
x = 1 + 5t,\\
y = 1 - 2t,\\
z = t,
\end{cases} \quad t \in \mathbb{R},$$

or as a vector equation of a line in $\mathbb{R}^3$:

$$\begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix} + t\begin{pmatrix} 5 \\ -2 \\ 1 \end{pmatrix}, \quad t \in \mathbb{R}.$$

## Quick verification

Substitute $(x, y, z) = (1+5t, 1-2t, t)$ back into the rows of the augmented matrix:
- **Row 1:** $1(1+5t) + 2(1-2t) - 1(t) = 1 + 5t + 2 - 4t - t = 3$. ✓
- **Row 2:** $0(1+5t) + 1(1-2t) + 2(t) = 1 - 2t + 2t = 1$. ✓
- **Row 3:** $0(1+5t) + 0(1-2t) + 0(t) = 0$. ✓

All three equations hold identically for every $t \in \mathbb{R}$.

## A concrete example

By choosing different values for the free variable $z = t$, we generate specific points on the solution line:
- For $t = 0$: $(x, y, z) = (1, 1, 0)$. Check: $1 + 2(1) - 0 = 3$ and $1 + 2(0) = 1$. ✓
- For $t = 1$: $(x, y, z) = (6, -1, 1)$. Check: $6 + 2(-1) - 1 = 3$ and $-1 + 2(1) = 1$. ✓
- For $t = -1$: $(x, y, z) = (-4, 3, -1)$. Check: $-4 + 2(3) - (-1) = 3$ and $3 + 2(-1) = 1$. ✓

Notice how each non-zero row only locks down **one** variable (its pivot variable) once the variables to its right have been chosen. Because the third column has no step of the staircase landing on it, $z$ is never locked down.

## How I would explain this in class

> To read a row echelon matrix, first check the bottom for any $0 = \text{non-zero}$ contradiction—here the bottom row is $0=0$, so we're safe. Next, circle the first non-zero number in each row: those are the pivots in columns 1 and 2. Since there are 3 variables and only 2 pivots, $3 - 2 = 1$ variable (column 3, $z$) has no pivot to pin it down. We set $z = t$, solve row 2 to get $y = 1 - 2t$, and plug both into row 1 to get $x = 1 + 5t$, giving infinitely many solutions.

## Related workbook topics

- [Exercise 4: Infinitely Many Solutions](problem_04_solution.md)
- [Exercise 13: Does Every Equation Add New Information?](problem_13_solution.md)
