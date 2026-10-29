# Exercise 9. Composing Transformations

## The question

Let

$$S=\begin{pmatrix}2&0\\0&1\end{pmatrix},\qquad R=\begin{pmatrix}0&-1\\1&0\end{pmatrix},\qquad x=\begin{pmatrix}1\\2\end{pmatrix}.$$

$S$ stretches horizontally by a factor of 2, and $R$ rotates by $90^\circ$ counterclockwise. Compute $RSx$ and $SRx$, compare them, and explain geometrically why the order matters.

## Before calculating: what idea do we need?

A product of matrices is applied to a vector **from right to left**:

$$RSx=R(Sx)\quad\text{means "first } S\text{, then } R\text{"},$$
$$SRx=S(Rx)\quad\text{means "first } R\text{, then } S\text{"}.$$

So matrix multiplication = **composition of transformations**. If the order of the actions matters geometrically, the products will differ.

What the two matrices do:

- $S\begin{pmatrix}u\\v\end{pmatrix}=\begin{pmatrix}2u\\v\end{pmatrix}$: double the $x$-coordinate.
- $R\begin{pmatrix}u\\v\end{pmatrix}=\begin{pmatrix}-v\\u\end{pmatrix}$: rotate by $90^\circ$.

## 1. Compute $RSx$ (stretch, then rotate)

$$Sx=\begin{pmatrix}2\\2\end{pmatrix},\qquad RSx=R\begin{pmatrix}2\\2\end{pmatrix}=\begin{pmatrix}-2\\2\end{pmatrix}.$$

## 2. Compute $SRx$ (rotate, then stretch)

$$Rx=\begin{pmatrix}-2\\1\end{pmatrix},\qquad SRx=S\begin{pmatrix}-2\\1\end{pmatrix}=\begin{pmatrix}-4\\1\end{pmatrix}.$$

## 3. Compare

$$RSx=\begin{pmatrix}-2\\2\end{pmatrix}\neq\begin{pmatrix}-4\\1\end{pmatrix}=SRx.$$

The matrices themselves also differ:

$$RS=\begin{pmatrix}0&-1\\2&0\end{pmatrix},\qquad SR=\begin{pmatrix}0&-2\\1&0\end{pmatrix}.$$

## 4. Geometric explanation

The stretch $S$ treats the two axes differently: it stretches only the horizontal direction.

- In $RS$, we stretch **first**, so the original $x$-coordinate ($1$) is doubled, and then the rotation moves it into the vertical direction.
- In $SR$, we rotate **first**, so the original $y$-coordinate ($2$) is moved into the horizontal direction, and *that* gets doubled.

Different parts of the vector get stretched, so the results differ. If the scaling were the same in every direction (e.g. $2I$), the order would not matter, because a uniform scaling has no preferred direction.

## 5. Quick verification

- Lengths: $\|x\|=\sqrt5$. Rotation keeps length, so $\|Rx\|=\sqrt5$. ✓
- $RSx=(RS)x=\begin{pmatrix}0\cdot1-1\cdot2\\2\cdot1+0\cdot2\end{pmatrix}=\begin{pmatrix}-2\\2\end{pmatrix}$. ✓
- $SRx=(SR)x=\begin{pmatrix}0\cdot1-2\cdot2\\1\cdot1+0\cdot2\end{pmatrix}=\begin{pmatrix}-4\\1\end{pmatrix}$. ✓

## 6. A concrete example

Take the unit square. Under $RS$ it is first stretched into a $2\times1$ rectangle lying flat, then rotated so it stands upright ($1$ wide, $2$ tall). Under $SR$ it is first rotated (still a unit square), then stretched into a flat $2\times1$ rectangle. Same area $2$ in both cases ($|\det|=2$), but different shapes and orientations.

## How I would explain this in class

> A product acts from right to left, so $RSx$ means stretch first, then rotate, and $SRx$ means rotate first, then stretch. I get $RSx=(-2,2)$ and $SRx=(-4,1)$. They differ because the stretch only affects the horizontal direction: depending on the order, a different coordinate of $x$ ends up being doubled. This is the geometric reason why matrix multiplication is not commutative.

## Related workbook topics

- [Exercise 4: Noncommutativity](problem_04_solution.md)
- [Exercise 14: Rotation matrices](problem_14_solution.md)
