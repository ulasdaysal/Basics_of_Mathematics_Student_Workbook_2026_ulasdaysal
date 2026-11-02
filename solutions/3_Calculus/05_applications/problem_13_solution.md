# Exercise 13. Minimum Distance from a Point to a Parabola

## The question

Find the point on the parabola

$$y=x^2$$

that is closest to the fixed point $P=(0,3)$, and compute the minimum distance between $P$ and the parabola. Interpret the geometric relationship between the shortest segment and the tangent line at the optimal point.

## Before calculating: what idea do we need?

Any point on the parabola $y=x^2$ can be written in terms of a single parameter as $Q=(x,x^2)$ for $x\in\mathbb{R}$. By the Euclidean distance formula, the distance between $P=(0,3)$ and $Q=(x,x^2)$ is

$$d(x) = \sqrt{(x-0)^2 + (x^2-3)^2}.$$

Because the square root function $\sqrt{u}$ is strictly increasing for $u\ge 0$, the distance $d(x)$ reaches its minimum at the exact same $x$-values where the **squared distance** $f(x)=[d(x)]^2$ reaches its minimum. Optimizing $f(x)$ avoids differentiating square roots!

## 1. Building the squared-distance objective function

For an arbitrary point $Q=(x,x^2)$ on the parabola ($x\in\mathbb{R}$), the squared distance to $P=(0,3)$ is

$$f(x) = [d(x)]^2 = x^2 + (x^2-3)^2.$$

Expanding the expression into a polynomial in $x$:

$$f(x) = x^2 + (x^4 - 6x^2 + 9) = x^4 - 5x^2 + 9,\qquad x\in\mathbb{R}.$$

## 2. Finding the critical points

Differentiating $f(x)=x^4-5x^2+9$ with respect to $x$ gives:

$$f'(x) = 4x^3 - 10x = 2x(2x^2 - 5).$$

Setting $f'(x)=0$ yields three critical points:

$$x_0 = 0,\qquad x_1 = -\sqrt{\frac{5}{2}} = -\frac{\sqrt{10}}{2} \approx -1.581,\qquad x_2 = \sqrt{\frac{5}{2}} = \frac{\sqrt{10}}{2} \approx 1.581.$$

## 3. Classifying the critical points and finding the minimum distance

Let us compute the second derivative $f''(x) = 12x^2 - 10$:

- At $x_0=0$: $f''(0) = -10 < 0$, so $x=0$ (the vertex $(0,0)$ of the parabola) is a **local maximum** of the distance among nearby points on the curve, with $f(0)=9$ and $d(0)=3$.
- At $x_{1,2}=\pm\sqrt{\frac{5}{2}}$: $f''\bigl(\pm\sqrt{\frac{5}{2}}\bigr) = 12\left(\frac{5}{2}\right)-10 = 20 > 0$, so both symmetric points give the **global minimum**.

At $x=\pm\sqrt{\frac{5}{2}}$, the $y$-coordinate on the parabola is $y=x^2=\frac{5}{2}=2.5$. Thus, there are two symmetric closest points on the parabola:

$$Q_1 = \left(-\frac{\sqrt{10}}{2},\, \frac{5}{2}\right) \quad\text{and}\quad Q_2 = \left(\frac{\sqrt{10}}{2},\, \frac{5}{2}\right).$$

Evaluating the minimum squared distance:

$$f\left(\pm\sqrt{\frac{5}{2}}\right) = \frac{5}{2} + \left(\frac{5}{2}-3\right)^2 = \frac{5}{2} + \frac{1}{4} = \frac{11}{4},$$

so the minimum distance is

$$d_{\min} = \sqrt{\frac{11}{4}} = \frac{\sqrt{11}}{2} \approx 1.658.$$

## 4. Geometric interpretation (orthogonality to the tangent line)

At the closest point $Q_2=\bigl(\sqrt{\frac{5}{2}}, \frac{5}{2}\bigr)$, the slope of the tangent line to $y=x^2$ is

$$m_{\text{tan}} = y'\left(\sqrt{\frac{5}{2}}\right) = 2\sqrt{\frac{5}{2}} = \sqrt{10}.$$

Meanwhile, the slope of the line segment $PQ_2$ connecting $P=(0,3)$ to $Q_2=\bigl(\sqrt{\frac{5}{2}}, \frac{5}{2}\bigr)$ is

$$m_{PQ_2} = \frac{\frac{5}{2}-3}{\sqrt{\frac{5}{2}}-0} = \frac{-\frac{1}{2}}{\sqrt{\frac{5}{2}}} = -\frac{1}{\sqrt{10}}.$$

Multiplying the two slopes gives $m_{\text{tan}}\cdot m_{PQ_2} = \sqrt{10}\cdot\bigl(-\frac{1}{\sqrt{10}}\bigr) = -1$. Geometrically, **the shortest segment from an external point to a smooth curve is always perpendicular (normal) to the tangent line at the foot of the segment**.

## Quick verification

We can verify the result by completing the square in $u=x^2\ge 0$:

$$f(x) = u^2 - 5u + 9 = \left(u - \frac{5}{2}\right)^2 + 9 - \frac{25}{4} = \left(x^2 - \frac{5}{2}\right)^2 + \frac{11}{4}.$$

Since $\bigl(x^2-\frac{5}{2}\bigr)^2\ge 0$, the minimum value of $f(x)$ is undeniably $\frac{11}{4}$, achieved precisely when $x^2=\frac{5}{2}$. ✓

## A concrete example

Compare the distances from $P=(0,3)$ to several points on $y=x^2$:
- To the vertex $(0,0)$: $d(0)=\sqrt{0+9}=3.000$.
- To $(1,1)$: $d(1)=\sqrt{1^2+(1-3)^2}=\sqrt{5}\approx 2.236$.
- To the optimal point $\bigl(\sqrt{2.5}, 2.5\bigr)\approx(1.581, 2.5)$: $d_{\min}=\frac{\sqrt{11}}{2}\approx 1.658$.
- To $(2,4)$: $d(2)=\sqrt{2^2+(4-3)^2}=\sqrt{5}\approx 2.236$.

Notice that $(0,0)$ is actually farther from $(0,3)$ than the side walls of the parabola near $y=2.5$!

## How I would explain this in class

> Instead of minimizing the square root $d(x)=\sqrt{x^2+(x^2-3)^2}$, we minimize the squared distance $f(x)=x^2+(x^2-3)^2=x^4-5x^2+9$. Differentiating gives $f'(x)=4x^3-10x=2x(2x^2-5)=0$, with critical points $x=0$ (a local maximum at the vertex) and $x=\pm\sqrt{5/2}$ (global minima). This gives the two symmetric closest points $\bigl(\pm\frac{\sqrt{10}}{2}, \frac{5}{2}\bigr)$ at distance $\frac{\sqrt{11}}{2}\approx 1.658$, where the segment from $(0,3)$ meets the parabola at a right angle.

## Related workbook topics

- [Exercise 2: Maximum Area of a Rectangle](problem_02_solution.md)
- [Exercise 10: A Cable Through Water and Land](problem_10_solution.md)
