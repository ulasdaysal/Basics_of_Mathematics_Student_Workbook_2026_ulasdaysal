# Exercise 14. A System of Equations and the Determinant

## The question

Consider $Ax=b$ with

$$A=\begin{pmatrix}1&2\\k&4\end{pmatrix}.$$

For which $k$ does the system have exactly one solution for every $b$? For the remaining value, give a right-hand side $b$ with infinitely many solutions and one with no solution.

## Before calculating: what idea do we need?

For a square system $Ax=b$:

- if $\det A\neq0$, $A$ is invertible and $x=A^{-1}b$ is the **unique** solution for **every** $b$;
- if $\det A=0$, the rows are dependent. Then, depending on $b$, there are either **infinitely many** solutions (the equations agree) or **none** (the equations contradict each other).

## 1. Compute the determinant

$$\det A=1\cdot4-2\cdot k=4-2k.$$

## 2. Unique solution for every $b$

$$4-2k\neq0\iff k\neq2.$$

So for every $k\neq2$ the system has exactly one solution for every $b$, namely

$$x=A^{-1}b=\frac{1}{4-2k}\begin{pmatrix}4&-2\\-k&1\end{pmatrix}b.$$

## 3. The exceptional value $k=2$

$$A=\begin{pmatrix}1&2\\2&4\end{pmatrix},\qquad R_2=2R_1.$$

The system is

$$\begin{cases}x_1+2x_2=b_1\\2x_1+4x_2=b_2\end{cases}$$

The left side of the second equation is exactly twice the left side of the first. So everything depends on whether $b_2=2b_1$.

**Infinitely many solutions:** take $b=\begin{pmatrix}1\\2\end{pmatrix}$ (so $b_2=2b_1$). The second equation is just the first one multiplied by $2$, so only $x_1+2x_2=1$ remains:

$$x=\begin{pmatrix}1-2s\\s\end{pmatrix},\qquad s\in\mathbb{R}.$$

Geometrically: both equations describe the **same line**.

**No solution:** take $b=\begin{pmatrix}1\\0\end{pmatrix}$. Then

$$x_1+2x_2=1\quad\text{and}\quad 2x_1+4x_2=0\ \Rightarrow\ x_1+2x_2=0.$$

The same expression cannot equal both $1$ and $0$. Geometrically: two **parallel lines** that never meet.

## 4. Quick verification

- Infinitely many: $s=0$ gives $(1,0)$: $1+0=1$, $2+0=2$ ✓. $s=1$ gives $(-1,1)$: $-1+2=1$, $-2+4=2$ ✓.
- No solution: $R_2-2R_1$ on the augmented matrix $\left(\begin{array}{cc|c}1&2&1\\2&4&0\end{array}\right)$ gives $(0,0\mid-2)$, i.e. $0=-2$. Contradiction ✓.

## 5. A concrete example of the unique case

For $k=1$, $b=\begin{pmatrix}3\\6\end{pmatrix}$: $\det=2$, and

$$x=\frac12\begin{pmatrix}4&-2\\-1&1\end{pmatrix}\begin{pmatrix}3\\6\end{pmatrix}=\frac12\begin{pmatrix}0\\3\end{pmatrix}=\begin{pmatrix}0\\1.5\end{pmatrix}.$$

Check: $0+2\cdot1.5=3$ ✓, $0+4\cdot1.5=6$ ✓.

## How I would explain this in class

> The determinant is $4-2k$. If $k\neq2$ it's non-zero, so $A$ is invertible and every $b$ gives exactly one solution. If $k=2$ the second row is twice the first. If $b$ also satisfies $b_2=2b_1$, like $(1,2)$, the two equations are the same line and there are infinitely many solutions. If not, like $(1,0)$, they are parallel lines and there is no solution.

## Related workbook topics

- [Exercise 6: Parameter and invertibility](problem_06_solution.md)
- [Exercise 10: Detecting dependence](problem_10_solution.md)
