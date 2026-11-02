# Exercise 11. Derivative from the Definition

## The question

Using only

$$f'(x)=\lim_{h\to0}\frac{f(x+h)-f(x)}{h},$$

find the derivative of $f(x)=x^2$. Compare the result with the power rule and indicate where the limit is used in the calculation.

## Before calculating: what idea do we need?

For a nonzero step $h\neq0$, the **difference quotient**

$$\frac{f(x+h)-f(x)}{h}$$

is the **slope of the secant line** passing through the two points $(x,f(x))$ and $(x+h,f(x+h))$ on the graph. We cannot simply plug $h=0$ into this fraction at the start because that gives the indeterminate form $\dfrac{0}{0}$.

Instead, we must:
1. expand $f(x+h)-f(x)$ algebraically,
2. factor out $h$ in the numerator and cancel it with the $h$ in the denominator (valid because $h\neq0$ inside the limit),
3. take the limit as $h\to0$ once the division-by-zero obstacle has been removed.

## 1. Set up and expand the difference quotient

For $f(x)=x^2$, evaluate $f(x+h)$ by replacing $x$ with $(x+h)$:

$$f(x+h)=(x+h)^2=x^2+2xh+h^2.$$

Subtract $f(x)=x^2$:

$$f(x+h)-f(x)=(x^2+2xh+h^2)-x^2=2xh+h^2.$$

Divide by $h$ (for $h\neq0$):

$$\frac{f(x+h)-f(x)}{h}=\frac{2xh+h^2}{h}.$$

## 2. Factor and cancel $h$

Factor $h$ out of the numerator:

$$\frac{2xh+h^2}{h}=\frac{h(2x+h)}{h}=2x+h \qquad (h\neq0).$$

Geometrically, $2x+h$ is the exact slope of the secant line between $x$ and $x+h$.

## 3. Take the limit as $h\to0$ (and indicate where it is used)

Now apply the limit as $h\to0$:

$$f'(x)=\lim_{h\to0}\frac{f(x+h)-f(x)}{h}=\lim_{h\to0}(2x+h)=2x+0=2x.$$

**Where is the limit used?**
- In steps 1 and 2, we used the fact that the limit as $h\to0$ examines $h\neq0$, which **allowed us to cancel $\frac{h}{h}=1$**.
- In the final step $\lim_{h\to0}(2x+h)=2x$, the limit is used to **make the remaining increment $h$ vanish** (by continuity of the linear function $h\mapsto 2x+h$ at $h=0$).

## 4. Compare with the power rule

The power rule $\dfrac{d}{dx}(x^n)=nx^{n-1}$ for $n=2$ gives

$$\frac{d}{dx}(x^2)=2x^{2-1}=2x.$$

The results are identical! In fact, the power rule is not an arbitrary axiom — it is a shortcut obtained by performing this exact binomial expansion and limit once and for all for general $n$:

$$(x+h)^n-x^n=nx^{n-1}h+\binom{n}{2}x^{n-2}h^2+\dots+h^n \implies \lim_{h\to0}\frac{(x+h)^n-x^n}{h}=nx^{n-1}.$$

## Quick verification

Think of $f(x)=x^2$ as the area of a square of side length $x$. If we increase the side length from $x$ to $x+h$:

- The square gains **two rectangular strips** of dimensions $x\times h$ (total area $2xh$) and **one tiny corner square** of dimensions $h\times h$ (area $h^2$).
- Total area change: $\Delta A = 2xh+h^2$.
- Rate of change per unit of $h$: $\dfrac{\Delta A}{h}=2x+h$.
- As the strip thickness $h\to0$, the tiny corner contributes $h\to0$, leaving the two side edges of total length $2x$. ✓

## A concrete example

At $x=3$, our derivative is $f'(3)=2(3)=6$, and the secant slope formula is $2(3)+h=6+h$:

- For $h=0.1$: secant slope between $3$ and $3.1$ is $\dfrac{3.1^2-3^2}{0.1}=\dfrac{9.61-9}{0.1}=6.1=6+0.1$.
- For $h=0.01$: secant slope is $6.01$.
- For $h=0.001$: secant slope is $6.001$.
- In the limit as $h\to0$, the extra $+h$ disappears and we get the exact tangent slope $6$.

## How I would explain this in class

> To find the derivative of $x^2$ from the definition, we write the difference quotient $\frac{(x+h)^2-x^2}{h}$. Expanding $(x+h)^2=x^2+2xh+h^2$ cancels the $x^2$ terms and leaves $\frac{2xh+h^2}{h}$. Since $h\neq0$ before taking the limit, we cancel $h$ to get $2x+h$. Finally, taking the limit as $h\to0$ makes the $+h$ term disappear, giving $2x$, which matches the power rule $2x^{2-1}=2x$.

## Related workbook topics

- [Exercise 1: Derivative of a Polynomial and the Slope of a Tangent Line](problem_01_solution.md)
- [Exercise 15: The Difference Quotient as a Check of the Derivative](problem_15_solution.md)
