# Exercise 14. Rotation Matrices

## The question

The matrix of a rotation through angle $\theta$ is

$$R(\theta)=\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}.$$

Compute $R(\alpha)R(\beta)$ and, using the angle-sum formulas, show that

$$R(\alpha)R(\beta)=R(\alpha+\beta).$$

Explain the result geometrically.

## Before calculating: what idea do we need?

1. **Where the matrix comes from:** the columns of a matrix are the images of $e_1$ and $e_2$ (Exercise 5). Rotating $e_1=(1,0)$ by $\theta$ gives $(\cos\theta,\sin\theta)$, and rotating $e_2=(0,1)$ gives $(-\sin\theta,\cos\theta)$. These are exactly the columns of $R(\theta)$.
2. **Product = composition:** $R(\alpha)R(\beta)$ means "rotate by $\beta$, then by $\alpha$" (Exercise 9).
3. **Angle-sum formulas:**
$$\cos(\alpha+\beta)=\cos\alpha\cos\beta-\sin\alpha\sin\beta,$$
$$\sin(\alpha+\beta)=\sin\alpha\cos\beta+\cos\alpha\sin\beta.$$

## 1. Multiply the matrices

$$R(\alpha)R(\beta)=\begin{pmatrix}\cos\alpha&-\sin\alpha\\\sin\alpha&\cos\alpha\end{pmatrix}\begin{pmatrix}\cos\beta&-\sin\beta\\\sin\beta&\cos\beta\end{pmatrix}$$

$$=\begin{pmatrix}\cos\alpha\cos\beta-\sin\alpha\sin\beta & -\cos\alpha\sin\beta-\sin\alpha\cos\beta\\ \sin\alpha\cos\beta+\cos\alpha\sin\beta & -\sin\alpha\sin\beta+\cos\alpha\cos\beta\end{pmatrix}.$$

## 2. Apply the angle-sum formulas

Entry by entry:

- $(1,1)$: $\cos\alpha\cos\beta-\sin\alpha\sin\beta=\cos(\alpha+\beta)$,
- $(1,2)$: $-(\sin\alpha\cos\beta+\cos\alpha\sin\beta)=-\sin(\alpha+\beta)$,
- $(2,1)$: $\sin\alpha\cos\beta+\cos\alpha\sin\beta=\sin(\alpha+\beta)$,
- $(2,2)$: $\cos\alpha\cos\beta-\sin\alpha\sin\beta=\cos(\alpha+\beta)$.

Therefore

$$R(\alpha)R(\beta)=\begin{pmatrix}\cos(\alpha+\beta)&-\sin(\alpha+\beta)\\\sin(\alpha+\beta)&\cos(\alpha+\beta)\end{pmatrix}=R(\alpha+\beta).\ \blacksquare$$

## 3. Geometric meaning

Rotating by $\beta$ and then by $\alpha$ is the same as rotating once by $\alpha+\beta$. The matrix algebra agrees with what we expect geometrically.

Consequences:

- **Rotations commute:** $R(\alpha)R(\beta)=R(\alpha+\beta)=R(\beta+\alpha)=R(\beta)R(\alpha)$. This is a special family where order does *not* matter (unlike Exercise 9, where a stretch was involved).
- **Inverse:** $R(\theta)R(-\theta)=R(0)=I$, so $R(\theta)^{-1}=R(-\theta)$: undo a rotation by rotating back.
- **Powers:** $R(\theta)^n=R(n\theta)$.

The result can also be read the other way round: if we trust the geometry, multiplying the matrices **proves** the angle-sum formulas.

## 4. Quick verification

- $\alpha=\beta=90^\circ$: $R(90^\circ)=\begin{pmatrix}0&-1\\1&0\end{pmatrix}$, and
$$R(90^\circ)^2=\begin{pmatrix}-1&0\\0&-1\end{pmatrix}=R(180^\circ).\ ✓$$
- Determinant: $\det R(\theta)=\cos^2\theta+\sin^2\theta=1$, and $1\cdot1=1=\det R(\alpha+\beta)$. ✓

## 5. A concrete example

$\alpha=30^\circ$, $\beta=60^\circ$:

$$R(30^\circ)R(60^\circ)=\begin{pmatrix}\tfrac{\sqrt3}{2}&-\tfrac12\\\tfrac12&\tfrac{\sqrt3}{2}\end{pmatrix}\begin{pmatrix}\tfrac12&-\tfrac{\sqrt3}{2}\\\tfrac{\sqrt3}{2}&\tfrac12\end{pmatrix}=\begin{pmatrix}\tfrac{\sqrt3}{4}-\tfrac{\sqrt3}{4}&-\tfrac34-\tfrac14\\\tfrac14+\tfrac34&-\tfrac{\sqrt3}{4}+\tfrac{\sqrt3}{4}\end{pmatrix}=\begin{pmatrix}0&-1\\1&0\end{pmatrix}=R(90^\circ).\ ✓$$

## How I would explain this in class

> I multiply the two rotation matrices and get entries like $\cos\alpha\cos\beta-\sin\alpha\sin\beta$. By the angle-sum formulas these are exactly $\cos(\alpha+\beta)$ and $\sin(\alpha+\beta)$, so $R(\alpha)R(\beta)=R(\alpha+\beta)$. Geometrically, two rotations in a row are one rotation by the total angle. That's why rotations commute and why $R(-\theta)$ is the inverse of $R(\theta)$.

## Related workbook topics

- [Exercise 9: Composing transformations](problem_09_solution.md)
- [Exercise 5: Matrix times vector](problem_05_solution.md)
