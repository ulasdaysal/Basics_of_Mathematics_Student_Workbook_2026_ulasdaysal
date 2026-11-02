# Exercise 14. Continuity and Differentiability of a Piecewise Function

## The question

Investigate the behavior at $x=0$ of

$$f(x)=\begin{cases}x^2,&x\ge0,\\ax,&x<0.\end{cases}$$

For which values of $a$ is the function continuous? For which values do the one-sided derivatives exist and agree? For which value of $a$ is the function differentiable? Explain why continuity alone is not sufficient.

## Before calculating: what idea do we need?

When a function is glued together from two formulas at a boundary point $x=0$, we must check two separate conditions in order:

1. **Continuity at $x=0$** (do the two pieces meet without a jump?):

$$\lim_{x\to0^-}f(x)=\lim_{x\to0^+}f(x)=f(0).$$

2. **Differentiability at $x=0$** (do the two pieces meet smoothly with the **same slope**, without a sharp corner?): the left-hand derivative $f'_-(0)$ and the right-hand derivative $f'_+(0)$ must both exist and be equal:

$$f'_-(0)=\lim_{h\to0^-}\frac{f(0+h)-f(0)}{h}=\lim_{h\to0^+}\frac{f(0+h)-f(0)}{h}=f'_+(0).$$

## 1. Continuity at $x=0$

Compute the value at $x=0$ and the two one-sided limits:

- Value at $x=0$ (using the $x\ge0$ branch): $f(0)=0^2=0$.
- Right-hand limit:

$$\lim_{x\to0^+}f(x)=\lim_{x\to0^+}x^2=0.$$

- Left-hand limit:

$$\lim_{x\to0^-}f(x)=\lim_{x\to0^-}(ax)=a\cdot0=0\quad\text{for every }a\in\mathbb{R}.$$

Since $\lim_{x\to0^-}f(x)=\lim_{x\to0^+}f(x)=f(0)=0$ regardless of $a$, the function $f$ is **continuous at $x=0$ for all real values $a\in\mathbb{R}$**.

## 2. One-sided derivatives at $x=0$

Now compute the right-hand and left-hand derivatives at $x=0$ using $f(0)=0$:

- **Right-hand derivative ($h\to0^+$, so $h>0$ and $f(h)=h^2$)**:

$$f'_+(0)=\lim_{h\to0^+}\frac{f(h)-f(0)}{h}=\lim_{h\to0^+}\frac{h^2-0}{h}=\lim_{h\to0^+}h=0.$$

- **Left-hand derivative ($h\to0^-$, so $h<0$ and $f(h)=ah$)**:

$$f'_-(0)=\lim_{h\to0^-}\frac{f(h)-f(0)}{h}=\lim_{h\to0^-}\frac{ah-0}{h}=\lim_{h\to0^-}a=a.$$

Thus:
- Both one-sided derivatives $f'_-(0)=a$ and $f'_+(0)=0$ **exist for every $a\in\mathbb{R}$**.
- They **agree** ($f'_-(0)=f'_+(0)$) if and only if

$$a=0.$$

## 3. Differentiability at $x=0$

A function is differentiable at $x=0$ if and only if its left-hand and right-hand derivatives exist and are equal. Therefore, $f$ is **differentiable at $x=0$ if and only if $a=0$** (in which case $f'(0)=0$).

## 4. Why continuity alone is not sufficient

- **Continuity** only requires the graphs of the two pieces $y=ax$ (for $x<0$) and $y=x^2$ (for $x\ge0$) to **connect at the same point** $(0,0)$. Since both $ax$ and $x^2$ equal $0$ at $x=0$, the pieces always touch at the origin.
- **Differentiability** requires a **unique tangent line** at $(0,0)$. The parabola $y=x^2$ arrives at the origin horizontally with slope $f'_+(0)=0$, whereas the line $y=ax$ arrives at the origin with slope $f'_-(0)=a$. If $a\neq0$, the graph has a **sharp corner (kink)** at $(0,0)$ where the slope abruptly jumps from $a$ to $0$, so no single tangent line exists.

## Quick verification

Check the formula for $f'(x)$ away from $x=0$:

$$f'(x)=\begin{cases}2x,&x>0,\\a,&x<0.\end{cases}$$

As $x\to0^+$, the slope $2x\to0$. As $x\to0^-$, the slope is constantly $a$. The slope transitions without a jump across $x=0$ if and only if $a=0$. ✓

## A concrete example

Compare $a=1$ and $a=0$:

- **If $a=1$**: $f(x)=\begin{cases}x^2,&x\ge0,\\x,&x<0.\end{cases}$ The graph is continuous at $(0,0)$, but coming from the left along the $45^\circ$ line $y=x$ the slope is $1$, and at $(0,0)$ it suddenly bends into the flat bottom of $y=x^2$ with slope $0$. This sharp corner at $(0,0)$ is not differentiable.
- **If $a=0$**: $f(x)=\begin{cases}x^2,&x\ge0,\\0,&x<0.\end{cases}$ Coming from the left along the horizontal line $y=0$ (slope $0$), the graph merges smoothly into the parabola $y=x^2$ (whose tangent at $x=0$ also has slope $0$), so $f'(0)=0$ exists.

## How I would explain this in class

> For any real number $a$, both $ax$ and $x^2$ approach $0$ as $x\to0$, so $f$ is continuous at $x=0$ for all $a\in\mathbb{R}$. However, from the right the parabola $x^2$ has slope $f'_+(0)=0$, while from the left the line $ax$ has slope $f'_-(0)=a$. The two one-sided derivatives agree only when $a=0$. Continuity only prevents a jump at $(0,0)$, whereas differentiability also prevents a sharp corner, which is why we need $a=0$.

## Related workbook topics

- [Exercise 11: Derivative from the Definition](problem_11_solution.md)
- [Exercise 15: The Difference Quotient as a Check of the Derivative](problem_15_solution.md)
