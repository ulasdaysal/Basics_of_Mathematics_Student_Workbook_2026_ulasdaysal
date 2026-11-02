# Exercise 10. The Tangent Line as an Application of the Derivative

## The question

For

$$f(x)=x^2-3x+1$$

find the equation of the tangent line at the point with $x=2$. Give the point of tangency, the value $f'(2)$, the equation of the line, and verify that the point lies on the obtained tangent line.

## Before calculating: what idea do we need?

To write the equation of a line, we need **a point** $(x_0,y_0)$ on the line and **its slope** $m$. For the tangent line to the graph $y=f(x)$ at $x_0$:

1. **Point of tangency**: $(x_0,y_0)=(x_0,f(x_0))$ — obtained by plugging $x_0$ into the **original function** $f$.
2. **Slope of the tangent line**: $m=f'(x_0)$ — obtained by plugging $x_0$ into the **derivative** $f'$.
3. **Point-slope equation of the tangent line**:

$$y-f(x_0)=f'(x_0)(x-x_0) \quad\Longleftrightarrow\quad y=f(x_0)+f'(x_0)(x-x_0).$$

*(A common mistake is plugging $f'(x)$ instead of the constant number $f'(x_0)$ into the line equation — the slope $m=f'(2)$ must be a constant number so that the equation represents a straight line.)*

## 1. Find the point of tangency

Evaluate the function $f(x)=x^2-3x+1$ at $x_0=2$:

$$f(2)=2^2-3(2)+1=4-6+1=-1.$$

So the point of tangency is

$$P=(2,-1).$$

## 2. Compute the derivative and the slope $f'(2)$

Differentiate $f(x)=x^2-3x+1$ using the power rule:

$$f'(x)=2x-3.$$

Evaluate $f'(x)$ at $x_0=2$ to get the slope of the tangent line:

$$m=f'(2)=2(2)-3=4-3=1.$$

## 3. Write the equation of the tangent line

Substitute $(x_0,y_0)=(2,-1)$ and $m=1$ into the tangent line formula $y-y_0=m(x-x_0)$:

$$y-(-1)=1\cdot(x-2)$$

$$y+1=x-2$$

$$y=x-3.$$

## 4. Verify that the point of tangency lies on the tangent line

Substitute $x=2$ into the tangent line equation $y=x-3$:

$$y(2)=2-3=-1=f(2).\quad\checkmark$$

Thus the point $P=(2,-1)$ lies on the line $y=x-3$.

## Quick verification

For a parabola, a line is tangent to the graph if and only if the system of equations has a **double root** (zero discriminant) at the point of tangency. Let us intersect $y=x^2-3x+1$ and $y=x-3$:

$$x^2-3x+1=x-3 \iff x^2-4x+4=0 \iff (x-2)^2=0.$$

Since $(x-2)^2=0$ has a double root at $x=2$, the line $y=x-3$ touches the parabola at $x=2$ without crossing it and stays strictly below the parabola ($x^2-3x+1-(x-3)=(x-2)^2\ge0$) everywhere else. ✓

## A concrete example

Use the tangent line $L(x)=x-3$ to approximate $f(2.1)$:

- Tangent line approximation: $L(2.1)=2.1-3=-0.9$.
- Exact function value: $f(2.1)=(2.1)^2-3(2.1)+1=4.41-6.3+1=-0.89$.
- The discrepancy is only $0.01=(2.1-2)^2$, showing that the tangent line is the best linear approximation to $f(x)$ near $x=2$.

## How I would explain this in class

> To find the tangent line at $x=2$, we need two numbers: the $y$-coordinate and the slope. First, $f(2)=2^2-3(2)+1=-1$, so the point of tangency is $(2,-1)$. Second, the derivative is $f'(x)=2x-3$, so the slope at $x=2$ is $f'(2)=2(2)-3=1$. Using point-slope form $y-(-1)=1(x-2)$, we get $y=x-3$, and plugging in $x=2$ gives $y=2-3=-1$, confirming the point is on the line.

## Related workbook topics

- [Exercise 1: Derivative of a Polynomial and the Slope of a Tangent Line](problem_01_solution.md)
- [Exercise 11: Derivative from the Definition](problem_11_solution.md)
