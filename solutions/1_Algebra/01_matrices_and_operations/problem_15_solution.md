# Exercise 15. Associativity of Multiplication and Different Calculation Paths

## The question

Given

$$A=\begin{pmatrix}1&2&0\\0&1&1\end{pmatrix},\quad B=\begin{pmatrix}1&0\\2&1\\-1&3\end{pmatrix},\quad C=\begin{pmatrix}2&1\\0&-1\end{pmatrix},$$

compute $(AB)C$ and $A(BC)$, compare the results and the number of intermediate operations, and explain what associativity means here.

## Before calculating: what idea do we need?

**Associativity** says

$$(AB)C=A(BC)$$

whenever the products are defined. We may choose where to put the brackets, but **not** the order of the factors (Exercise 4).

Why it should be true: as transformations, both sides mean "apply $C$, then $B$, then $A$". Brackets only say which two steps we combine first.

Sizes: $A$ is $2\times3$, $B$ is $3\times2$, $C$ is $2\times2$. The final result is $2\times2$.

To compare the cost, we count **scalar multiplications**: a $(m\times n)(n\times q)$ product needs $m\cdot n\cdot q$ of them.

## 1. Path 1: $(AB)C$

First $AB$ ($2\times3$ times $3\times2$):

$$AB=\begin{pmatrix}1+4+0&0+2+0\\0+2-1&0+1+3\end{pmatrix}=\begin{pmatrix}5&2\\1&4\end{pmatrix}.$$

Then multiply by $C$:

$$(AB)C=\begin{pmatrix}5\cdot2+2\cdot0&5\cdot1+2\cdot(-1)\\1\cdot2+4\cdot0&1\cdot1+4\cdot(-1)\end{pmatrix}=\begin{pmatrix}10&3\\2&-3\end{pmatrix}.$$

## 2. Path 2: $A(BC)$

First $BC$ ($3\times2$ times $2\times2$):

$$BC=\begin{pmatrix}1\cdot2+0\cdot0&1\cdot1+0\cdot(-1)\\2\cdot2+1\cdot0&2\cdot1+1\cdot(-1)\\-1\cdot2+3\cdot0&-1\cdot1+3\cdot(-1)\end{pmatrix}=\begin{pmatrix}2&1\\4&1\\-2&-4\end{pmatrix}.$$

Then multiply $A$ by it:

$$A(BC)=\begin{pmatrix}2+8+0&1+2+0\\0+4-2&0+1-4\end{pmatrix}=\begin{pmatrix}10&3\\2&-3\end{pmatrix}.$$

## 3. Compare results

$$(AB)C=\begin{pmatrix}10&3\\2&-3\end{pmatrix}=A(BC).\ ✓$$

## 4. Compare the work

| Path | First product | Second product | Total multiplications | Intermediate size |
|---|---|---|---|---|
| $(AB)C$ | $AB$: $2\cdot3\cdot2=12$ | $(AB)C$: $2\cdot2\cdot2=8$ | **20** | $2\times2$ (4 entries) |
| $A(BC)$ | $BC$: $3\cdot2\cdot2=12$ | $A(BC)$: $2\cdot3\cdot2=12$ | **24** | $3\times2$ (6 entries) |

Same answer, but $(AB)C$ is cheaper here because its intermediate matrix is smaller. For large matrices (e.g. in computer graphics or machine learning) a good choice of brackets can save a huge amount of computation.

## 5. Why associativity holds in general

$$\big((AB)C\big)_{ij}=\sum_l\Big(\sum_k a_{ik}b_{kl}\Big)c_{lj}=\sum_k\sum_l a_{ik}b_{kl}c_{lj}=\sum_k a_{ik}\Big(\sum_l b_{kl}c_{lj}\Big)=\big(A(BC)\big)_{ij}.$$

Both sides are the same double sum; only the order of adding is different.

## 6. Quick verification

Apply both to $e_1=(1,0)^T$:

- $Ce_1=(2,0)^T$, $B(2,0)^T=(2,4,-2)^T$, $A(2,4,-2)^T=(2+8,\ 4-2)^T=(10,2)^T$.
- First column of the result: $(10,2)^T$. ✓

## 7. A concrete example

If we only need $ABCx$ for one vector $x$, the cheapest path is $A(B(Cx))$: three matrix-vector products, $4+6+6=16$ multiplications, with no matrix-matrix products at all. Associativity guarantees the same answer.

## How I would explain this in class

> I computed the product in two ways. First $AB=\begin{pmatrix}5&2\\1&4\end{pmatrix}$ and then times $C$. Second $BC$, which is $3\times2$, and then $A$ times it. Both give $\begin{pmatrix}10&3\\2&-3\end{pmatrix}$. That's associativity: the brackets don't change the result, as long as the order $A,B,C$ stays the same. But the work differs: 20 multiplications versus 24, because $(AB)C$ goes through a smaller intermediate matrix.

## Related workbook topics

- [Exercise 3: When can matrices be multiplied?](problem_03_solution.md)
- [Exercise 10: Columns of a matrix product](problem_10_solution.md)
