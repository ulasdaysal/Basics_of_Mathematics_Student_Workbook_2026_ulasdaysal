# Exercise 8. Inverse of a Transformation

## The question

The matrix

$$S=\begin{pmatrix}2&0\\0&\frac12\end{pmatrix}$$

describes a scaling of the plane. Find $S^{-1}$ and explain geometrically what the inverse transformation does. Check the action of the pair $S,S^{-1}$ on one simple vector.

## Before calculating: what idea do we need?

A matrix is not just a table of numbers—it represents a **geometric transformation** of the plane.
- For a diagonal matrix $\begin{pmatrix}d_1&0\\0&d_2\end{pmatrix}$, the first coordinate $x$ is multiplied by $d_1$ and the second coordinate $y$ is multiplied by $d_2$.
- The **inverse matrix** $S^{-1}$ represents the **inverse transformation**: the geometric operation that reverses $S$ and brings every point back to where it started.

## 1. How $S$ acts on the plane

Apply $S$ to a general point $\begin{pmatrix}x\\y\end{pmatrix}$:

$$S\begin{pmatrix}x\\y\end{pmatrix}=\begin{pmatrix}2&0\\0&\frac{1}{2}\end{pmatrix}\begin{pmatrix}x\\y\end{pmatrix}=\begin{pmatrix}2x\\\frac{1}{2}y\end{pmatrix}.$$

Geometrically, $S$:
- **stretches** the plane horizontally (along the $x$-axis) by a factor of $2$,
- **compresses** the plane vertically (along the $y$-axis) by a factor of $\frac{1}{2}$.

## 2. Find $S^{-1}$

For a diagonal matrix with non-zero diagonal entries, we simply take the reciprocal of each diagonal entry (or use the $2\times2$ formula with $\det S = 2\cdot\frac{1}{2} = 1$):

$$S^{-1}=\begin{pmatrix}\frac{1}{2}&0\\0&2\end{pmatrix}.$$

## 3. Geometric meaning of $S^{-1}$

Apply $S^{-1}$ to a point $\begin{pmatrix}x'\\y'\end{pmatrix}$:

$$S^{-1}\begin{pmatrix}x'\\y'\end{pmatrix}=\begin{pmatrix}\frac{1}{2}&0\\0&2\end{pmatrix}\begin{pmatrix}x'\\y'\end{pmatrix}=\begin{pmatrix}\frac{1}{2}x'\\2y'\end{pmatrix}.$$

Geometrically, $S^{-1}$ does the exact opposite of $S$:
- where $S$ doubled the horizontal coordinate, $S^{-1}$ **halves** it (scales horizontally by $\frac{1}{2}$),
- where $S$ halved the vertical coordinate, $S^{-1}$ **doubles** it (scales vertically by $2$).

## 4. Check the action of $S$ and $S^{-1}$ on a simple vector

Choose the vector $v=\begin{pmatrix}3\\4\end{pmatrix}$.

First, apply $S$:

$$Sv=\begin{pmatrix}2&0\\0&\frac{1}{2}\end{pmatrix}\begin{pmatrix}3\\4\end{pmatrix}=\begin{pmatrix}6\\2\end{pmatrix}.$$

(The $x$-coordinate doubled from $3$ to $6$, and the $y$-coordinate halved from $4$ to $2$.)

Next, apply $S^{-1}$ to the transformed vector $\begin{pmatrix}6\\2\end{pmatrix}$:

$$S^{-1}(Sv)=\begin{pmatrix}\frac{1}{2}&0\\0&2\end{pmatrix}\begin{pmatrix}6\\2\end{pmatrix}=\begin{pmatrix}3\\4\end{pmatrix}=v.$$

The vector returns to its original coordinates $(3,4)^T$.

## Quick verification

Check that $SS^{-1}=I$:

$$SS^{-1}=\begin{pmatrix}2&0\\0&\frac{1}{2}\end{pmatrix}\begin{pmatrix}\frac{1}{2}&0\\0&2\end{pmatrix}=\begin{pmatrix}2\cdot\frac{1}{2}&0\\0&\frac{1}{2}\cdot2\end{pmatrix}=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I.$$

The product is the identity matrix $I$. ✓

## A concrete example

Consider the unit square $[0,1]\times[0,1]$, which has width $1$, height $1$, and area $1$:
- Under $S$, the unit square is stretched into a wide, flat rectangle $[0,2]\times[0,\frac{1}{2}]$ of width $2$ and height $\frac{1}{2}$ (notice its area is still $2\cdot\frac{1}{2}=1$ because $\det S=1$).
- Under $S^{-1}$, that flat rectangle $[0,2]\times[0,\frac{1}{2}]$ is compressed horizontally by $\frac{1}{2}$ and stretched vertically by $2$, restoring the original $[0,1]\times[0,1]$ unit square.

## How I would explain this in class

> The matrix $S$ stretches the $x$-direction by $2$ and squashes the $y$-direction by $\frac{1}{2}$. To undo that geometrically, we need to shrink the $x$-direction by $\frac{1}{2}$ and stretch the $y$-direction by $2$. That immediately tells us $S^{-1}=\begin{pmatrix}1/2&0\\0&2\end{pmatrix}$. When we test this on $v=(3,4)^T$, $S$ moves it to $(6,2)^T$, and $S^{-1}$ brings $(6,2)^T$ right back to $(3,4)^T$.

## Related workbook topics

- [Exercise 10: Inverse of a Diagonal Matrix](problem_10_solution.md)
- [Exercise 13: Undoing a Composite Transformation](problem_13_solution.md)
