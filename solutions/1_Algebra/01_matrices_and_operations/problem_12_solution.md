# Exercise 12. Formula for a Matrix Power

## The question

Let

$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix}.$$

Compute $A^2$, $A^3$, $A^4$, formulate a conjecture for $A^n$, and then prove it: assume the formula holds for $n$, multiply by $A$, and show that it gives the formula for $n+1$.

## Before calculating: what idea do we need?

Two tools:

1. **Pattern recognition:** compute a few powers and look for what changes.
2. **Mathematical induction:** checking more cases never proves a formula for *all* $n$. Induction does:
   - **Base case:** the formula is true for $n=1$.
   - **Induction step:** *if* it is true for some $n$, *then* it is true for $n+1$.

   Together these give a chain $1\Rightarrow2\Rightarrow3\Rightarrow\dots$ that reaches every natural number.

## 1. Compute the first powers

$$A^2=\begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}=\begin{pmatrix}1&2\\0&1\end{pmatrix},$$

$$A^3=A^2A=\begin{pmatrix}1&2\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}=\begin{pmatrix}1&3\\0&1\end{pmatrix},$$

$$A^4=A^3A=\begin{pmatrix}1&3\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}=\begin{pmatrix}1&4\\0&1\end{pmatrix}.$$

## 2. Conjecture

Only the top-right entry changes, and it equals the exponent:

$$\boxed{A^n=\begin{pmatrix}1&n\\0&1\end{pmatrix}}\qquad(n\geq1).$$

## 3. Proof by induction

**Base case** $n=1$: $\begin{pmatrix}1&1\\0&1\end{pmatrix}=A$. ✓

**Induction step.** Assume $A^n=\begin{pmatrix}1&n\\0&1\end{pmatrix}$ for some $n$. Then

$$A^{n+1}=A^nA=\begin{pmatrix}1&n\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}=\begin{pmatrix}1\cdot1+n\cdot0 & 1\cdot1+n\cdot1\\ 0\cdot1+1\cdot0 & 0\cdot1+1\cdot1\end{pmatrix}=\begin{pmatrix}1&n+1\\0&1\end{pmatrix}.$$

This is exactly the formula with $n$ replaced by $n+1$. By induction, the formula holds for all $n\geq1$. $\blacksquare$

## 4. Meaning

$A$ is a **horizontal shear**:

$$A\begin{pmatrix}x\\y\end{pmatrix}=\begin{pmatrix}x+y\\y\end{pmatrix}.$$

Each application pushes a point to the right by its height $y$. Applying it $n$ times pushes it by $ny$, which is exactly what $\begin{pmatrix}1&n\\0&1\end{pmatrix}$ does. So the entries grow **linearly** in $n$ (not exponentially), because each shear just adds the same amount again.

The formula also works for $n=0$ (giving $I$) and $n=-1$: $\begin{pmatrix}1&-1\\0&1\end{pmatrix}$ is indeed $A^{-1}$, since it undoes the shear.

## 5. Quick verification

- The formula reproduces $A^2,A^3,A^4$ computed above. ✓
- Alternative argument: $A=I+N$ with $N=\begin{pmatrix}0&1\\0&0\end{pmatrix}$, $N^2=0$, so $A^n=I+nN$. ✓
- $\det A^n=1=(\det A)^n$. ✓

## 6. A concrete example

$$A^{10}=\begin{pmatrix}1&10\\0&1\end{pmatrix},\qquad A^{10}\begin{pmatrix}0\\1\end{pmatrix}=\begin{pmatrix}10\\1\end{pmatrix}.$$

The point $(0,1)$ is shifted 10 units to the right after 10 shears.

## How I would explain this in class

> I computed $A^2$, $A^3$, $A^4$ and saw that only the corner changes: it is $2,3,4$. So I conjecture $A^n=\begin{pmatrix}1&n\\0&1\end{pmatrix}$. To prove it, I assume it for $n$ and multiply by $A$. The corner becomes $n+1$, which is the formula for $n+1$. Together with the case $n=1$, induction proves it for all $n$. Geometrically, $A$ is a shear, and $n$ shears shift by $n$ times as much.

## Related workbook topics

- [Exercise 7: Identity, zero matrix, and powers](problem_07_solution.md)
- [Exercise 11: When do matrices commute?](problem_11_solution.md)
- [Exercise 13: A recurrence in matrix form](problem_13_solution.md)
