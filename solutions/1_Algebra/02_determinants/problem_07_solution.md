# Exercise 7. Using Properties Instead of Recomputing

## The question

For a $3\times3$ matrix with $\det A=-4$, compute

$$\det(2A),\qquad \det(A^T),\qquad \det(A^2),\qquad \det(-A),$$

justifying each answer with the appropriate property.

## Before calculating: what idea do we need?

We don't know the entries of $A$, so we **cannot** compute anything directly. We must use properties instead:

| Property | Formula ($n\times n$) |
|---|---|
| Scaling | $\det(cA)=c^n\det A$ |
| Transpose | $\det(A^T)=\det A$ |
| Product | $\det(AB)=\det A\cdot\det B$ |

The scaling rule is the one most often done wrong: $cA$ multiplies **every row** by $c$, and each row contributes one factor $c$. With $n$ rows we get $c^n$, not $c$.

## 1. $\det(2A)$

$A$ is $3\times3$, so all three rows are multiplied by $2$:

$$\det(2A)=2^3\det A=8\cdot(-4)=-32.$$

## 2. $\det(A^T)$

Transposing does not change the determinant (rows and columns play symmetric roles):

$$\det(A^T)=\det A=-4.$$

## 3. $\det(A^2)$

By the product rule:

$$\det(A^2)=\det(A\cdot A)=\det A\cdot\det A=(-4)^2=16.$$

## 4. $\det(-A)$

$-A=(-1)A$, so by the scaling rule with $n=3$:

$$\det(-A)=(-1)^3\det A=-1\cdot(-4)=4.$$

## 5. Summary and meaning

| Expression | Property | Value |
|---|---|---|
| $\det(2A)$ | $c^n\det A$ | $-32$ |
| $\det(A^T)$ | transpose invariance | $-4$ |
| $\det(A^2)$ | product rule | $16$ |
| $\det(-A)$ | $(-1)^n\det A$ | $4$ |

Geometric reading: $A$ scales volume by $4$ and flips orientation. $2A$ also doubles every length, which multiplies volume by $2^3=8$. $A^2$ flips orientation twice, so the sign becomes positive. $-A=(-I)A$ applies $A$ and then a point reflection $-I$; the reflection $-I$ has determinant $(-1)^3=-1$ in dimension 3, so composing it with $A$ changes the determinant from $-4$ to $+4$.

## 6. Quick verification with a concrete matrix

Take $A=\operatorname{diag}(-4,1,1)$, so $\det A=-4$. Then

- $2A=\operatorname{diag}(-8,2,2)$, $\det=-32$. ✓
- $A^T=A$, $\det=-4$. ✓
- $A^2=\operatorname{diag}(16,1,1)$, $\det=16$. ✓
- $-A=\operatorname{diag}(4,-1,-1)$, $\det=4$. ✓

## 7. A concrete example of the common mistake

Writing $\det(2A)=2\det A=-8$ would be wrong. For a $3\times3$ matrix, scaling by $2$ doubles length, width and height, so volume grows by $8$, not $2$.

## How I would explain this in class

> I can't compute $A$, so I use properties. Multiplying a $3\times3$ matrix by $2$ multiplies each of the three rows by $2$, so $\det(2A)=8\cdot(-4)=-32$. Transposing doesn't change the determinant, so $\det A^T=-4$. The product rule gives $\det A^2=16$, and $\det(-A)=(-1)^3(-4)=4$.

## Related workbook topics

- [Exercise 8: Determinant of a product](problem_08_solution.md)
- [Exercise 15: Combining determinant properties](problem_15_solution.md)
