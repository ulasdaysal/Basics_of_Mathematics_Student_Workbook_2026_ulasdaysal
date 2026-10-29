# Exercise 10. Detecting Dependence

## The question

Without a full determinant calculation, explain why

$$\det\begin{pmatrix}1&2&3\\2&4&6\\0&1&5\end{pmatrix}=0.$$

Identify a specific dependence between the rows and connect it with noninvertibility.

## Before calculating: what idea do we need?

The determinant is zero **exactly when** the rows are linearly dependent, i.e. one row can be built from the others. Before computing, it is worth scanning the rows for a simple relation, such as one row being a multiple of another.

Tool: adding a multiple of one row to another does **not** change the determinant (Exercise 5).

## 1. Spot the dependence

Compare the first two rows:

$$R_2=(2,4,6)=2\cdot(1,2,3)=2R_1.$$

So the rows satisfy the dependence

$$2R_1-R_2+0\cdot R_3=0.$$

## 2. Why this forces $\det=0$

Apply $R_2\leftarrow R_2-2R_1$, which does not change the determinant:

$$\begin{pmatrix}1&2&3\\0&0&0\\0&1&5\end{pmatrix}.$$

A matrix with a **zero row** has determinant $0$: every term of the determinant contains one entry from that row, so every term is zero. Hence

$$\det\begin{pmatrix}1&2&3\\2&4&6\\0&1&5\end{pmatrix}=0.$$

## 3. Connection with noninvertibility

- **Geometrically:** the three rows lie in one plane (only two independent directions), so the "box" they span is flat and has volume $0$.
- **Algebraically:** the matrix squashes $\mathbb{R}^3$ into a plane, so some non-zero vector is sent to $0$. Different inputs give the same output, so the map cannot be reversed.

We can find such a vector $x$ with $Ax=0$ from rows 1 and 3 (row 2 gives the same equation as row 1):

$$x+2y+3z=0,\quad y+5z=0\ \Longrightarrow\ y=-5z,\ x=7z.$$

Taking $z=1$: $x=(7,-5,1)^T$.

## 4. Quick verification

- $Ax$: row 1: $7-10+3=0$; row 2: $14-20+6=0$; row 3: $0-5+5=0$. So $Ax=0$ with $x\neq0$. ✓
- Sarrus' rule: $(1\cdot4\cdot5+2\cdot6\cdot0+3\cdot2\cdot1)-(3\cdot4\cdot0+1\cdot6\cdot1+2\cdot2\cdot5)=(20+0+6)-(0+6+20)=0$. ✓

## 5. A concrete example

Because $A\begin{pmatrix}7\\-5\\1\end{pmatrix}=0$, the system $Ax=b$ can never have a **unique** solution. If $x_0$ is a solution, then so is $x_0+t(7,-5,1)^T$ for every $t$.

## How I would explain this in class

> I notice that the second row is exactly twice the first one. Subtracting $2R_1$ from $R_2$ doesn't change the determinant but creates a zero row, so the determinant is $0$. The rows are dependent, the matrix flattens space into a plane, and for example $(7,-5,1)$ is sent to zero. So the matrix cannot be inverted.

## Related workbook topics

- [Exercise 1: Determinant of a 2×2 matrix](problem_01_solution.md)
- [Exercise 12: A parameter revealed by a row operation](problem_12_solution.md)
