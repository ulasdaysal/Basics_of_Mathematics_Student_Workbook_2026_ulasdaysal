# Exercise 9. Area and the Determinant

## The question

The vectors

$$u=\begin{pmatrix}3\\1\end{pmatrix},\qquad v=\begin{pmatrix}1\\4\end{pmatrix}$$

span a parallelogram. Compute its area using a determinant. Then reverse the order of the vectors and explain what changes in the determinant and what does not change in the area.

## Before calculating: what idea do we need?

Put the vectors as **columns** of a matrix. Then

$$\text{area of parallelogram}=\left|\det\begin{pmatrix}u&v\end{pmatrix}\right|.$$

The **sign** of the determinant carries extra information, which is the orientation:

- $\det>0$: going from $u$ to $v$ is a counterclockwise turn,
- $\det<0$: it is a clockwise turn.

Area is always non-negative, which is why we take the absolute value.

## 1. Compute the determinant

$$\det\begin{pmatrix}3&1\\1&4\end{pmatrix}=3\cdot4-1\cdot1=11.$$

## 2. The area

$$\text{Area}=|11|=11.$$

The determinant is positive, so $v$ lies counterclockwise from $u$.

## 3. Reverse the order

$$\det\begin{pmatrix}v&u\end{pmatrix}=\det\begin{pmatrix}1&3\\4&1\end{pmatrix}=1\cdot1-3\cdot4=-11.$$

| | $\det$ | Area |
|---|---|---|
| $(u,v)$ | $11$ | $11$ |
| $(v,u)$ | $-11$ | $11$ |

- **Changes:** the sign of the determinant. Swapping two columns multiplies the determinant by $-1$ (Exercise 3), because the orientation is reversed: from $v$ to $u$ is a clockwise turn.
- **Does not change:** the area. It is the same parallelogram, so $|\det|$ stays $11$.

## 4. Why the determinant gives the area

The matrix $\begin{pmatrix}u&v\end{pmatrix}$ sends $e_1\mapsto u$ and $e_2\mapsto v$, so it maps the unit square (area $1$) onto our parallelogram. The determinant is the factor by which the matrix scales areas, so the parallelogram has area $|\det|\cdot1$.

## 5. Quick verification (geometric)

Put the parallelogram in the rectangle $[0,4]\times[0,5]$ (vertices $0$, $u=(3,1)$, $v=(1,4)$, $u+v=(4,5)$). The rectangle has area $20$. Outside the parallelogram are two triangles with legs $3,1$ (area $1.5$ each), two triangles with legs $1,4$ (area $2$ each), and two $1\times1$ corner squares (area $1$ each):

$$20-2(1.5)-2(2)-2(1)=20-3-4-2=11.\ ✓$$

## 6. A concrete example

If $v$ were parallel to $u$, e.g. $v=(6,2)$, then $\det=3\cdot2-6\cdot1=0$. The parallelogram collapses into a segment with area $0$, which matches the fact that dependent vectors give $\det=0$.

## How I would explain this in class

> I put $u$ and $v$ as columns, and the determinant is $3\cdot4-1\cdot1=11$, so the area is $11$. If I swap the vectors, the determinant becomes $-11$, because the orientation flips from counterclockwise to clockwise. The parallelogram is the same, so the area, the absolute value, stays $11$.

## Related workbook topics

- [Exercise 3: Swapping two rows](problem_03_solution.md)
- [Exercise 10: Detecting dependence](problem_10_solution.md)
