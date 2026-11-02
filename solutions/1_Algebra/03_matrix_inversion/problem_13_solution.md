# Exercise 13. Undoing a Composite Transformation

## The question

The matrices

$$S=\begin{pmatrix}2&0\\0&1\end{pmatrix},\qquad H=\begin{pmatrix}1&1\\0&1\end{pmatrix}$$

describe nonuniform scaling and shear. For $T=HS$, find $T^{-1}$ in two ways:

1. first compute $T$, then its inverse,
2. use $(HS)^{-1}=S^{-1}H^{-1}$.

Compare the results. Additionally compute $H^{-1}S^{-1}$ and verify that the incorrect order gives a different matrix. Explain the rule: “when undoing a composition of operations, we undo them from the end.”

## Before calculating: what idea do we need?

When we apply the composite transformation $T=HS$ to a vector $v$, the matrix closest to $v$ acts **first**:

$$Tv=(HS)v=H(Sv).$$

So $S$ (horizontal scaling by $2$) happens first, and $H$ (horizontal shear) happens second.
To return from $Tv$ back to $v$, we must undo the **last** operation ($H$) **first** using $H^{-1}$, and then undo the **first** operation ($S$) **second** using $S^{-1}$:

$$T^{-1}=(HS)^{-1}=S^{-1}H^{-1}.$$

## 1. Method 1: First compute $T=HS$, then invert $T$

Multiply $H$ by $S$:

$$T=HS=\begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}2&0\\0&1\end{pmatrix}=\begin{pmatrix}2&1\\0&1\end{pmatrix}.$$

Now find $T^{-1}$ using the $2\times2$ formula. Since $\det T = 2\cdot1 - 1\cdot0 = 2$:

$$T^{-1}=\frac{1}{2}\begin{pmatrix}1&-1\\0&2\end{pmatrix}=\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\0&1\end{pmatrix}.$$

## 2. Method 2: Compute $S^{-1}H^{-1}$

First find the individual inverses:
- $S=\begin{pmatrix}2&0\\0&1\end{pmatrix}$ scales $x$ by $2$, so its inverse scales $x$ by $\frac{1}{2}$:

$$S^{-1}=\begin{pmatrix}\frac{1}{2}&0\\0&1\end{pmatrix}.$$

- $H=\begin{pmatrix}1&1\\0&1\end{pmatrix}$ shifts $x$ by $+y$, so its inverse shifts $x$ by $-y$:

$$H^{-1}=\begin{pmatrix}1&-1\\0&1\end{pmatrix}.$$

Now multiply $S^{-1}$ on the left of $H^{-1}$:

$$S^{-1}H^{-1}=\begin{pmatrix}\frac{1}{2}&0\\0&1\end{pmatrix}\begin{pmatrix}1&-1\\0&1\end{pmatrix}=\begin{pmatrix}\frac{1}{2}\cdot1+0\cdot0 & \frac{1}{2}\cdot(-1)+0\cdot1\\0\cdot1+1\cdot0 & 0\cdot(-1)+1\cdot1\end{pmatrix}=\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\0&1\end{pmatrix}.$$

Both methods give the exact same matrix!

## 3. Compute the incorrect order $H^{-1}S^{-1}$

Now multiply in the unreversed order $H^{-1}S^{-1}$:

$$H^{-1}S^{-1}=\begin{pmatrix}1&-1\\0&1\end{pmatrix}\begin{pmatrix}\frac{1}{2}&0\\0&1\end{pmatrix}=\begin{pmatrix}1\cdot\frac{1}{2}+(-1)\cdot0 & 1\cdot0+(-1)\cdot1\\0\cdot\frac{1}{2}+1\cdot0 & 0\cdot0+1\cdot1\end{pmatrix}=\begin{pmatrix}\frac{1}{2}&-1\\0&1\end{pmatrix}.$$

Compare the top-right entry: $H^{-1}S^{-1}$ has $-1$, whereas the true inverse $T^{-1}$ has $-\frac{1}{2}$. Thus

