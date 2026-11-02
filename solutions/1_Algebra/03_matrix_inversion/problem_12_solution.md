# Exercise 12. Finding Inverses Without Starting from Scratch

## The question

It is known that

$$A^{-1}=\begin{pmatrix}2&-1\\-3&2\end{pmatrix}.$$

Without finding $A$, compute $(3A)^{-1}$, $(A^T)^{-1}$, and $(A^2)^{-1}$. Justify each result using the appropriate property.

## Before calculating: what idea do we need?

If we already know $A^{-1}$, we never need to reconstruct $A$ first and then invert again. Instead, we use three fundamental **properties of matrix inverses** that express each new inverse directly in terms of $A^{-1}$:

1. **Scalar multiple:** $(cA)^{-1}=\dfrac{1}{c}A^{-1}$ for any non-zero scalar $c\neq0$.
2. **Transpose:** $(A^T)^{-1}=(A^{-1})^T$ (inverting and transposing can be done in either order).
3. **Power / Product:** $(A^2)^{-1}=(AA)^{-1}=A^{-1}A^{-1}=(A^{-1})^2$.

## 1. Compute $(3A)^{-1}$

**Justification:** If we multiply $(3A)$ by $\frac{1}{3}A^{-1}$, the scalars $3$ and $\frac{1}{3}$ cancel to $1$ and $AA^{-1}$ cancels to $I$:

$$(3A)\left(\frac{1}{3}A^{-1}\right)=\left(3\cdot\frac{1}{3}\right)(AA^{-1})=1\cdot I=I.$$

Therefore, $(3A)^{-1}=\frac{1}{3}A^{-1}$:

$$(3A)^{-1}=\frac{1}{3}\begin{pmatrix}2&-1\\-3&2\end{pmatrix}=\begin{pmatrix}\frac{2}{3}&-\frac{1}{3}\\-1&\frac{2}{3}\end{pmatrix}.$$

## 2. Compute $(A^T)^{-1}$

**Justification:** Taking the transpose of $AA^{-1}=I$ and using the reversal rule $(XY)^T=Y^TX^T$ gives

$$(AA^{-1})^T = I^T \quad\Longrightarrow\quad (A^{-1})^T A^T = I.$$

Similarly, $(A^{-1}A)^T=I^T$ gives $A^T(A^{-1})^T=I$. Thus the inverse of $A^T$ is simply the transpose of $A^{-1}$:

$$(A^T)^{-1}=(A^{-1})^T=\begin{pmatrix}2&-1\\-3&2\end{pmatrix}^T=\begin{pmatrix}2&-3\\-1&2\end{pmatrix}.$$

## 3. Compute $(A^2)^{-1}$

**Justification:** Using the inverse-of-a-product rule $(AB)^{-1}=B^{-1}A^{-1}$ with $B=A$, we have

$$(A^2)^{-1}=(AA)^{-1}=A^{-1}A^{-1}=(A^{-1})^2.$$

(Geometrically, if $A^2$ applies $A$ twice, undoing it requires applying $A^{-1}$ twice.) Multiply $A^{-1}$ by itself:

$$(A^2)^{-1}=\begin{pmatrix}2&-1\\-3&2\end{pmatrix}\begin{pmatrix}2&-1\\-3&2\end{pmatrix}=\begin{pmatrix}2\cdot2+(-1)\cdot(-3) & 2\cdot(-1)+(-1)\cdot2\\(-3)\cdot2+2\cdot(-3) & (-3)\cdot(-1)+2\cdot2\end{pmatrix}=\begin{pmatrix}4+3 & -2-2\\-6-6 & 3+4\end{pmatrix}=\begin{pmatrix}7&-4\\-12&7\end{pmatrix}.$$

## Quick verification

To verify independently, note that $A=(A^{-1})^{-1}=\begin{pmatrix}2&1\\3&2\end{pmatrix}$ (since $\det(A^{-1})=4-3=1$).
- $3A=\begin{pmatrix}6&3\\9&6\end{pmatrix}$, and $(3A)(3A)^{-1}=\begin{pmatrix}6&3\\9&6\end{pmatrix}\begin{pmatrix}\frac{2}{3}&-\frac{1}{3}\\-1&\frac{2}{3}\end{pmatrix}=\begin{pmatrix}4-3&-2+2\\6-6&-3+4\end{pmatrix}=I$. ✓
- $A^T=\begin{pmatrix}2&3\\1&2\end{pmatrix}$, and $A^T(A^T)^{-1}=\begin{pmatrix}2&3\\1&2\end{pmatrix}\begin{pmatrix}2&-3\\-1&2\end{pmatrix}=\begin{pmatrix}4-3&-6+6\\2-2&-3+4\end{pmatrix}=I$. ✓
- $A^2=\begin{pmatrix}2&1\\3&2\end{pmatrix}\begin{pmatrix}2&1\\3&2\end{pmatrix}=\begin{pmatrix}7&4\\12&7\end{pmatrix}$, and $A^2(A^2)^{-1}=\begin{pmatrix}7&4\\12&7\end{pmatrix}\begin{pmatrix}7&-4\\-12&7\end{pmatrix}=\begin{pmatrix}49-48&-28+28\\84-84&-48+49\end{pmatrix}=I$. ✓

## A concrete example

Notice a common pitfall in part 1: students sometimes write $(3A)^{-1}=3A^{-1}$ instead of $\frac{1}{3}A^{-1}$.
Think about what $3A$ does to a vector: it applies $A$ and stretches the result by a factor of $3$. To undo a stretch by $3$, you must shrink by $\frac{1}{3}$, never stretch by $3$ again!

## How I would explain this in class

> Instead of inverting $A^{-1}$ to find $A$ and starting over three times, we use algebra rules for inverses. First, scaling a matrix by $3$ scales its inverse by $\frac{1}{3}$, so $(3A)^{-1}=\frac{1}{3}A^{-1}$. Second, transposing and inverting commute, so $(A^T)^{-1}=(A^{-1})^T$, which just swaps $-1$ and $-3$. Third, undoing $A$ applied twice means applying $A^{-1}$ twice, so $(A^2)^{-1}=(A^{-1})^2=\begin{pmatrix}7&-4\\-12&7\end{pmatrix}$.

## Related workbook topics

- [Exercise 7: Inverse of a Product](problem_07_solution.md)
- [Exercise 13: Undoing a Composite Transformation](problem_13_solution.md)
