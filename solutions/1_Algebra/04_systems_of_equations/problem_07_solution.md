# Exercise 7. Choosing a Method Deliberately

## The question

Do not solve all of the following systems completely. For each situation, choose the method that best uses its structure and justify your choice:

1. one system with a triangular coefficient matrix
   $$\begin{cases}2x-y=3,\\4y=8;\end{cases}$$
2. three systems $Ax=b_i$ with the same invertible matrix $A$, when $A^{-1}$ is already known;
3. one $3\times3$ system for which the inverse matrix is not given and the goal is only to find one solution vector.

For case 1, carry out the chosen method completely. For cases 2 and 3, describe the plan and indicate which part of the computation would be reusable or unnecessary. Do not judge a method by its name alone — refer to the number of right-hand sides and the structure of the matrix.

## Before calculating: what idea do we need?

Different algebraic methods solve $Ax=b$, but their computational effort depends heavily on **what structure we already have** and **how many right-hand sides $b_i$ we need to process**:
- **Back-substitution** works immediately when the matrix is already triangular—doing elimination or finding an inverse would repeat work that is already finished.
- **Multiplying by $A^{-1}$** ($x_i = A^{-1}b_i$) is fast *if $A^{-1}$ has already been computed*, because each new right-hand side only costs one matrix-vector multiplication.
- **Gaussian elimination** on $[A\mid b]$ is the most efficient general method for a single system when $A^{-1}$ is not given, because computing all of $A^{-1}$ is equivalent to solving three separate systems when we only care about one.

## 1. Case 1: Triangular coefficient matrix

The system is

$$\begin{cases} 2x - y = 3, \\ 4y = 8. \end{cases}$$

- **Chosen method:** **Direct back-substitution** (from bottom to top).
- **Justification:** The coefficient matrix $\begin{pmatrix} 2 & -1 \\ 0 & 4 \end{pmatrix}$ is already in upper triangular (row echelon) form—the forward elimination phase is already complete! Computing $A^{-1}$ or applying row operations would be completely unnecessary.
- **Complete calculation:**
  1. From the second equation:
     $$4y = 8 \implies y = 2.$$
  2. Substitute $y = 2$ into the first equation:
     $$2x - 2 = 3 \implies 2x = 5 \implies x = \frac{5}{2}.$$
  So the unique solution is $(x, y) = \left(\frac{5}{2}, 2\right)$.

## 2. Case 2: Three systems $Ax=b_i$ when $A^{-1}$ is already known

- **Chosen method:** **Matrix multiplication by the known inverse**, computing $x_i = A^{-1}b_i$ for $i = 1, 2, 3$.
- **Justification and plan:** Since $A^{-1}$ is already provided, we do not need to perform Gaussian elimination three times. For each right-hand side $b_i$, we simply multiply the given matrix $A^{-1}$ by the column vector $b_i$:
  $$x_1 = A^{-1}b_1, \qquad x_2 = A^{-1}b_2, \qquad x_3 = A^{-1}b_3.$$
- **What is reusable or unnecessary:** The inverse matrix $A^{-1}$ itself is the **reusable** object—it encodes the inverted structure of $A$ once and for all, so we reuse it across all three right-hand sides $b_1, b_2, b_3$. Running row reduction on $A$ from scratch for each system would be **unnecessary** duplicate work.

## 3. Case 3: One $3\times 3$ system without $A^{-1}$ given

- **Chosen method:** **Gaussian elimination with back-substitution** on the single augmented matrix $[A\mid b]$.
- **Justification and plan:** We only have **one** right-hand side $b$, and $A^{-1}$ is not known. Our plan is to use elementary row operations to reduce $[A\mid b]$ to upper triangular form $[U\mid c]$, and then solve for $x_3$, $x_2$, and $x_1$ by back-substitution.
- **What is reusable or unnecessary:** Computing the full inverse matrix $A^{-1}$ (or using Cramer's rule with four $3\times 3$ determinants) is **unnecessary**. Finding $A^{-1}$ by Gauss–Jordan elimination on $[A\mid I_3]$ requires reducing to reduced row echelon form with **three** right-hand side columns $(e_1, e_2, e_3)$, which takes roughly three times as much work on the right-hand side as solving for the single vector $b$.

## Quick verification

Let us verify the solution $(x, y) = \left(\frac{5}{2}, 2\right)$ for Case 1 in the original system:
- First equation: $2\left(\frac{5}{2}\right) - 2 = 5 - 2 = 3$. ✓
- Second equation: $4(2) = 8$. ✓

Both equations are satisfied.

## A concrete example

To see the work difference between Cases 2 and 3 concretely for a $3\times 3$ matrix:
- Multiplying a known $3\times 3$ matrix $A^{-1}$ by one vector $b_i$ takes just $3 \times 3 = 9$ multiplications and $6$ additions. Doing this for three vectors $b_1, b_2, b_3$ takes $27$ multiplications total.
- By contrast, finding $A^{-1}$ from scratch first (when you only have a single vector $b$) forces you to solve $Ax_1 = (1,0,0)^T$, $Ax_2 = (0,1,0)^T$, and $Ax_3 = (0,0,1)^T$ even though you never needed those three columns separately!

## How I would explain this in class

> Always look at what work is already done and how many right-hand sides you have. In Case 1, the matrix is already a staircase, so just read $y=2$ from the bottom and plug it into the top to get $x=5/2$. In Case 2, someone already did the hard work of finding $A^{-1}$, so we reuse $A^{-1}$ and just multiply $A^{-1}b_1, A^{-1}b_2, A^{-1}b_3$. In Case 3, we have only one right-hand side and no inverse, so ordinary Gaussian elimination on $[A\mid b]$ goes straight to the answer without wasting time inverting the whole matrix.

## Related workbook topics

- [Exercise 2: Gaussian Elimination — One Solution](problem_02_solution.md)
- [Exercise 8: Two Systems with the Same Coefficient Matrix](problem_08_solution.md)
