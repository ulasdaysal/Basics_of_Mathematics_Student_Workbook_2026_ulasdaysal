# Exercise 3. Ellipse

## The question

For

$$\frac{x^2}{25}+\frac{y^2}{9}=1,$$

find the semiaxis lengths, the intercepts with the coordinate axes, and make a sketch. Explain along which axis the ellipse is more stretched and how this is visible in the equation.

## Before calculating: what idea do we need?

The canonical equation of an ellipse centered at the origin is

$$\frac{x^2}{a^2}+\frac{y^2}{b^2}=1\qquad (a>0,\;b>0).$$

Because a square is never negative ($x^2\ge 0$ and $y^2\ge 0$), neither fraction can exceed $1$:

$$\frac{x^2}{a^2}\le 1 \iff |x|\le a,\qquad \frac{y^2}{b^2}\le 1 \iff |y|\le b.$$

Thus $a$ is the horizontal semiaxis (maximum horizontal reach from the center) and $b$ is the vertical semiaxis (maximum vertical reach from the center).

## 1. Semiaxis lengths

Write the denominators as squares of positive numbers:

$$25 = 5^2,\qquad 9 = 3^2.$$

Therefore:
- **Horizontal semiaxis (along $Ox$):** $a = \sqrt{25} = 5$.
- **Vertical semiaxis (along $Oy$):** $b = \sqrt{9} = 3$.

The full major axis has length $2a=10$, and the full minor axis has length $2b=6$.

## 2. Intercepts with the coordinate axes

- **Intercepts with the $x$-axis ($y=0$):**
  $$\frac{x^2}{25} + 0 = 1 \implies x^2 = 25 \implies x = \pm 5.$$
  The $x$-intercepts (major vertices) are $(-5,0)$ and $(5,0)$.

- **Intercepts with the $y$-axis ($x=0$):**
  $$0 + \frac{y^2}{9} = 1 \implies y^2 = 9 \implies y = \pm 3.$$
  The $y$-intercepts (minor vertices) are $(0,-3)$ and $(0,3)$.

## 3. Direction of stretching and why it appears in the equation

The ellipse is **more stretched along the $x$-axis** (horizontally) because $a=5 > b=3$.

How is this visible in the equation? The denominator under $x^2$ is $25$, which is larger than the denominator $9$ under $y^2$. Since $\frac{x^2}{25}+\frac{y^2}{9}=1$, dividing $x^2$ by a larger number means $x$ must reach a larger magnitude ($|x|=5$) than $y$ ($|y|=3$) to make its fraction equal to $1$.

## 4. Sketch of the ellipse

Plot the center $(0,0)$ and the four vertices $(\pm 5,0)$ and $(0,\pm 3)$, then connect them with a smooth symmetric oval:

```text
               y
              3* (0,3)
         *     |     *
     *         |         *
  (-5,0)       |        (5,0)
  --*----------+----------*-- x
     *         |         *
         *     |     *
             -3* (0,-3)
```

| Point | Coordinates | Role |
| :--- | :--- | :--- |
| Left / Right vertices | $(-5,0),\;(5,0)$ | Endpoints of major axis (length $10$) |
| Bottom / Top vertices | $(0,-3),\;(0,3)$ | Endpoints of minor axis (length $6$) |

## Quick verification

Let us check a non-vertex point on the ellipse. If $x=4$, then

$$\frac{4^2}{25}+\frac{y^2}{9}=1 \implies \frac{y^2}{9}=1-\frac{16}{25}=\frac{9}{25} \implies y=\pm\frac{9}{5}=\pm 1.8.$$

Substituting $(4, 1.8)$ gives $\frac{16}{25}+\frac{3.24}{9}=0.64+0.36=1$, and indeed $|x|=4\le 5$ and $|y|=1.8\le 3$. ✓

## A concrete example

Think of the ellipse as a rescaled unit circle $u^2+v^2=1$ where $u=\frac{x}{5}$ and $v=\frac{y}{3}$, so $x=5u$ and $y=3v$. A unit circle is stretched by a factor of $5$ horizontally and by a factor of $3$ vertically, which directly explains why the horizontal span $[-5,5]$ is wider than the vertical span $[-3,3]$.

## How I would explain this in class

> In the equation $\frac{x^2}{25}+\frac{y^2}{9}=1$, the denominators are $5^2$ and $3^2$, so the semiaxes are $a=5$ along the $x$-axis and $b=3$ along the $y$-axis. Setting $y=0$ gives $x$-intercepts $(\pm 5,0)$, and setting $x=0$ gives $y$-intercepts $(0,\pm 3)$. Because $x^2$ is divided by the larger denominator $25$, $x$ can grow further before the fraction hits $1$, so the ellipse is stretched horizontally along $Ox$.

## Related workbook topics

- [Exercise 1: Recognizing Curves from Canonical Form](problem_01_solution.md)
- [Exercise 6: Shifted Ellipse](problem_06_solution.md)
