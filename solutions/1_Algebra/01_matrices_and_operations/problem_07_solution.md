# Exercise 7. Identity Matrix, Zero Matrix, and Powers

## The question

For

$$A=\begin{pmatrix}2&1\\0&2\end{pmatrix}$$

compute

$$AI,\qquad IA,\qquad A+0,\qquad A^2,\qquad A^3.$$

Explain the roles of $I$ and $0$, and describe the pattern in successive powers of $A$.

## Before calculating: what idea do we need?

For numbers, $1$ is neutral for multiplication ($1\cdot x=x$) and $0$ is neutral for addition ($x+0=x$). Matrices have the same two neutral elements:

$$I=\begin{pmatrix}1&0\\0&1\end{pmatrix},\qquad 0=\begin{pmatrix}0&0\\0&0\end{pmatrix}.$$

Powers are repeated multiplication: $A^2=AA$, $A^3=A^2A$. A good trick here is to split $A$ into simple parts:

$$A=2I+N,\qquad N=\begin{pmatrix}0&1\\0&0\end{pmatrix},\qquad N^2=0.$$

## 1. Multiplying by $I$

$$AI=\begin{pmatrix}2\cdot1+1\cdot0&2\cdot0+1\cdot1\\0\cdot1+2\cdot0&0\cdot0+2\cdot1\end{pmatrix}=\begin{pmatrix}2&1\\0&2\end{pmatrix}=A,$$

$$IA=\begin{pmatrix}1\cdot2+0\cdot0&1\cdot1+0\cdot2\\0\cdot2+1\cdot0&0\cdot1+1\cdot2\end{pmatrix}=\begin{pmatrix}2&1\\0&2\end{pmatrix}=A.$$

$I$ leaves $A$ unchanged from **both** sides. As a transformation, $I$ does nothing to any vector.

## 2. Adding $0$

$$A+0=\begin{pmatrix}2+0&1+0\\0+0&2+0\end{pmatrix}=A.$$

$0$ is neutral for addition. (Note that $A\cdot0=0$: as a transformation, $0$ sends every vector to the origin.)

## 3. Powers

$$A^2=\begin{pmatrix}2&1\\0&2\end{pmatrix}\begin{pmatrix}2&1\\0&2\end{pmatrix}=\begin{pmatrix}4&2+2\\0&4\end{pmatrix}=\begin{pmatrix}4&4\\0&4\end{pmatrix},$$

$$A^3=A^2A=\begin{pmatrix}4&4\\0&4\end{pmatrix}\begin{pmatrix}2&1\\0&2\end{pmatrix}=\begin{pmatrix}8&4+8\\0&8\end{pmatrix}=\begin{pmatrix}8&12\\0&8\end{pmatrix}.$$

## 4. The pattern

| $n$ | $A^n$ | diagonal | top-right |
|---|---|---|---|
| 1 | $\begin{pmatrix}2&1\\0&2\end{pmatrix}$ | $2^1$ | $1=1\cdot2^0$ |
| 2 | $\begin{pmatrix}4&4\\0&4\end{pmatrix}$ | $2^2$ | $4=2\cdot2^1$ |
| 3 | $\begin{pmatrix}8&12\\0&8\end{pmatrix}$ | $2^3$ | $12=3\cdot2^2$ |

Conjecture:

$$A^n=\begin{pmatrix}2^n&n\,2^{n-1}\\0&2^n\end{pmatrix}.$$

The diagonal simply doubles, while the top-right entry grows faster than $2^n$ because of the extra factor $n$.

## 5. Why the pattern holds

$2I$ commutes with every matrix, so the binomial formula may be used. Since $N^2=0$, all terms with $N^2$ or higher vanish:

$$A^n=(2I+N)^n=(2I)^n+n(2I)^{n-1}N=2^nI+n\,2^{n-1}N=\begin{pmatrix}2^n&n\,2^{n-1}\\0&2^n\end{pmatrix}.$$

## 6. Quick verification

- $n=1$: $\begin{pmatrix}2&1\\0&2\end{pmatrix}$. ✓ $n=2$: $\begin{pmatrix}4&4\\0&4\end{pmatrix}$. ✓ $n=3$: $\begin{pmatrix}8&12\\0&8\end{pmatrix}$. ✓
- Determinant: $\det A^3=64=(\det A)^3=4^3$. ✓

## 7. A concrete example

The formula predicts

$$A^4=\begin{pmatrix}16&32\\0&16\end{pmatrix}.$$

Direct check: $A^3A=\begin{pmatrix}8&12\\0&8\end{pmatrix}\begin{pmatrix}2&1\\0&2\end{pmatrix}=\begin{pmatrix}16&8+24\\0&16\end{pmatrix}=\begin{pmatrix}16&32\\0&16\end{pmatrix}$. ✓

## How I would explain this in class

> $I$ plays the role of the number 1: $AI=IA=A$. The zero matrix plays the role of 0 in addition: $A+0=A$. For powers, I got $A^2=\begin{pmatrix}4&4\\0&4\end{pmatrix}$ and $A^3=\begin{pmatrix}8&12\\0&8\end{pmatrix}$. The diagonal is $2^n$ and the corner is $n\,2^{n-1}$. This comes from writing $A=2I+N$ with $N^2=0$, so only two terms of the binomial expansion survive.

## Related workbook topics

- [Exercise 12: Formula for a matrix power](problem_12_solution.md)
- [Exercise 13: A recurrence in matrix form](problem_13_solution.md)
