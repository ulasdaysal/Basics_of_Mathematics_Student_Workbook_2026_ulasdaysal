# Exercise 8. A Square Root in a Function Limit

## The question

Compute

$$\lim_{x\to4}\frac{\sqrt{x}-2}{x-4}$$

by rationalizing the numerator. Compare the idea with Exercise 3 involving a sequence.

## Before calculating: what idea do we need?

Substituting $x=4$ into $\dfrac{\sqrt{x}-2}{x-4}$ gives $\dfrac{\sqrt{4}-2}{4-4}=\dfrac{0}{0}$. Just as in Exercise 7, a $\dfrac{0}{0}$ limit means a hidden common factor is vanishing in both the numerator and denominator.

Here the factor $x-4$ is hidden beneath the square root in $\sqrt{x}-2$. Multiplying the numerator and denominator by the **conjugate** $\sqrt{x}+2$ uses $(\sqrt{x}-2)(\sqrt{x}+2)=x-4$ to bring that factor into the open so it can cancel!

## 1. Multiply numerator and denominator by the conjugate

For $x\ge0$, $x\neq4$, multiply top and bottom by $\sqrt{x}+2$:

$$\frac{\sqrt{x}-2}{x-4} = \frac{(\sqrt{x}-2)(\sqrt{x}+2)}{(x-4)(\sqrt{x}+2)}.$$

## 2. Expand the numerator and cancel $(x-4)$

Using the difference-of-squares formula $(A-B)(A+B)=A^2-B^2$ in the numerator gives $(\sqrt{x})^2-2^2=x-4$. Therefore, for $x\neq4$:

$$\frac{(\sqrt{x}-2)(\sqrt{x}+2)}{(x-4)(\sqrt{x}+2)} = \frac{x-4}{(x-4)(\sqrt{x}+2)} = \frac{1}{\sqrt{x}+2}.$$

## 3. Evaluate the limit as $x\to4$

Now the denominator no longer vanishes at $x=4$, so we can substitute $x=4$ directly:

$$\lim_{x\to4}\frac{\sqrt{x}-2}{x-4} = \lim_{x\to4}\frac{1}{\sqrt{x}+2} = \frac{1}{\sqrt{4}+2} = \frac{1}{2+2} = \frac{1}{4}.$$

## 4. Comparison with Exercise 3

- **What is the same:** Both exercises use the exact same algebraic identity, $(\sqrt{A}-B)(\sqrt{A}+B)=A-B^2$, to remove a square root from a difference and turn a problematic subtraction into a benign sum in the other position.
- **What is different:** In Exercise 3 ($n\to\infty$), conjugation turned an $\infty-\infty$ form into an $\dfrac{\infty}{\infty}$ fraction where the dominant term $n$ was factored out. Here ($x\to4$), conjugation turns a $\dfrac{0}{0}$ form into a product where the vanishing factor $(x-4)$ cancels directly.

## Quick verification

We can also factor the denominator directly as a difference of squares since $x-4=(\sqrt{x})^2-2^2$:

$$\frac{\sqrt{x}-2}{x-4} = \frac{\sqrt{x}-2}{(\sqrt{x}-2)(\sqrt{x}+2)} = \frac{1}{\sqrt{x}+2}\xrightarrow[x\to4]{}\frac{1}{4}.$$

Both viewpoints yield $\dfrac{1}{4}=0.25$. ✓

## A concrete example

Notice that $\dfrac{\sqrt{x}-2}{x-4}$ is the slope of the secant line to $y=\sqrt{x}$ between $(4,2)$ and $(x,\sqrt{x})$:

- For $x=4.04$: $\sqrt{4.04}\approx 2.009975$, so $\dfrac{2.009975-2}{4.04-4} \approx \dfrac{0.009975}{0.04} \approx 0.2494$.
- For $x=3.96$: $\sqrt{3.96}\approx 1.989975$, so $\dfrac{1.989975-2}{3.96-4} \approx \dfrac{-0.010025}{-0.04} \approx 0.2506$.

As $x\to4$, the secant slope approaches the tangent slope $\dfrac{1}{4}=0.25$.

## How I would explain this in class

> Plugging in $x=4$ gives $0/0$. Just like in Exercise 3, whenever a square root sits in a difference, we multiply top and bottom by its conjugate, $\sqrt{x}+2$. The top simplifies to $(\sqrt{x})^2-2^2=x-4$, which cancels the $(x-4)$ on the bottom! That leaves $\dfrac{1}{\sqrt{x}+2}$, and plugging in $x=4$ gives $\dfrac{1}{2+2}=\dfrac{1}{4}$.

## Related workbook topics

- [Exercise 3: A square root and removing an indeterminate form](problem_03_solution.md)
- [Exercise 7: Limit at a point and canceling a factor](problem_07_solution.md)
