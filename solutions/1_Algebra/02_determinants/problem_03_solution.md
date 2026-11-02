# Exercise 3. Swapping Two Rows

## The question

For

$$A=\begin{pmatrix}1&2&0\\0&3&1\\2&1&1\end{pmatrix}$$

compute $\det A$. Form $B$ by swapping the first and second rows of $A$, predict $\det B$ using a determinant property, and verify the prediction by calculation.

## Before calculating: what idea do we need?

Two tools:

1. **Cofactor expansion along the first row:**
$$\det A=a_{11}M_{11}-a_{12}M_{12}+a_{13}M_{13},$$
where $M_{1j}$ is the $2\times2$ determinant left after deleting row 1 and column $j$. The signs alternate $+,-,+$.
2. **Row swap property:** swapping two rows **changes the sign** of the determinant but not its absolute value. Geometrically, a swap flips the orientation (like a mirror) but keeps the volume.

## 1. Compute $\det A$

$$\det A=1\cdot\det\begin{pmatrix}3&1\\1&1\end{pmatrix}-2\cdot\det\begin{pmatrix}0&1\\2&1\end{pmatrix}+0\cdot(\dots)$$
$$=1\cdot(3-1)-2\cdot(0-2)+0=2+4=6.$$

## 2. Form $B$ and predict

$$B=\begin{pmatrix}0&3&1\\1&2&0\\2&1&1\end{pmatrix}.$$

$B$ is obtained from $A$ by one row swap, so the prediction is

$$\det B=-\det A=-6.$$

## 3. Verify by calculation

$$\det B=0\cdot\det\begin{pmatrix}2&0\\1&1\end{pmatrix}-3\cdot\det\begin{pmatrix}1&0\\2&1\end{pmatrix}+1\cdot\det\begin{pmatrix}1&2\\2&1\end{pmatrix}$$
$$=0-3\cdot(1-0)+1\cdot(1-4)=-3-3=-6.\ ✓$$

The prediction is confirmed.

## 4. Why a swap changes the sign

In every term of the determinant expansion, each row contributes one entry according to a permutation of the columns. Swapping two rows composes every permutation with a transposition, which changes the parity of the corresponding permutation in the determinant expansion and reverses its coefficient sign. Geometrically, the volume spanned by the rows stays the same, but the orientation flips.

Consequence: if two rows are **equal**, swapping them changes nothing, but must change the sign. So $\det=-\det$, which forces $\det=0$.

## 5. Quick verification

Check $\det A$ with Sarrus' rule:

$$(1\cdot3\cdot1+2\cdot1\cdot2+0)-(0+1\cdot1\cdot1+2\cdot0\cdot1)=(3+4)-1=6.\ ✓$$

## 6. A concrete example

Swapping twice returns $A$, and the sign flips twice: $(-1)^2\cdot6=6$. In general, $k$ swaps multiply the determinant by $(-1)^k$.

## How I would explain this in class

> Expanding along the first row gives $\det A=2+4=6$. Swapping two rows only flips the sign, so I predict $\det B=-6$. Computing $\det B$ directly gives $-3-3=-6$, as predicted. A swap keeps the volume but reverses the orientation.

## Related workbook topics

- [Exercise 2: Determinant of a 3×3 matrix](problem_02_solution.md)
- [Exercise 5: Row operations](problem_05_solution.md)
