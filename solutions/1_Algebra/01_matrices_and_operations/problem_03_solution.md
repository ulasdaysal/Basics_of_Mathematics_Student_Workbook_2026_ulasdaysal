# Exercise 3. When Can Matrices Be Multiplied?

## The question

The matrix sizes are

$$A_{2\times3},\qquad B_{3\times4},\qquad C_{4\times2},\qquad D_{2\times2}.$$

For the products

$$AB,\ BA,\ BC,\ CB,\ AC,\ CA,\ AD,\ DA$$

decide whether each is defined and, if so, state the size of the result.

## Before calculating: what idea do we need?

Each entry of $PQ$ is a **row of $P$ times a column of $Q$**: multiply matching entries and add. That only works if a row of $P$ and a column of $Q$ have the same length.

- A row of $P_{m\times n}$ has $n$ entries.
- A column of $Q_{p\times q}$ has $p$ entries.

**Compatibility rule:**

$$P_{m\times n}\,Q_{p\times q}\ \text{is defined}\iff n=p,\qquad\text{and then } PQ \text{ is } m\times q.$$

A handy picture: write the sizes next to each other. The **inner** numbers must match, and the **outer** numbers give the result:

$$(m\times \underbrace{n)\,(p}_{\text{must match}}\times q)\ \longrightarrow\ m\times q.$$

## 1. Checking each product

| Product | Sizes | Inner numbers | Defined? | Result size |
|---|---|---|---|---|
| $AB$ | $(2\times3)(3\times4)$ | $3=3$ | yes | $2\times4$ |
| $BA$ | $(3\times4)(2\times3)$ | $4\neq2$ | no | — |
| $BC$ | $(3\times4)(4\times2)$ | $4=4$ | yes | $3\times2$ |
| $CB$ | $(4\times2)(3\times4)$ | $2\neq3$ | no | — |
| $AC$ | $(2\times3)(4\times2)$ | $3\neq4$ | no | — |
| $CA$ | $(4\times2)(2\times3)$ | $2=2$ | yes | $4\times3$ |
| $AD$ | $(2\times3)(2\times2)$ | $3\neq2$ | no | — |
| $DA$ | $(2\times2)(2\times3)$ | $2=2$ | yes | $2\times3$ |

## 2. What the table tells us

- $AB$ exists but $BA$ does not. The **order of factors matters** even for whether a product exists, before we compute anything.
- $DA$ exists but $AD$ does not. Multiplying by a square matrix $D$ from the left keeps the shape of $A$ ($2\times3$), but $D$ cannot be placed on the right.
- Products can be chained when consecutive inner sizes match: $ABC$ is $(2\times3)(3\times4)(4\times2)$, which gives a $2\times2$ matrix.

## 3. Why the failed cases fail

Take $BA$. A row of $B$ has 4 entries, and a column of $A$ has 2 entries. Pairing them up leaves 2 entries of the row without partners, so a "row times column" cannot be formed. The same reasoning applies to every "no" in the table.

## 4. Quick verification

The result size can be checked by counting: $AB$ has one entry for every (row of $A$, column of $B$) pair. $A$ has 2 rows and $B$ has 4 columns, so $AB$ has $2\cdot4=8$ entries arranged as $2\times4$. ✓ Similarly $CA$ has $4$ rows (from $C$) and $3$ columns (from $A$). ✓

## 5. A concrete example

Let $A=\begin{pmatrix}1&0&2\\0&1&1\end{pmatrix}$ ($2\times3$) and $D=\begin{pmatrix}1&1\\0&1\end{pmatrix}$ ($2\times2$). Then

$$DA=\begin{pmatrix}1&1&3\\0&1&1\end{pmatrix}\quad(2\times3),$$

while $AD$ would need a row of $A$ (3 entries) times a column of $D$ (2 entries), which is impossible.

## How I would explain this in class

> Before multiplying, I write the sizes side by side. The inner numbers must be equal, because a row of the first matrix is paired with a column of the second. The outer numbers give the size of the result. So $AB$ is $2\times4$, $BC$ is $3\times2$, $CA$ is $4\times3$ and $DA$ is $2\times3$, while $BA$, $CB$, $AC$ and $AD$ are undefined. This already shows that the order of multiplication matters.

## Related workbook topics

- [Exercise 4: Noncommutativity](problem_04_solution.md)
- [Exercise 15: Associativity](problem_15_solution.md)
