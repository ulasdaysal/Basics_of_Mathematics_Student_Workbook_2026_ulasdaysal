# Exercise 11. A Parameter in a System of Three Equations

## The question

Analyze the number of solutions depending on $t$:

$$\begin{cases}x+y+z=1,\\x+ty+z=2,\\x+y+tz=3.\end{cases}$$

Use elimination and separately analyze the parameter values for which a standard calculation step ceases to be valid.

## Before calculating: what idea do we need?

When we apply Gaussian elimination to a matrix containing a parameter $t$, the **row addition steps** ($R_i \leftarrow R_i + cR_j$) are valid for **every** real value of $t$. However, when we reach row echelon form and want to divide by a pivot entry containing $t$, that division **ceases to be valid if the pivot equals zero**!

Therefore, the cleanest strategy is:
1. Use only row subtractions (which never divide by expressions in $t$) to bring the matrix into upper triangular form.
2. Inspect the diagonal pivots: any value of $t$ that makes a pivot zero must be analyzed separately.

## 1. Elimination to upper triangular form

Write the augmented matrix of the system:

$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\
1 & t & 1 & 2 \\
1 & 1 & t & 3
\end{array}\right].$$

Subtract the first row from the second row ($R_2 \leftarrow R_2 - R_1$) and from the third row ($R_3 \leftarrow R_3 - R_1$) to eliminate $x$ from rows 2 and 3. Note that this step is valid for **all** $t \in \mathbb{R}$:

$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\
1 - 1 & t - 1 & 1 - 1 & 2 - 1 \\
1 - 1 & 1 - 1 & t - 1 & 3 - 1
\end{array}\right] = \left[\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\
0 & t - 1 & 0 & 1 \\
0 & 0 & t - 1 & 2
\end{array}\right].$$

Remarkably, the matrix is **already in upper triangular (row echelon) form**! The three diagonal entries are $1$, $t-1$, and $t-1$, corresponding to the decoupled equations:

$$\begin{cases}
x + y + z = 1,\\
(t - 1)y = 1,\\
(t - 1)z = 2.
\end{cases}$$

## 2. Identifying when the standard step ceases to be valid

To solve for $y$ and $z$ from the second and third equations, the standard back-substitution step divides by $t - 1$:

$$y = \frac{1}{t-1}, \qquad z = \frac{2}{t-1}.$$

Dividing by $t - 1$ **ceases to be valid when $t - 1 = 0$, that is, when $t = 1$**. Thus, we split our analysis into two cases: $t \neq 1$ and $t = 1$.

## 3. Case-by-case classification of the number of solutions

### Case 1: $t \neq 1$
When $t \neq 1$, the factor $t - 1$ is non-zero, so all three columns have non-zero pivots ($1$, $t-1$, and $t-1$). We can legally divide by $t-1$:
- From row 3: $z = \dfrac{2}{t-1}$.
- From row 2: $y = \dfrac{1}{t-1}$.
- From row 1: $x = 1 - y - z = 1 - \dfrac{1}{t-1} - \dfrac{2}{t-1} = 1 - \dfrac{3}{t-1} = \dfrac{t - 4}{t - 1}$.

Thus, for every **$t \neq 1$**, the system has **exactly one solution**:

$$(x, y, z) = \left(\frac{t-4}{t-1},\; \frac{1}{t-1},\; \frac{2}{t-1}\right).$$

### Case 2: $t = 1$
Substitute $t = 1$ directly into the reduced augmented matrix:

$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\
0 & 0 & 0 & 1 \\
0 & 0 & 0 & 2
\end{array}\right].$$

Both the second row ($0 = 1$) and the third row ($0 = 2$) are contradictions! (In terms of the original system, when $t = 1$, the three equations say $x+y+z=1$, $x+y+z=2$, and $x+y+z=3$ simultaneously.)
Thus, for **$t = 1$**, the system is inconsistent and has **no solution**.

*(Note: There is **no value of $t$** for which this system has infinitely many solutions.)*

## Quick verification

Let us verify the general unique solution for $t \neq 1$ by substituting $x = \frac{t-4}{t-1}$, $y = \frac{1}{t-1}$, $z = \frac{2}{t-1}$ into the three original equations:
- **Equation 1:** $x + y + z = \frac{(t-4) + 1 + 2}{t-1} = \frac{t-1}{t-1} = 1$. ✓
- **Equation 2:** $x + ty + z = \frac{(t-4) + t(1) + 2}{t-1} = \frac{2t-2}{t-1} = 2$. ✓
- **Equation 3:** $x + y + tz = \frac{(t-4) + 1 + 2t}{t-1} = \frac{3t-3}{t-1} = 3$. ✓

## A concrete example

Let us pick a concrete value with $t \neq 1$, say **$t = 2$**:
- Our formula gives $(x, y, z) = \left(\frac{2-4}{2-1}, \frac{1}{2-1}, \frac{2}{2-1}\right) = (-2, 1, 2)$.
- Checking in the system for $t = 2$:
  - $-2 + 1 + 2 = 1$ ✓
  - $-2 + 2(1) + 2 = 2$ ✓
  - $-2 + 1 + 2(2) = 3$ ✓

On the other hand, if $t = 1$, the three planes $x+y+z=1$, $x+y+z=2$, and $x+y+z=3$ are three parallel planes at different heights, which never intersect.

## How I would explain this in class

> Subtracting the first equation from the second and third immediately isolates the parameter: we get $(t-1)y = 1$ and $(t-1)z = 2$. Notice we didn't divide by anything yet, so this is valid for every $t$. Now, to solve for $y$ and $z$, we want to divide by $t-1$, which is only forbidden when $t = 1$. So if $t \neq 1$, we can divide and get a single unique solution. If $t = 1$, those equations become $0 = 1$ and $0 = 2$, which is a contradiction, giving no solution.

## Related workbook topics

- [Exercise 6: A System with a Parameter — Which Cases Actually Occur?](problem_06_solution.md)
- [Exercise 15: Classifying Three Systems](problem_15_solution.md)
