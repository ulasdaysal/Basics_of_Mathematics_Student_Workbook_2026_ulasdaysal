# Exercise 7. Inverse of a Product

## The question

For

$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}2&0\\0&3\end{pmatrix}$$

compute $(AB)^{-1}$ and $B^{-1}A^{-1}$. Check that the results are the same and explain the meaning of the reversed order.

## Before calculating: what idea do we need?

When two invertible matrices $A$ and $B$ are multiplied, their product $AB$ is also invertible, and its inverse reverses the order of the factors:

$$(AB)^{-1}=B^{-1}A^{-1}.$$

Algebraically, this happens because $B^{-1}$ and $A^{-1}$ meet in the middle and cancel one pair at a time:

$$(AB)(B^{-1}A^{-1}) = A(BB^{-1})A^{-1} = AIA^{-1} = AA^{-1} = I.$$

## 1. First path: compute $AB$ and then $(AB)^{-1}$

Multiply $A$ and $B$:

$$AB=\begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}2&0\\0&3\end{pmatrix}=\begin{pmatrix}2&3\\0&3\end{pmatrix}.$$

Now find the inverse of $AB$ using the $2\times2$ formula. Its determinant is

$$\det(AB)=2\cdot3-3\cdot0=6.$$

Therefore,

$$(AB)^{-1}=\frac{1}{6}\begin{pmatrix}3&-3\\0&2\end{pmatrix}=\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\0&\frac{1}{3}\end{pmatrix}.$$

## 2. Second path: compute $A^{-1}$, $B^{-1}$, and then $B^{-1}A^{-1}$

Find each inverse separately using the $2\times2$ formula:
- For $A=\begin{pmatrix}1&1\\0&1\end{pmatrix}$, $\det A=1$, so

$$A^{-1}=\begin{pmatrix}1&-1\\0&1\end{pmatrix}.$$

- For the diagonal matrix $B=\begin{pmatrix}2&0\\0&3\end{pmatrix}$, $\det B=6$, so

$$B^{-1}=\begin{pmatrix}\frac{1}{2}&0\\0&\frac{1}{3}\end{pmatrix}.$$

Now multiply $B^{-1}$ by $A^{-1}$ in that order:

$$B^{-1}A^{-1}=\begin{pmatrix}\frac{1}{2}&0\\0&\frac{1}{3}\end{pmatrix}\begin{pmatrix}1&-1\\0&1\end{pmatrix}=\begin{pmatrix}\frac{1}{2}\cdot1+0\cdot0 & \frac{1}{2}\cdot(-1)+0\cdot1\\0\cdot1+\frac{1}{3}\cdot0 & 0\cdot(-1)+\frac{1}{3}\cdot1\end{pmatrix}=\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\0&\frac{1}{3}\end{pmatrix}.$$

## 3. Compare the results and explain the reversed order

Both paths produce the exact same matrix:

$$(AB)^{-1}=B^{-1}A^{-1}=\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\0&\frac{1}{3}\end{pmatrix}.$$

Why must the order be reversed? Think of how $(AB)$ acts on a vector $x$:

$$x \;\xrightarrow{\;\text{first } B\;}\; Bx \;\xrightarrow{\;\text{second } A\;}\; A(Bx).$$

Because $A$ was applied **last**, to undo the combined process we must undo $A$ **first** (by applying $A^{-1}$) and then undo $B$ **second** (by applying $B^{-1}$):

$$A(Bx) \;\xrightarrow{\;\text{first } A^{-1}\;}\; Bx \;\xrightarrow{\;\text{second } B^{-1}\;}\; x.$$

Since matrices act from the left, "first $A^{-1}$, then $B^{-1}$" is written as the product $B^{-1}A^{-1}$.

## Quick verification

Multiply $(AB)$ directly by $B^{-1}A^{-1}$:

$$\begin{pmatrix}2&3\\0&3\end{pmatrix}\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\0&\frac{1}{3}\end{pmatrix}=\begin{pmatrix}2\cdot\frac{1}{2}+3\cdot0 & 2\cdot(-\frac{1}{2})+3\cdot\frac{1}{3}\\0\cdot\frac{1}{2}+3\cdot0 & 0\cdot(-\frac{1}{2})+3\cdot\frac{1}{3}\end{pmatrix}=\begin{pmatrix}1&-1+1\\0&1\end{pmatrix}=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I.$$

Also note that multiplying in the wrong order gives $A^{-1}B^{-1}=\begin{pmatrix}1&-1\\0&1\end{pmatrix}\begin{pmatrix}\frac{1}{2}&0\\0&\frac{1}{3}\end{pmatrix}=\begin{pmatrix}\frac{1}{2}&-\frac{1}{3}\\0&\frac{1}{3}\end{pmatrix}\neq(AB)^{-1}$. ✓

## A concrete example

This is often called the **socks-and-shoes rule**:
- In the morning, you put on your socks ($B$) first, and then your shoes ($A$) second.
- At night, to undo the process, you cannot take off your socks first! You must take off your shoes ($A^{-1}$) first, and then take off your socks ($B^{-1}$) second.

Let us test this on the vector $v=\begin{pmatrix}1\\1\end{pmatrix}$:
1. Apply $B$: $Bv=\begin{pmatrix}2\\3\end{pmatrix}$.
2. Apply $A$: $A(Bv)=\begin{pmatrix}5\\3\end{pmatrix}$.
3. Undo $A$ first: $A^{-1}\begin{pmatrix}5\\3\end{pmatrix}=\begin{pmatrix}5-3\\3\end{pmatrix}=\begin{pmatrix}2\\3\end{pmatrix}$.
4. Undo $B$ second: $B^{-1}\begin{pmatrix}2\\3\end{pmatrix}=\begin{pmatrix}1\\1\end{pmatrix}=v$.

## How I would explain this in class

> Whether we multiply $AB$ first and invert it, or invert $A$ and $B$ separately and compute $B^{-1}A^{-1}$, we get the exact same matrix $\begin{pmatrix}1/2&-1/2\\0&1/3\end{pmatrix}$. The order flips because in the product $(AB)x$, $B$ acts on $x$ first and $A$ acts second. To reverse a two-step process, you always have to undo the last step ($A$) first and the first step ($B$) last, which means multiplying by $A^{-1}$ and then $B^{-1}$, written $B^{-1}A^{-1}$.

## Related workbook topics

- [Exercise 12: Finding Inverses Without Starting from Scratch](problem_12_solution.md)
- [Exercise 13: Undoing a Composite Transformation](problem_13_solution.md)
