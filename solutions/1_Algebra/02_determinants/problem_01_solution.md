# Exercise 1. Determinant of a 2×2 Matrix

## The question

Compute

$$\det\begin{pmatrix}3&-2\\5&4\end{pmatrix},\qquad \det\begin{pmatrix}1&7\\2&14\end{pmatrix}.$$

Which matrix is invertible? Justify the answer.

## Before calculating: what idea do we need?

For a $2\times2$ matrix

$$\det\begin{pmatrix}a&b\\c&d\end{pmatrix}=ad-bc.$$

The determinant tells us whether the matrix loses information:

- $\det\neq0$: the matrix is **invertible**,
- $\det=0$: the matrix is **singular**. Its rows (and columns) are dependent, and it cannot be undone.

The reason is the inverse formula $\dfrac{1}{ad-bc}\begin{pmatrix}d&-b\\-c&a\end{pmatrix}$. It requires dividing by the determinant.

## 1. First matrix

$$\det\begin{pmatrix}3&-2\\5&4\end{pmatrix}=3\cdot4-(-2)\cdot5=12+10=22.$$

## 2. Second matrix

$$\det\begin{pmatrix}1&7\\2&14\end{pmatrix}=1\cdot14-7\cdot2=14-14=0.$$

## 3. Which one is invertible?

- The first matrix has $\det=22\neq0$, so it **is invertible**.
- The second matrix has $\det=0$, so it **is not invertible**.

## 4. Why the second one fails

The second row is twice the first row:

$$(2,14)=2\cdot(1,7).$$

The two rows carry the same information. Geometrically, the matrix squashes the whole plane onto a single line (every image is a multiple of $(1,2)^T$). Many different points land on the same point, so the map cannot be reversed.

## 5. Quick verification

For the first matrix, the inverse formula gives

$$A^{-1}=\frac{1}{22}\begin{pmatrix}4&2\\-5&3\end{pmatrix}.$$

Check:

$$\begin{pmatrix}3&-2\\5&4\end{pmatrix}\begin{pmatrix}4&2\\-5&3\end{pmatrix}=\begin{pmatrix}12+10&6-6\\20-20&10+12\end{pmatrix}=\begin{pmatrix}22&0\\0&22\end{pmatrix}=22I.$$

After dividing by $22$ we get $I$. ✓

## 6. A concrete example

For the second matrix, two different vectors give the same result:

$$\begin{pmatrix}1&7\\2&14\end{pmatrix}\begin{pmatrix}7\\0\end{pmatrix}=\begin{pmatrix}7\\14\end{pmatrix}=\begin{pmatrix}1&7\\2&14\end{pmatrix}\begin{pmatrix}0\\1\end{pmatrix}.$$

From the output $(7,14)^T$ we cannot tell which input we started with. That is exactly what "not invertible" means.

## How I would explain this in class

> For a $2\times2$ matrix the determinant is $ad-bc$. The first one is $12+10=22$, which is not zero, so it is invertible. The second one is $14-14=0$, because its second row is twice the first. Its rows are dependent, the plane is squashed onto a line, and the matrix cannot be inverted.

## Related workbook topics

- [Exercise 6: Parameter and invertibility](problem_06_solution.md)
- [Exercise 10: Detecting dependence](problem_10_solution.md)
