# Exercise 4. Gauss–Jordan

## The question

Find $A^{-1}$ using the Gauss–Jordan method for

$$A=\begin{pmatrix}1&2\\3&5\end{pmatrix}.$$

Show the augmented matrix $[A\mid I]$ after successive operations and explain why obtaining $I$ on the left gives the inverse on the right.

## Before calculating: what idea do we need?

The **Gauss–Jordan method** finds $A^{-1}$ by placing $A$ and the identity matrix $I$ side by side in an augmented matrix $[A\mid I]$ and applying elementary row operations until the left side becomes $I$:

$$[A\mid I] \;\xrightarrow{\text{row operations}}\; [I\mid A^{-1}].$$

Why does this work? Every elementary row operation is equivalent to multiplying on the left by an elementary matrix $E_k$. If a combined sequence of row operations $E=E_m\cdots E_2E_1$ turns $A$ into $I$, then $EA=I$, which means $E=A^{-1}$. Applying those exact same row operations to $I$ on the right computes $EI = A^{-1}I = A^{-1}$.

## 1. Set up the augmented matrix $[A\mid I]$

Write $A$ on the left and the $2\times2$ identity matrix $I$ on the right:

$$[A\mid I]=\left(\begin{array}{cc|cc}1&2&1&0\\3&5&0&1\end{array}\right).$$

## 2. Eliminate the entry below the first pivot

The top-left pivot is already $1$. To create a $0$ below it in the first column, replace Row 2 with $R_2 - 3R_1$:

$$R_2 \leftarrow R_2 - 3R_1:\qquad \left(\begin{array}{cc|cc}1&2&1&0\\3-3(1)&5-3(2)&0-3(1)&1-3(0)\end{array}\right)=\left(\begin{array}{cc|cc}1&2&1&0\\0&-1&-3&1\end{array}\right).$$

## 3. Make the second pivot equal to $1$

Multiply Row 2 by $-1$ so the second pivot becomes $+1$:

$$R_2 \leftarrow -R_2:\qquad \left(\begin{array}{cc|cc}1&2&1&0\\0&1&3&-1\end{array}\right).$$

## 4. Eliminate the entry above the second pivot

To create a $0$ above the second pivot, replace Row 1 with $R_1 - 2R_2$:

$$R_1 \leftarrow R_1 - 2R_2:\qquad \left(\begin{array}{cc|cc}1&2-2(1)&1-2(3)&0-2(-1)\\0&1&3&-1\end{array}\right)=\left(\begin{array}{cc|cc}1&0&-5&2\\0&1&3&-1\end{array}\right).$$

Now the left block is $I$, so the right block is $A^{-1}$:

$$A^{-1}=\begin{pmatrix}-5&2\\3&-1\end{pmatrix}.$$

## 5. Why obtaining $I$ on the left gives $A^{-1}$ on the right

We can view $[A\mid I]$ as solving two linear systems simultaneously:

$$Ax^{(1)}=\begin{pmatrix}1\\0\end{pmatrix}\quad\text{and}\quad Ax^{(2)}=\begin{pmatrix}0\\1\end{pmatrix},$$

which together form the matrix equation $AX=I$. Row operations do not change the solution set of a linear system. Once the left side reaches $I$, the equation has become $IX=B$, or $X=B$. Thus the right side $B$ satisfies $AB=I$, meaning $B=A^{-1}$.

## Quick verification

Multiply $A$ by our result $A^{-1}$:

$$AA^{-1}=\begin{pmatrix}1&2\\3&5\end{pmatrix}\begin{pmatrix}-5&2\\3&-1\end{pmatrix}=\begin{pmatrix}-5+6 & 2-2\\-15+15 & 6-5\end{pmatrix}=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I.$$

Also, the $2\times2$ formula gives $\det A = 1(5)-2(3)=-1$, so $A^{-1}=\frac{1}{-1}\begin{pmatrix}5&-2\\-3&1\end{pmatrix}=\begin{pmatrix}-5&2\\3&-1\end{pmatrix}$. Both checks agree! ✓

## A concrete example

Notice how the columns of $A^{-1}$ solve $Ax=e_1$ and $Ax=e_2$:
- Column 1 of $A^{-1}$ is $\begin{pmatrix}-5\\3\end{pmatrix}$, and $\begin{pmatrix}1&2\\3&5\end{pmatrix}\begin{pmatrix}-5\\3\end{pmatrix}=\begin{pmatrix}-5+6\\-15+15\end{pmatrix}=\begin{pmatrix}1\\0\end{pmatrix}=e_1$.
- Column 2 of $A^{-1}$ is $\begin{pmatrix}2\\-1\end{pmatrix}$, and $\begin{pmatrix}1&2\\3&5\end{pmatrix}\begin{pmatrix}2\\-1\end{pmatrix}=\begin{pmatrix}2-2\\6-5\end{pmatrix}=\begin{pmatrix}0\\1\end{pmatrix}=e_2$.

Gauss–Jordan simply solved both systems at once.

## How I would explain this in class

> In the Gauss–Jordan method, we set up $[A\mid I]$ and use row operations to turn $A$ into the identity matrix $I$. Here we do $R_2\leftarrow R_2-3R_1$, then $R_2\leftarrow -R_2$, and finally $R_1\leftarrow R_1-2R_2$. Because row operations act like multiplying on the left by a matrix $E$, turning the left side from $A$ into $I$ means $EA=I$, so $E=A^{-1}$. Since the right side started as $I$, it gets multiplied by $E$ too and becomes $EI=A^{-1}$.

## Related workbook topics

- [Exercise 2: Formula for a 2×2 Matrix](problem_02_solution.md)
- [Exercise 5: A 3×3 Matrix](problem_05_solution.md)
