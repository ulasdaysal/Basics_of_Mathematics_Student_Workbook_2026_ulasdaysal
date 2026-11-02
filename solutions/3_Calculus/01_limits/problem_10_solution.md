# Exercise 10. Continuity of a Piecewise Function

## The question

Find $a$ so that

$$f(x)=\begin{cases}ax+1,&x<2,\\x^2-1,&x\ge2\end{cases}$$

is continuous at $x=2$. Explicitly compare the left-hand limit, right-hand limit, and function value.

## Before calculating: what idea do we need?

A function $f$ is **continuous at a point $x_0$** if three quantities exist and are equal:

1. The left-hand limit $\lim_{x\to x_0^-}f(x)$,
2. The right-hand limit $\lim_{x\to x_0^+}f(x)$,
3. The function value $f(x_0)$.

Geometrically, for a piecewise function that switches formulas at $x_0=2$, continuity means the left-hand branch ($y=ax+1$) and the right-hand branch ($y=x^2-1$) must meet at the exact same point $(2, f(2))$ without a jump.

## 1. Compute the function value at $x=2$

Because the condition $x\ge2$ includes $x=2$, we use the second formula to find $f(2)$:

$$f(2) = 2^2-1 = 4-1 = 3.$$

## 2. Compute the right-hand limit ($x\to2^+$)

When $x\to2^+$, we have $x>2$, so $f(x)=x^2-1$:

$$\lim_{x\to2^+}f(x) = \lim_{x\to2^+}(x^2-1) = 2^2-1 = 3.$$

Notice that the right-hand limit automatically agrees with $f(2)=3$.

## 3. Compute the left-hand limit ($x\to2^-$)

When $x\to2^-$, we have $x<2$, so $f(x)=ax+1$:

$$\lim_{x\to2^-}f(x) = \lim_{x\to2^-}(ax+1) = 2a+1.$$

## 4. Equate the three quantities to find $a$

For $f$ to be continuous at $x=2$, the left-hand limit, right-hand limit, and function value must all be equal:

$$\lim_{x\to2^-}f(x) = \lim_{x\to2^+}f(x) = f(2).$$

Substituting the expressions we found:

$$2a+1 = 3 \implies 2a = 2 \implies a = 1.$$

Thus, $f$ is continuous at $x=2$ if and only if **$a=1$**.

## Quick verification

Substitute $a=1$ back into $f(x)$:

$$f(x)=\begin{cases}x+1,&x<2,\\x^2-1,&x\ge2.\end{cases}$$

At the junction $x=2$:
- Left-hand limit: $\lim_{x\to2^-}(x+1) = 2+1 = 3$.
- Right-hand limit: $\lim_{x\to2^+}(x^2-1) = 4-1 = 3$.
- Function value: $f(2) = 4-1 = 3$.

All three equal $3$. ✓

## A concrete example

What happens if we choose a different parameter, say $a=2$?

- Then for $x<2$, $f(x)=2x+1\xrightarrow[x\to2^-]{} 5$, while for $x\ge2$, $f(x)=x^2-1\xrightarrow[x\to2^+]{} 3$.
- At $x=2$, the graph jumps abruptly from height $5$ down to height $3$ (a jump discontinuity of size $2$). Choosing $a=1$ tilts the line $y=ax+1$ so that its endpoint lands right on $(2,3)$, sealing the gap.

## How I would explain this in class

> Continuity at $x=2$ means no break in the graph at $x=2$, which requires three numbers to match: the left-hand limit, the right-hand limit, and $f(2)$. For $x\ge2$, the formula $x^2-1$ gives both the right-hand limit and $f(2)$ as $2^2-1=3$. For $x<2$, the formula $ax+1$ approaches $2a+1$ from the left. Setting $2a+1=3$ gives $a=1$.

## Related workbook topics

- [Exercise 7: Limit at a point and canceling a factor](problem_07_solution.md)
- [Exercise 9: One-sided limits and an asymptote](problem_09_solution.md)
