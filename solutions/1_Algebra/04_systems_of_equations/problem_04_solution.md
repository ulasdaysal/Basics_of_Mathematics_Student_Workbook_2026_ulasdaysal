# Exercise 4. Infinitely Many Solutions

## The question

Solve

$$\begin{cases}x+y+z=2,\\2x+2y+2z=4,\\x-y+z=0.\end{cases}$$

Give the solution in parametric form, identify a free variable, and for one chosen parameter value check that the resulting point really satisfies the system.

## Before calculating: what idea do we need?

When one equation in a system is a redundant copy (or combination) of the others, elimination produces an **entirely zero row** $[0\;\;0\;\;0\mid 0]$. Unlike $[0\;\;0\;\;0\mid 1]$, the equation $0 = 0$ is always true—it simply says we have fewer independent equations than variables.

When a consistent system has fewer pivots than unknowns:
- The variables in columns **with pivots** are **leading (basic) variables**.
- The variables in columns **without pivots** are **free variables**: we can set them equal to arbitrary real parameters (like $t \in \mathbb{R}$) and express the basic variables in terms of those parameters.

## 1. Gaussian elimination on the augmented matrix

Write the augmented matrix:

$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\
2 & 2 & 2 & 4 \\
1 & -1 & 1 & 0
\end{array}\right].$$

Eliminate $x$ below the first pivot by performing $R_2 \leftarrow R_2 - 2R_1$ and $R_3 \leftarrow R_3 - R_1$:

$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\
0 & 0 & 0 & 0 \\
0 & -2 & 0 & -2
\end{array}\right].$$

Swap row 2 and row 3 ($R_2 \leftrightarrow R_3$) so the zero row is at the bottom, and divide the new row 2 by $-2$ ($R_2 \leftarrow -\frac{1}{2}R_2$):

$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\
0 & 1 & 0 & 1 \\
0 & 0 & 0 & 0
\end{array}\right].$$

## 2. Identifying pivots and the free variable

Looking at the row echelon matrix:
- **Column 1 ($x$)** has a pivot at $(1,1)$.
- **Column 2 ($y$)** has a pivot at $(2,2)$.
- **Column 3 ($z$)** has **no pivot**.

Therefore, $x$ and $y$ are the basic variables, and **$z$ is the free variable**. Since $z$ can take any real value without restriction, the system has **infinitely many solutions**.

## 3. Writing the solution in parametric form

Translate the two non-zero rows back into equations:

$$\begin{cases}
x + y + z = 2,\\
y = 1.
\end{cases}$$

Set the free variable to a parameter $z = t \in \mathbb{R}$. Now back-substitute:
- From the second equation, $y = 1$ (it is fixed regardless of $t$).
- From the first equation, $x = 2 - y - z = 2 - 1 - t = 1 - t$.

Thus, the general solution in parametric form is:

$$\begin{cases}
x = 1 - t,\\
y = 1,\\
z = t,
\end{cases} \quad t \in \mathbb{R},$$

or in vector form:

$$\begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix} + t\begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix}, \quad t \in \mathbb{R}.$$

## Quick verification

Let us check the general parametric formula $(x,y,z) = (1-t, 1, t)$ directly in all three original equations:
- **Equation 1:** $(1-t) + 1 + t = 2$. ✓
- **Equation 2:** $2(1-t) + 2(1) + 2t = 2 - 2t + 2 + 2t = 4$. ✓
- **Equation 3:** $(1-t) - 1 + t = 0$. ✓

The parameter $t$ cancels out in every single equation, proving that every point on this line is a valid solution.

## A concrete example

Let us choose a specific parameter value, say **$t = 3$**. Substituting $t = 3$ into our parametric formula gives the point:

$$(x, y, z) = (1 - 3, 1, 3) = (-2, 1, 3).$$

Now let us check that $(-2, 1, 3)$ satisfies the original system:
- First equation: $(-2) + 1 + 3 = 2$. ✓
- Second equation: $2(-2) + 2(1) + 2(3) = -4 + 2 + 6 = 4$. ✓
- Third equation: $(-2) - 1 + 3 = 0$. ✓

(If we instead chose $t = 0$, we would get the point $(1, 1, 0)$, which also satisfies $1+1+0=2$, $2+2+0=4$, and $1-1+0=0$.)

## How I would explain this in class

> Notice right away that the second equation $2x+2y+2z=4$ is just twice the first equation $x+y+z=2$, so it adds zero new information. During elimination, that duplicate equation turns into a row of all zeros, leaving us with only two real equations for three unknowns. Because the $z$-column has no pivot, $z$ is a free variable: we set $z=t$, find $y=1$ and $x=1-t$, and get an entire line of solutions in $\mathbb{R}^3$.

## Related workbook topics

- [Exercise 5: Row Echelon Form and Number of Solutions](problem_05_solution.md)
- [Exercise 12: Homogeneous System](problem_12_solution.md)
