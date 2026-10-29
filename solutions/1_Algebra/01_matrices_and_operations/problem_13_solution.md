# Exercise 13. A Recurrence Written in Matrix Form

## The question

Let

$$F=\begin{pmatrix}1&1\\1&0\end{pmatrix}.$$

Compute $F^2$, $F^3$, $F^4$, $F^5$ and compare the entries with the sequence

$$0,1,1,2,3,5,8,\ldots$$

Then compute $F\begin{pmatrix}a\\b\end{pmatrix}$ and explain how this performs one step of the recurrence.

## Before calculating: what idea do we need?

The sequence above is the **Fibonacci sequence**:

$$F_0=0,\quad F_1=1,\quad F_{n+1}=F_n+F_{n-1}.$$

Each new term needs the **two** previous terms. A single number cannot store that information, but a **vector** of two numbers can. If a matrix turns $(F_n,F_{n-1})$ into $(F_{n+1},F_n)$, then repeating the step is just taking powers of that matrix.

## 1. Compute the powers

$$F^2=\begin{pmatrix}1&1\\1&0\end{pmatrix}\begin{pmatrix}1&1\\1&0\end{pmatrix}=\begin{pmatrix}2&1\\1&1\end{pmatrix},$$

$$F^3=F^2F=\begin{pmatrix}2&1\\1&1\end{pmatrix}\begin{pmatrix}1&1\\1&0\end{pmatrix}=\begin{pmatrix}3&2\\2&1\end{pmatrix},$$

$$F^4=F^3F=\begin{pmatrix}3&2\\2&1\end{pmatrix}\begin{pmatrix}1&1\\1&0\end{pmatrix}=\begin{pmatrix}5&3\\3&2\end{pmatrix},$$

$$F^5=F^4F=\begin{pmatrix}5&3\\3&2\end{pmatrix}\begin{pmatrix}1&1\\1&0\end{pmatrix}=\begin{pmatrix}8&5\\5&3\end{pmatrix}.$$

## 2. Relationship with the sequence

| $n$ | $F^n$ | $F_{n+1}$ | $F_n$ | $F_{n-1}$ |
|---|---|---|---|---|
| 1 | $\begin{pmatrix}1&1\\1&0\end{pmatrix}$ | 1 | 1 | 0 |
| 2 | $\begin{pmatrix}2&1\\1&1\end{pmatrix}$ | 2 | 1 | 1 |
| 3 | $\begin{pmatrix}3&2\\2&1\end{pmatrix}$ | 3 | 2 | 1 |
| 4 | $\begin{pmatrix}5&3\\3&2\end{pmatrix}$ | 5 | 3 | 2 |
| 5 | $\begin{pmatrix}8&5\\5&3\end{pmatrix}$ | 8 | 5 | 3 |

The entries are always three consecutive Fibonacci numbers:

$$F^n=\begin{pmatrix}F_{n+1}&F_n\\F_n&F_{n-1}\end{pmatrix}.$$

## 3. One recurrence step

$$F\begin{pmatrix}a\\b\end{pmatrix}=\begin{pmatrix}1\cdot a+1\cdot b\\1\cdot a+0\cdot b\end{pmatrix}=\begin{pmatrix}a+b\\a\end{pmatrix}.$$

- The **first row** $(1,1)$ creates the **sum** of the two terms: the new Fibonacci number.
- The **second row** $(1,0)$ **keeps** the previous top term $a$, so it is available for the next step.

With $a=F_n$, $b=F_{n-1}$:

$$F\begin{pmatrix}F_n\\F_{n-1}\end{pmatrix}=\begin{pmatrix}F_{n+1}\\F_n\end{pmatrix}.$$

Starting from $\begin{pmatrix}F_1\\F_0\end{pmatrix}=\begin{pmatrix}1\\0\end{pmatrix}$ and applying $F$ repeatedly:

$$F^n\begin{pmatrix}1\\0\end{pmatrix}=\begin{pmatrix}F_{n+1}\\F_n\end{pmatrix},$$

which is the first column of $F^n$. That explains the pattern in the table.

## 4. Why the pattern holds for all $n$ (induction)

Base: $F^1=\begin{pmatrix}F_2&F_1\\F_1&F_0\end{pmatrix}=\begin{pmatrix}1&1\\1&0\end{pmatrix}$. ✓

Step: if $F^n=\begin{pmatrix}F_{n+1}&F_n\\F_n&F_{n-1}\end{pmatrix}$, then

$$F^{n+1}=F^nF=\begin{pmatrix}F_{n+1}+F_n&F_{n+1}\\F_n+F_{n-1}&F_n\end{pmatrix}=\begin{pmatrix}F_{n+2}&F_{n+1}\\F_{n+1}&F_n\end{pmatrix}.\ ✓$$

## 5. Quick verification

Determinant: $\det F=-1$, so $\det F^n=(-1)^n$. For $n=5$: $8\cdot3-5\cdot5=24-25=-1=(-1)^5$. ✓ (This is Cassini's identity $F_{n+1}F_{n-1}-F_n^2=(-1)^n$.)

## 6. A concrete example

From $\begin{pmatrix}5\\3\end{pmatrix}$, one step gives $\begin{pmatrix}8\\5\end{pmatrix}$, and the next gives $\begin{pmatrix}13\\8\end{pmatrix}$. So we can predict

$$F^6=\begin{pmatrix}13&8\\8&5\end{pmatrix}.$$

## How I would explain this in class

> The powers of $F$ contain Fibonacci numbers: $F^5=\begin{pmatrix}8&5\\5&3\end{pmatrix}$, and in general $F^n=\begin{pmatrix}F_{n+1}&F_n\\F_n&F_{n-1}\end{pmatrix}$. The reason is that $F(a,b)=(a+b,a)$: the first row makes the new term as a sum, and the second row remembers the old one. So one multiplication by $F$ is one step of the recurrence, and $F^n$ is $n$ steps.

## Related workbook topics

- [Exercise 12: Formula for a matrix power](problem_12_solution.md)
- [Exercise 5: Matrix times vector](problem_05_solution.md)
