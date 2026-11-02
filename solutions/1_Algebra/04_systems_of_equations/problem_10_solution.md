# Exercise 10. A Polynomial Through Three Points

## The question

Find a polynomial $p(x)=ax^2+bx+c$ whose graph passes through $(0,1)$, $(1,3)$, and $(2,9)$. Reduce the problem to a system of equations and check the result by substituting all three points.

## Before calculating: what idea do we need?

At first glance, $p(x) = ax^2 + bx + c$ looks non-linear because of the $x^2$ term. However, here **$x$ is not the unknown**—we are *given* the values of $x$ at three points ($x = 0, 1, 2$), and **the unknowns are the coefficients $a, b, c$**!

When we plug a known point $(x_0, y_0)$ into $p(x_0) = y_0$, the numbers $x_0^2$ and $x_0$ become plain numerical coefficients in front of $a, b, c$. Thus, three points give a system of three **linear** equations in the three unknowns $(a, b, c)$.

## 1. Reducing the problem to a linear system in $a, b, c$

Saying that the graph of $p(x) = ax^2 + bx + c$ passes through $(x_0, y_0)$ means $p(x_0) = y_0$. Substituting each of the three given points produces one linear equation in $a, b, c$:

1. **Point $(0,1)$:** $p(0) = 1 \implies a(0)^2 + b(0) + c = 1 \implies c = 1$.
2. **Point $(1,3)$:** $p(1) = 3 \implies a(1)^2 + b(1) + c = 3 \implies a + b + c = 3$.
3. **Point $(2,9)$:** $p(2) = 9 \implies a(2)^2 + b(2) + c = 9 \implies 4a + 2b + c = 9$.

Putting these together gives the $3\times 3$ linear system:

$$\begin{cases}
c = 1,\\
a + b + c = 3,\\
4a + 2b + c = 9.
\end{cases}$$

## 2. Solving the system for $a, b, c$

Since the first equation already gives $c = 1$ directly (thanks to $x=0$), we substitute $c = 1$ into the remaining two equations:

$$\begin{cases}
a + b + 1 = 3,\\
4a + 2b + 1 = 9
\end{cases} \implies \begin{cases}
a + b = 2,\\
4a + 2b = 8.
\end{cases}$$

Divide the second equation by $2$ (or subtract twice the first equation from the second, $R_2 \leftarrow R_2 - 2R_1$):

$$(4a + 2b) - 2(a + b) = 8 - 2(2) \implies 2a = 4 \implies a = 2.$$

Now substitute $a = 2$ into $a + b = 2$:

$$2 + b = 2 \implies b = 0.$$

## 3. Writing the polynomial

Substituting the solved coefficients $a = 2$, $b = 0$, and $c = 1$ back into $p(x) = ax^2 + bx + c$, we obtain the unique quadratic polynomial:

$$p(x) = 2x^2 + 1.$$

## Quick verification

Let us evaluate $p(x) = 2x^2 + 1$ at all three given $x$-coordinates to verify that the graph passes through each point:

- **At $x = 0$:** $p(0) = 2(0)^2 + 1 = 0 + 1 = 1 \implies (0,1)$. ✓
- **At $x = 1$:** $p(1) = 2(1)^2 + 1 = 2 + 1 = 3 \implies (1,3)$. ✓
- **At $x = 2$:** $p(2) = 2(2)^2 + 1 = 2(4) + 1 = 9 \implies (2,9)$. ✓

All three points lie on the parabola $y = 2x^2 + 1$.

## A concrete example

In matrix form, our system for the unknown coefficient vector $(a, b, c)^T$ is

$$\begin{pmatrix}
0^2 & 0 & 1 \\
1^2 & 1 & 1 \\
2^2 & 2 & 1
\end{pmatrix}\begin{pmatrix} a \\ b \\ c \end{pmatrix} = \begin{pmatrix} 1 \\ 3 \\ 9 \end{pmatrix}
\iff
\begin{pmatrix}
0 & 0 & 1 \\
1 & 1 & 1 \\
4 & 2 & 1
\end{pmatrix}\begin{pmatrix} a \\ b \\ c \end{pmatrix} = \begin{pmatrix} 1 \\ 3 \\ 9 \end{pmatrix}.$$

This coefficient matrix is called a **Vandermonde matrix**. As long as the three $x$-coordinates $x_1, x_2, x_3$ are distinct, this matrix is always invertible, guaranteeing that **any** three points with distinct $x$-coordinates determine a unique polynomial of degree at most $2$. For our polynomial $p(x) = 2x^2 + 1$, we can now predict the height at any new point, such as $x = 3$, where $p(3) = 2(3)^2 + 1 = 19$.

## How I would explain this in class

> Even though the curve $p(x) = ax^2 + bx + c$ has an $x^2$ in it, the unknowns we are solving for are the coefficients $a, b,$ and $c$, which only appear to the first power. Plugging in $x=0, 1, 2$ turns each point into a simple linear equation in $a, b, c$. The point $(0,1)$ immediately gives $c=1$, which simplifies the other two equations to $a+b=2$ and $4a+2b=8$. Elimination gives $a=2$ and $b=0$, so the parabola is $p(x) = 2x^2 + 1$.

## Related workbook topics

- [Exercise 1: From a System to a Matrix](problem_01_solution.md)
- [Exercise 2: Gaussian Elimination — One Solution](problem_02_solution.md)
