# Exercise 9. Cross Product as a Perpendicular Direction

## The question

For $u=(1,2,0)$ and $v=(0,1,3)$ compute $u\times v$. Use dot products to check perpendicularity to both vectors, compute $v\times u$, and compare the results.

## Before calculating: what idea do we need?

In $\mathbb R^3$, the **cross product** of $u=(u_1,u_2,u_3)$ and $v=(v_1,v_2,v_3)$ is a **vector** given by the symbolic determinant

$$u\times v = \begin{vmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\u_1&u_2&u_3\\v_1&v_2&v_3\end{vmatrix} = \left(u_2v_3-u_3v_2,\; u_3v_1-u_1v_3,\; u_1v_2-u_2v_1\right).$$

Key geometric properties of $u\times v$:

1. **Perpendicularity:** $u\times v$ is orthogonal to both $u$ and $v$ (and therefore perpendicular to the plane spanned by $u$ and $v$).
2. **Anticommutativity (orientation):** Swapping the order of the two vectors reverses the orientation of the cross product (by the right-hand rule):
   $$v\times u = -(u\times v).$$

## 1. Computing $u\times v$

For $u=(1,2,0)$ and $v=(0,1,3)$:

$$u\times v = \begin{vmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\1&2&0\\0&1&3\end{vmatrix} = \left(\begin{vmatrix}2&0\\1&3\end{vmatrix},\; -\begin{vmatrix}1&0\\0&3\end{vmatrix},\; \begin{vmatrix}1&2\\0&1\end{vmatrix}\right).$$

Evaluating the three $2\times 2$ determinants:

- First component: $2\cdot 3 - 0\cdot 1 = 6$,
- Second component: $-(1\cdot 3 - 0\cdot 0) = -3$,
- Third component: $1\cdot 1 - 2\cdot 0 = 1$.

Therefore,

$$u\times v = (6,-3,1).$$

## 2. Checking perpendicularity using dot products

We take the dot product of $u\times v = (6,-3,1)$ with $u=(1,2,0)$ and with $v=(0,1,3)$:

$$(u\times v)\cdot u = (6,-3,1)\cdot(1,2,0) = 6\cdot 1 + (-3)\cdot 2 + 1\cdot 0 = 6 - 6 + 0 = 0,$$

$$(u\times v)\cdot v = (6,-3,1)\cdot(0,1,3) = 6\cdot 0 + (-3)\cdot 1 + 1\cdot 3 = 0 - 3 + 3 = 0.$$

Since both dot products are $0$, $u\times v$ is perpendicular to both $u$ and $v$.

## 3. Computing $v\times u$

Now we put $v=(0,1,3)$ in the second row and $u=(1,2,0)$ in the third row:

$$v\times u = \begin{vmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\0&1&3\\1&2&0\end{vmatrix} = \left(\begin{vmatrix}1&3\\2&0\end{vmatrix},\; -\begin{vmatrix}0&3\\1&0\end{vmatrix},\; \begin{vmatrix}0&1\\1&2\end{vmatrix}\right).$$

Evaluating each component:

- First component: $1\cdot 0 - 3\cdot 2 = -6$,
- Second component: $-(0\cdot 0 - 3\cdot 1) = -(-3) = 3$,
- Third component: $0\cdot 2 - 1\cdot 1 = -1$.

Thus,

$$v\times u = (-6,3,-1).$$

## 4. Comparing $u\times v$ and $v\times u$

Comparing the two results:

$$u\times v = (6,-3,1),\qquad v\times u = (-6,3,-1) = -(u\times v).$$

- **Same line and same length:** Both vectors lie on the exact same line perpendicular to the plane of $u$ and $v$, and both have length $\sqrt{6^2+(-3)^2+1^2}=\sqrt{46}$.
- **Opposite orientation:** They point in **opposite directions**. Geometrically, curling the fingers of your right hand from $u$ to $v$ makes your thumb point along $u\times v=(6,-3,1)$, whereas curling them from $v$ to $u$ flips your thumb to point along $v\times u=(-6,3,-1)$. Algebraically, swapping two rows of a determinant multiplies the determinant by $-1$.

## Quick verification

Let us verify Lagrange's identity $\|u\times v\|^2 = \|u\|^2\|v\|^2 - (u\cdot v)^2$:

- Left side: $\|u\times v\|^2 = 6^2 + (-3)^2 + 1^2 = 36 + 9 + 1 = 46$.
- Right side: $\|u\|^2 = 1^2+2^2+0^2 = 5$, $\|v\|^2 = 0^2+1^2+3^2 = 10$, and $u\cdot v = 1(0)+2(1)+0(3) = 2$, so
  $$\|u\|^2\|v\|^2 - (u\cdot v)^2 = 5\cdot 10 - 2^2 = 50 - 4 = 46.\quad \checkmark$$

## A concrete example

Think of turning a right-handed screw with a wrench:

- If the wrench handle lies along $u$ and you push in the direction $v$, the torque vector is $u\times v$, which drives the screw **outward** along $(6,-3,1)$.
- If the handle is along $v$ and you push in the direction $u$, the rotation reverses and the screw moves **inward** along $v\times u = (-6,3,-1)$.

## How I would explain this in class

> Using the $2\times 2$ minors, $u\times v = (6,-3,1)$. We immediately verify our arithmetic by checking $(6,-3,1)\cdot(1,2,0)=6-6=0$ and $(6,-3,1)\cdot(0,1,3)=-3+3=0$, confirming that $u\times v$ is perpendicular to both $u$ and $v$. When we compute $v\times u$, we get $(-6,3,-1) = -(u\times v)$: swapping the two vectors keeps the same perpendicular line and length, but flips the orientation to the opposite side of the plane.

## Related workbook topics

- [Exercise 10: Triangle area from vectors](problem_10_solution.md)
- [Exercise 12: A normal vector to a plane](problem_12_solution.md)
