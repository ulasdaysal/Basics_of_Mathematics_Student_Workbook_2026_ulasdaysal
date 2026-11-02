# Exercise 14. A Matrix That Is Its Own Inverse

## The question

Assume that a square matrix $A$ satisfies

$$A^2=I.$$

Show that

$$A^{-1}=A.$$

Then give an example of a $2\times2$ matrix different from $I$ and $-I$ that satisfies this condition, and verify it by multiplication.

## Before calculating: what idea do we need?

Recall the definition of the inverse from Exercise 1: a matrix $B$ is the inverse of $A$ ($B=A^{-1}$) if and only if

$$AB=I \quad\text{and}\quad BA=I.$$

A matrix that satisfies $A^2=I$ (equivalently $A^{-1}=A$) is called an **involution**. Geometrically, an involution is a transformation that **undoes itself** when applied twice—such as a reflection across a line or swapping two coordinate axes.

## 1. Show that $A^2=I$ implies $A^{-1}=A$

Write out $A^2$ as the product of $A$ with itself:

$$A^2 = AA.$$

Since we are given $A^2=I$, this equation reads:

$$AA = I.$$

Compare this directly with the definition of the inverse ($AB=I$ and $BA=I$). Taking $B=A$, we have both $AB=AA=I$ and $BA=AA=I$. Therefore, $A$ satisfies the definition of the inverse of $A$, which proves that $A$ is invertible and

$$A^{-1}=A.$$

## 2. Construct a $2\times2$ example different from $I$ and $-I$

We want a transformation of the plane that is not the identity ($I$) and not a $180^\circ$ rotation ($-I$), yet returns every point to where it started when applied twice.

Two natural geometric choices are:
- **Reflection across the $x$-axis** (which flips the sign of $y$):

$$A=\begin{pmatrix}1&0\\0&-1\end{pmatrix}.$$

- **Reflection across the line $y=x$** (which swaps the coordinates $x$ and $y$):

$$P=\begin{pmatrix}0&1\\1&0\end{pmatrix}.$$

Let us choose $A=\begin{pmatrix}1&0\\0&-1\end{pmatrix}$ (clearly $A\neq I$ and $A\neq -I$).

## 3. Verify the example by multiplication

Multiply $A=\begin{pmatrix}1&0\\0&-1\end{pmatrix}$ by itself:

$$A^2=AA=\begin{pmatrix}1&0\\0&-1\end{pmatrix}\begin{pmatrix}1&0\\0&-1\end{pmatrix}=\begin{pmatrix}1\cdot1+0\cdot0 & 1\cdot0+0\cdot(-1)\\0\cdot1+(-1)\cdot0 & 0\cdot0+(-1)\cdot(-1)\end{pmatrix}=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I.$$

Since $AA=I$, we have $A^{-1}=A$.

## Quick verification

Let us also check the coordinate-swapping matrix $P=\begin{pmatrix}0&1\\1&0\end{pmatrix}$:

$$P^2=\begin{pmatrix}0&1\\1&0\end{pmatrix}\begin{pmatrix}0&1\\1&0\end{pmatrix}=\begin{pmatrix}0+1 & 0+0\\0+0 & 1+0\end{pmatrix}=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I.$$

And using the $2\times2$ inverse formula on $A=\begin{pmatrix}1&0\\0&-1\end{pmatrix}$ gives $\det A=-1$, so $A^{-1}=\frac{1}{-1}\begin{pmatrix}-1&0\\0&1\end{pmatrix}=\begin{pmatrix}1&0\\0&-1\end{pmatrix}=A$. ✓

## A concrete example

Watch how the reflection matrix $A=\begin{pmatrix}1&0\\0&-1\end{pmatrix}$ acts on the vector $v=\begin{pmatrix}3\\5\end{pmatrix}$:
1. First reflection across the $x$-axis: $Av=\begin{pmatrix}1&0\\0&-1\end{pmatrix}\begin{pmatrix}3\\5\end{pmatrix}=\begin{pmatrix}3\\-5\end{pmatrix}$.
2. Second reflection across the $x$-axis: $A(Av)=\begin{pmatrix}1&0\\0&-1\end{pmatrix}\begin{pmatrix}3\\-5\end{pmatrix}=\begin{pmatrix}3\\5\end{pmatrix}=v$.

Reflecting a point across the same mirror a second time always puts it right back where it started!

## How I would explain this in class

> By definition, the inverse of $A$ is the matrix $B$ that multiplies with $A$ to give $I$. Since $A^2=I$ just means $A\cdot A=I$, the matrix that multiplies with $A$ to give $I$ is $A$ itself—so $A^{-1}=A$. Geometrically, any reflection does this because reflecting twice brings every point back to its starting spot. For example, $A=\begin{pmatrix}1&0\\0&-1\end{pmatrix}$ reflects across the $x$-axis, is different from $\pm I$, and satisfies $A^2=I$.

## Related workbook topics

- [Exercise 1: Definition of the Inverse](problem_01_solution.md)
- [Exercise 8: Inverse of a Transformation](problem_08_solution.md)
