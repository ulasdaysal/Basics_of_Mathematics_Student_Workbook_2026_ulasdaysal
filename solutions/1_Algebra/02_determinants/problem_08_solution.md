# Exercise 8. Determinant of a Product

## The question

Let $A,B$ be square matrices with $\det A=3$ and $\det B=-5$. Compute $\det(AB)$, $\det(BA)$ and, if it exists, $\det(A^{-1}B)$. Explain why the first two are equal even though usually $AB\neq BA$.

## Before calculating: what idea do we need?

1. **Product rule:** $\det(AB)=\det A\cdot\det B$.
2. **Inverse rule:** since $AA^{-1}=I$ and $\det I=1$,
$$\det A\cdot\det(A^{-1})=1\quad\Longrightarrow\quad\det(A^{-1})=\frac{1}{\det A}.$$
   $A^{-1}$ exists only if $\det A\neq0$.

The key insight: matrices do not commute, but **determinants are numbers**, and numbers do commute.

## 1. $\det(AB)$

$$\det(AB)=\det A\cdot\det B=3\cdot(-5)=-15.$$

## 2. $\det(BA)$

$$\det(BA)=\det B\cdot\det A=(-5)\cdot3=-15.$$

## 3. $\det(A^{-1}B)$

$\det A=3\neq0$, so $A^{-1}$ exists and $\det(A^{-1})=\tfrac13$. Then

$$\det(A^{-1}B)=\det(A^{-1})\cdot\det B=\frac13\cdot(-5)=-\frac53.$$

## 4. Why $\det(AB)=\det(BA)$ although $AB\neq BA$

The matrices $AB$ and $BA$ are generally different, but the product rule turns both determinants into a product of the **same two numbers**, $3$ and $-5$, and multiplication of numbers is commutative.

Geometrically, $\det$ is the volume scaling factor. $AB$ scales volume first by $\det B$, then by $\det A$. $BA$ does it in the opposite order. The shapes may end up different, but the total volume factor is the same: $|3|\cdot|{-5}|=15$, and both flip orientation once.

## 5. Quick verification with concrete matrices

Take
$$A=\begin{pmatrix}1&1\\0&3\end{pmatrix}\ (\det 3),\qquad B=\begin{pmatrix}1&0\\2&-5\end{pmatrix}\ (\det -5).$$

$$AB=\begin{pmatrix}3&-5\\6&-15\end{pmatrix},\quad BA=\begin{pmatrix}1&1\\2&-13\end{pmatrix}.$$

$AB\neq BA$, but $\det(AB)=-45+30=-15$ and $\det(BA)=-13-2=-15$. ✓

Also $A^{-1}=\tfrac13\begin{pmatrix}3&-1\\0&1\end{pmatrix}$, so $A^{-1}B=\tfrac13\begin{pmatrix}1&5\\2&-5\end{pmatrix}$ and $\det=\tfrac19(-5-10)=-\tfrac{15}{9}=-\tfrac53$. ✓

## How I would explain this in class

> The determinant of a product is the product of determinants, so $\det(AB)=3\cdot(-5)=-15$ and $\det(BA)=-15$ too. The matrices $AB$ and $BA$ can be different, but their determinants are products of the same two numbers, and numbers commute. Since $\det A\neq0$, $A^{-1}$ exists with determinant $\frac13$, so $\det(A^{-1}B)=-\frac53$.

## Related workbook topics

- [Exercise 7: Using properties instead of recomputing](problem_07_solution.md)
- [Exercise 15: Combining determinant properties](problem_15_solution.md)
- [Matrices, Exercise 4: Noncommutativity](../01_matrices_and_operations/problem_04_solution.md)
