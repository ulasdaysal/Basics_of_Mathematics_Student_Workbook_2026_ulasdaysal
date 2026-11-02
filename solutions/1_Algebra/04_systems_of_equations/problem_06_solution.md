# Exercise 6. A System with a Parameter — Which Cases Actually Occur?

## The question

Analyze, depending on the parameter $a$, the system

$$\begin{cases}x+y=2,\\ax+ay=4.\end{cases}$$

Among the three possibilities — exactly one solution, infinitely many solutions, no solution — determine which actually occur and for which values of $a$. If one type cannot occur, explain why.

## Before calculating: what idea do we need?

Students often assume that if a system contains a parameter $a$, there must be some value of $a$ that gives a unique solution, some value that gives infinitely many solutions, and some value that gives no solution. **That is not always true!**

Whether a system can have a unique solution depends on whether its coefficient matrix can have two independent rows (or a non-zero determinant). If the left-hand sides of the two equations are already proportional for *every* value of $a$, then elimination will always wipe out both variables in the second row at the same time.

## 1. Elimination on the augmented matrix

Write the augmented matrix of the system:

$$\left[\begin{array}{cc|c}
1 & 1 & 2 \\
a & a & 4
\end{array}\right].$$

Eliminate $x$ from the second row by subtracting $a$ times the first row ($R_2 \leftarrow R_2 - aR_1$):

$$\left[\begin{array}{cc|c}
1 & 1 & 2 \\
a - a(1) & a - a(1) & 4 - 2a
\end{array}\right] = \left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & 0 & 4 - 2a
\end{array}\right].$$

## 2. Analyzing the reduced second row

The second row translates to the equation

$$0x + 0y = 4 - 2a \iff 0 = 4 - 2a.$$

Now we examine when this equation is true and when it is false:

- **Case 1: $4 - 2a = 0 \iff a = 2$.**
  When $a = 2$, the second row becomes $[0\;\;0\mid 0]$, so the system reduces to the single equation $x + y = 2$. Here $y = t \in \mathbb{R}$ is a free variable and $x = 2 - t$.
  Thus, for **$a = 2$**, the system has **infinitely many solutions**.

- **Case 2: $4 - 2a \neq 0 \iff a \neq 2$.**
  When $a \neq 2$, the second row is $[0\;\;0\mid c]$ with $c = 4 - 2a \neq 0$, which is the contradiction $0 = 4 - 2a$.
  Thus, for **$a \neq 2$**, the system has **no solution** (it is inconsistent).

## 3. Why "exactly one solution" can never occur

The case of **exactly one solution never occurs** for any real number $a$.

**Algebraic reason:**
For a $2\times 2$ system to have a unique solution, the coefficient matrix $A = \begin{pmatrix} 1 & 1 \\ a & a \end{pmatrix}$ would need two pivots (or equivalently, $\det(A) \neq 0$). However,

$$\det\begin{pmatrix} 1 & 1 \\ a & a \end{pmatrix} = 1\cdot a - 1\cdot a = 0 \quad \text{for every } a \in \mathbb{R}.$$

Because $x$ and $y$ appear only in the combination $(x+y)$ in both equations ($x+y=2$ and $a(x+y)=4$), no equation in the system can ever distinguish between $x$ and $y$ individually.

**Geometric reason:**
For $a \neq 0$, both equations describe lines with slope $-1$. Changing $a$ shifts the second line parallel to itself, so the two lines are either **parallel and distinct** ($a \neq 2$, no intersection) or **the exact same line** ($a = 2$, infinitely many intersections). Two lines of identical slope can never cross at a single point. (Even for $a = 0$, the second equation $0 = 4$ is immediately inconsistent.)

## Quick verification

Let us plug $x + y = 2$ from the first equation directly into the left-hand side of the second equation:

$$ax + ay = a(x + y) = a(2) = 2a.$$

For the second equation $ax + ay = 4$ to hold, we must have $2a = 4$, which forces $a = 2$.
- If $a \neq 2$, then $2a \neq 4$, so no pair $(x,y)$ satisfying the first equation can ever satisfy the second. ✓
- If $a = 2$, every pair $(x,y)$ satisfying $x + y = 2$ automatically satisfies $2x + 2y = 4$. ✓

## A concrete example

Let us test two specific values of $a$:
1. **Suppose $a = 2$:** The system is $\begin{cases} x+y=2, \\ 2x+2y=4. \end{cases}$ Every point of the form $(2-t, t)$, such as $(2,0)$, $(1,1)$, or $(0,2)$, satisfies both equations.
2. **Suppose $a = 3$:** The system is $\begin{cases} x+y=2, \\ 3x+3y=4. \end{cases}$ Dividing the second equation by $3$ asks for $x+y = \frac{4}{3}$, which directly clashes with $x+y = 2$.

## How I would explain this in class

> Don't assume a parameter automatically gives all three cases! Here the second equation can be factored as $a(x+y) = 4$. Since the first equation already tells us $x+y=2$, the second equation really just says $2a = 4$. If $a \neq 2$, that's a contradiction, so there is no solution. If $a = 2$, the second equation is just twice the first, leaving one equation $x+y=2$ with two unknowns—infinitely many solutions. A unique solution is impossible because both equations only depend on the sum $x+y$.

## Related workbook topics

- [Exercise 3: Inconsistent System](problem_03_solution.md)
- [Exercise 11: A Parameter in a System of Three Equations](problem_11_solution.md)
