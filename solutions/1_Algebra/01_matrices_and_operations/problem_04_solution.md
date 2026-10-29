# Exercise 4. Matrix Multiplication and Noncommutativity

## The question

For

$$A=\begin{pmatrix}1&2\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}2&0\\3&1\end{pmatrix}$$

compute $AB$ and $BA$. Is $AB=BA$? Use the example to explain noncommutativity.

## Before calculating: what idea do we need?

The entry in row $i$, column $j$ of a product is

$$(AB)_{ij}=\sum_k a_{ik}b_{kj}=(\text{row } i \text{ of } A)\cdot(\text{column } j \text{ of } B).$$

For numbers we know $xy=yx$. For matrices, $AB$ uses rows of $A$ and columns of $B$, while $BA$ uses rows of $B$ and columns of $A$. These are different pairs of numbers, so there is no reason to expect the same result.

## 1. Compute $AB$

$$AB=\begin{pmatrix}1\cdot2+2\cdot3 & 1\cdot0+2\cdot1\\ 0\cdot2+1\cdot3 & 0\cdot0+1\cdot1\end{pmatrix}=\begin{pmatrix}8&2\\3&1\end{pmatrix}.$$

## 2. Compute $BA$

$$BA=\begin{pmatrix}2\cdot1+0\cdot0 & 2\cdot2+0\cdot1\\ 3\cdot1+1\cdot0 & 3\cdot2+1\cdot1\end{pmatrix}=\begin{pmatrix}2&4\\3&7\end{pmatrix}.$$

## 3. Compare

$$AB=\begin{pmatrix}8&2\\3&1\end{pmatrix}\neq\begin{pmatrix}2&4\\3&7\end{pmatrix}=BA.$$

So **matrix multiplication is not commutative**: in general $AB\neq BA$, even when both products exist and have the same size.

## 4. What this means

- **Algebraically:** we cannot swap factors. For example $(A+B)^2=A^2+AB+BA+B^2$, and in general this is **not** $A^2+2AB+B^2$.
- **Geometrically:** a matrix is a transformation. $AB$ means "first apply $B$, then $A$". Here $A$ is a horizontal shear and $B$ mixes coordinates differently, and doing them in different orders moves points to different places (see Exercise 9).

Note that some pairs *do* commute (e.g. any matrix with $I$). Noncommutativity means "not always", not "never" (see Exercise 11).

## 5. Quick verification

Two invariants must agree for $AB$ and $BA$ even though the matrices differ:

- **Determinant:** $\det(AB)=8\cdot1-2\cdot3=2$, $\det(BA)=2\cdot7-4\cdot3=2$, and $\det A\cdot\det B=1\cdot2=2$. ✓
- **Trace** (sum of diagonal): $\operatorname{tr}(AB)=8+1=9$, $\operatorname{tr}(BA)=2+7=9$. ✓

These agreements give us confidence that both products were computed correctly.

## 6. A concrete example

Apply both products to $x=\begin{pmatrix}1\\0\end{pmatrix}$:

$$ABx=\begin{pmatrix}8\\3\end{pmatrix},\qquad BAx=\begin{pmatrix}2\\3\end{pmatrix}.$$

The same starting vector lands in different places depending on the order of the transformations.

## How I would explain this in class

> I compute each entry as a row times a column. $AB=\begin{pmatrix}8&2\\3&1\end{pmatrix}$ but $BA=\begin{pmatrix}2&4\\3&7\end{pmatrix}$, so $AB\neq BA$. The reason is that the two products pair different rows with different columns. Geometrically, doing transformation $B$ then $A$ is not the same as $A$ then $B$. That is what noncommutativity means.

## Related workbook topics

- [Exercise 9: Composing transformations](problem_09_solution.md)
- [Exercise 11: When do matrices commute?](problem_11_solution.md)
