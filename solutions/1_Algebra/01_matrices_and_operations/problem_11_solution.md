# Exercise 11. When Do Matrices Commute?

## The question

Given

$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}a&b\\c&d\end{pmatrix},$$

find the conditions on $a,b,c,d$ under which $AB=BA$, and describe the general form of all such $B$.

## Before calculating: what idea do we need?

In Exercise 4 we saw that usually $AB\neq BA$. Here we turn the question around: **which** matrices $B$ do commute with this particular $A$?

Strategy: compute both products with unknown entries, then require that they are equal **entry by entry**. Two matrices are equal exactly when all corresponding entries are equal, so we get a system of equations.

## 1. Compute $AB$

$$AB=\begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}a&b\\c&d\end{pmatrix}=\begin{pmatrix}a+c&b+d\\c&d\end{pmatrix}.$$

Multiplying by $A$ from the **left** adds row 2 of $B$ to row 1.

## 2. Compute $BA$

$$BA=\begin{pmatrix}a&b\\c&d\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}=\begin{pmatrix}a&a+b\\c&c+d\end{pmatrix}.$$

Multiplying by $A$ from the **right** adds column 1 of $B$ to column 2.

## 3. Set them equal entry by entry

| Position | Equation | Simplified |
|---|---|---|
| $(1,1)$ | $a+c=a$ | $c=0$ |
| $(1,2)$ | $b+d=a+b$ | $d=a$ |
| $(2,1)$ | $c=c$ | no condition |
| $(2,2)$ | $d=c+d$ | $c=0$ |

So the conditions are

$$c=0\qquad\text{and}\qquad d=a,$$

while $a$ and $b$ can be any real numbers.

## 4. General form

$$B=\begin{pmatrix}a&b\\0&a\end{pmatrix}=a\begin{pmatrix}1&0\\0&1\end{pmatrix}+b\begin{pmatrix}0&1\\0&0\end{pmatrix}=aI+bN,\qquad a,b\in\mathbb{R}.$$

**Meaning:** note that $A=I+N$. So the matrices that commute with $A$ are exactly the combinations of $I$ and $N$, i.e. "polynomials in $A$". This makes sense: $I$ commutes with everything, and $N$ commutes with itself, so any combination of them commutes with $A$. The calculation shows there are **no other** such matrices. Out of a 4-dimensional space of $2\times2$ matrices, only a 2-dimensional family commutes with $A$.

## 5. Quick verification

Take $B=aI+bN$. Then

$$AB=(I+N)(aI+bN)=aI+(a+b)N+bN^2=aI+(a+b)N,$$
$$BA=(aI+bN)(I+N)=aI+(a+b)N+bN^2=aI+(a+b)N,$$

using $N^2=0$. They are equal. ✓

A counter-check with $c\neq0$: $B=\begin{pmatrix}0&0\\1&0\end{pmatrix}$ gives $AB=\begin{pmatrix}1&0\\1&0\end{pmatrix}$ but $BA=\begin{pmatrix}0&0\\1&1\end{pmatrix}$. Not equal, as predicted.

## 6. A concrete example

With $a=3$, $b=-2$:

$$B=\begin{pmatrix}3&-2\\0&3\end{pmatrix},\qquad AB=\begin{pmatrix}3&1\\0&3\end{pmatrix}=BA.$$

## How I would explain this in class

> I compute $AB$ and $BA$ with unknown entries and compare them entry by entry. The equations give $c=0$ and $d=a$, and $b$ is free. So the matrices commuting with $A$ are exactly $\begin{pmatrix}a&b\\0&a\end{pmatrix}=aI+bN$. Since $A=I+N$ itself, these are just combinations of $I$ and $A$. That explains why they commute, and the computation shows no other matrices do.

## Related workbook topics

- [Exercise 4: Noncommutativity](problem_04_solution.md)
- [Exercise 12: Formula for a matrix power](problem_12_solution.md)