$$H^{-1}S^{-1}\neq T^{-1}.$$

## 4. Explaining “when undoing a composition, we undo from the end”

Follow a general point $\begin{pmatrix}x\\y\end{pmatrix}$ step by step under $T=HS$:

$$\begin{pmatrix}x\\y\end{pmatrix} \;\xrightarrow{\;\text{1st: scale } S\;}\; \begin{pmatrix}2x\\y\end{pmatrix} \;\xrightarrow{\;\text{2nd: shear } H\;}\; \begin{pmatrix}2x+y\\y\end{pmatrix}=\begin{pmatrix}x'\\y'\end{pmatrix}.$$

Look at the final output $x'=2x+y$ and $y'=y$:
- Because $+y$ was added **at the end** (after $x$ was doubled), to solve for $x$ we must **first** subtract $y'$ ($2x = x'-y'$, which is $H^{-1}$) and **then** divide the result by $2$ ($x = \frac{1}{2}(x'-y')$, which is $S^{-1}$).
- If we divided by $2$ first and subtracted $y'$ second ($H^{-1}S^{-1}$), we would get $\frac{1}{2}x'-y' = (x+\frac{1}{2}y)-y = x-\frac{1}{2}y\neq x$!

## Quick verification

Check that $T(S^{-1}H^{-1})=I$, whereas $T(H^{-1}S^{-1})\neq I$:

$$T(S^{-1}H^{-1})=\begin{pmatrix}2&1\\0&1\end{pmatrix}\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\0&1\end{pmatrix}=\begin{pmatrix}1&-1+1\\0&1\end{pmatrix}=\begin{pmatrix}1&0\\0&1\end{pmatrix}=I. \quad\checkmark$$

$$T(H^{-1}S^{-1})=\begin{pmatrix}2&1\\0&1\end{pmatrix}\begin{pmatrix}\frac{1}{2}&-1\\0&1\end{pmatrix}=\begin{pmatrix}1&-2+1\\0&1\end{pmatrix}=\begin{pmatrix}1&-1\\0&1\end{pmatrix}\neq I. \quad\checkmark$$

## A concrete example

Take the vector $v=\begin{pmatrix}3\\2\end{pmatrix}$:
1. $S$ scales it to $\begin{pmatrix}6\\2\end{pmatrix}$, and $H$ shears that to $Tv=\begin{pmatrix}8\\2\end{pmatrix}$.
2. Using the **correct order** $S^{-1}H^{-1}$: first $H^{-1}\begin{pmatrix}8\\2\end{pmatrix}=\begin{pmatrix}6\\2\end{pmatrix}$, then $S^{-1}\begin{pmatrix}6\\2\end{pmatrix}=\begin{pmatrix}3\\2\end{pmatrix}=v$.
3. Using the **wrong order** $H^{-1}S^{-1}$: first $S^{-1}\begin{pmatrix}8\\2\end{pmatrix}=\begin{pmatrix}4\\2\end{pmatrix}$, then $H^{-1}\begin{pmatrix}4\\2\end{pmatrix}=\begin{pmatrix}2\\2\end{pmatrix}\neq v$.

## How I would explain this in class

> In $T=HS$, $S$ acts first (doubling $x$ to $2x$) and $H$ acts second (adding $y$ to get $2x+y$). Just like unwrapping a gift or solving $2x+y=x'$ in algebra, you have to undo the outermost, last operation first: first subtract $y$ ($H^{-1}$), and only then divide by $2$ ($S^{-1}$). That is why $(HS)^{-1}=S^{-1}H^{-1}=\begin{pmatrix}1/2&-1/2\\0&1\end{pmatrix}$, while the unreversed product $H^{-1}S^{-1}=\begin{pmatrix}1/2&-1\\0&1\end{pmatrix}$ fails to cancel the shear properly.

## Related workbook topics

- [Exercise 7: Inverse of a Product](problem_07_solution.md)
- [Exercise 8: Inverse of a Transformation](problem_08_solution.md)
