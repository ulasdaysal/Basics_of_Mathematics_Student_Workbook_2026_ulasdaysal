# Exercise 12. Symmetry, Sign, and Absolute Value

## The question

Compare

$$\int_{-2}^{2}x\,dx\qquad\text{and}\qquad\int_{-2}^{2}|x|\,dx.$$

Before calculating, predict the results from symmetry and a sketch, then carry out the calculation and explain the difference.

## Before calculating: what idea do we need?

On a **symmetric interval $[-a,a]$** centered at the origin, the symmetry of the integrand drastically simplifies integration:

- **Odd function** ($f(-x)=-f(x)$, symmetric about the origin): Every positive height at $+x$ is matched by an equal and opposite negative height at $-x$. The signed areas on $[-a,0]$ and $[0,a]$ cancel out completely:
  $$\int_{-a}^{a} f(x)\,dx = 0.$$
- **Even function** ($f(-x)=f(x)$, symmetric across the $y$-axis): The graph on $[-a,0]$ is a mirror image of the graph on $[0,a]$, so both halves contribute the exact same signed area:
  $$\int_{-a}^{a} f(x)\,dx = 2\int_{0}^{a} f(x)\,dx.$$

## 1. Predicting the results from symmetry and a sketch

1. **For $f(x)=x$ on $[-2,2]$:**
   The graph of $y=x$ is a straight line through the origin. On $[-2,0]$ it forms a right triangle of base $2$ and height $2$ **below** the $x$-axis (signed area $-2$), and on $[0,2]$ it forms an identical right triangle **above** the $x$-axis (signed area $+2$). Since $f(-x)=-x=-f(x)$ is **odd**, the two triangles cancel and we predict:
   $$\int_{-2}^{2}x\,dx = 0.$$

2. **For $g(x)=|x|$ on $[-2,2]$:**
   The absolute value reflects the negative left branch upward across the $x$-axis, creating a V-shaped graph that lies entirely above the $x$-axis. Both $[-2,0]$ and $[0,2]$ form right triangles of base $2$ and height $2$ **above** the $x$-axis, each of area $\frac{1}{2}(2)(2)=2$. Since $g(-x)=|-x|=|x|$ is **even**, the two areas add up and we predict:
   $$\int_{-2}^{2}|x|\,dx = 2+2 = 4.$$

## 2. Carrying out the analytical calculations

1. **First integral:** Using the antiderivative $F(x)=\dfrac{x^2}{2}$:
   $$\int_{-2}^{2}x\,dx = \left[\frac{x^2}{2}\right]_{-2}^{2} = \frac{2^2}{2}-\frac{(-2)^2}{2} = 2-2 = 0.$$

2. **Second integral:** Since $|x|=\begin{cases}-x,&x<0,\\x,&x\ge 0,\end{cases}$ we split the integral at the corner $x=0$:
   $$\int_{-2}^{2}|x|\,dx = \int_{-2}^{0}(-x)\,dx + \int_{0}^{2}x\,dx = \left[-\frac{x^2}{2}\right]_{-2}^{0} + \left[\frac{x^2}{2}\right]_{0}^{2} = \left(0-\left(-\frac{4}{2}\right)\right)+\left(\frac{4}{2}-0\right) = 2+2 = 4.$$

## 3. Explaining the difference

- $\int_{-2}^{2}x\,dx=0$ measures **net signed accumulation**: the negative half on $[-2,0]$ cancels the positive half on $[0,2]$.
- $\int_{-2}^{2}|x|\,dx=4$ measures the **total geometric area** between the line $y=x$ and the $x$-axis on $[-2,2]$, because $|x|$ makes all heights non-negative so that both halves contribute positively.

## Quick verification

Using the even-function property for $|x|$ directly avoids integrating on the negative interval altogether:

$$\int_{-2}^{2}|x|\,dx = 2\int_{0}^{2}x\,dx = 2\left[\frac{x^2}{2}\right]_{0}^{2} = 2(2-0) = 4.$$

Both the piecewise split and the even-symmetry shortcut give $4$, while the odd integral gives $0$. ✓

## A concrete example

Symmetry can save enormous work on much harder integrals. For example, consider:

$$\int_{-2}^{2} x^3\cos x\,dx.$$

Instead of doing integration by parts three times, we simply check symmetry: $(-x)^3\cos(-x)=-x^3\cos x$, which is an **odd** function on the symmetric interval $[-2,2]$. Therefore, the integral is immediately $0$ without a single line of antiderivative calculation!

## How I would explain this in class

> Before touching an antiderivative on $[-2,2]$, I look at symmetry. The function $y=x$ is odd: the triangle of area $2$ below the axis on $[-2,0]$ cancels the triangle of area $2$ above the axis on $[0,2]$, so $\int_{-2}^2 x\,dx = 0$. Taking the absolute value $|x|$ flips the negative triangle above the axis, turning the function into an even V-shape where both triangles have area $+2$, so $\int_{-2}^2 |x|\,dx = 2+2=4$.

## Related workbook topics

- [Exercise 9: Definite Integral and Geometric Area](problem_09_solution.md)
- [Exercise 14: A Piecewise-Defined Function](problem_14_solution.md)
