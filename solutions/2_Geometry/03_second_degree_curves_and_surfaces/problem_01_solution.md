# Exercise 1. Recognizing Curves from Canonical Form

## The question

Recognize the curves

$$x^2+y^2=9,$$

$$\frac{x^2}{16}+\frac{y^2}{9}=1,$$

$$y^2=8x,$$

$$\frac{x^2}{9}-\frac{y^2}{4}=1.$$

For each one, identify the most important features and make a sketch. Explain which parts of the equation let you recognize the type of curve.

## Before calculating: what idea do we need?

When a second-degree curve in the plane is written in canonical form (centered at the origin or with vertex at the origin), the **signs and degrees of the terms in $x$ and $y$** immediately reveal its geometric family:

- **Two squared terms with the same sign and equal coefficients** ($x^2+y^2=r^2$): a **circle** of radius $r$.
- **Two squared terms with the same sign and different denominators** ($\frac{x^2}{a^2}+\frac{y^2}{b^2}=1$): an **ellipse** with semiaxes $a$ and $b$.
- **One squared term and one linear term** ($y^2=2px$ or $x^2=2py$): a **parabola**.
- **Two squared terms with opposite signs** ($\frac{x^2}{a^2}-\frac{y^2}{b^2}=1$): a **hyperbola**.

## 1. First curve: $x^2+y^2=9$

Both $x^2$ and $y^2$ appear with coefficient $+1$, and the right-hand side is $9=3^2>0$.

- **Type:** Circle.
- **Key features:** Center at $(0,0)$, radius $r=3$, axis intercepts at $(\pm 3,0)$ and $(0,\pm 3)$.
- **How we recognize it:** $x^2+y^2$ measures the squared distance from $(0,0)$, so setting it equal to $3^2$ selects all points at distance $3$ from the origin.

```text
          y
         3* (0,3)
       *  |  *
  (-3,0)  |   (3,0)
  ----*---+---*---- x
       *  |  *
        -3* (0,-3)
```

## 2. Second curve: $\frac{x^2}{16}+\frac{y^2}{9}=1$

Both $x^2$ and $y^2$ are positive and sum to $1$, with denominators $16=4^2$ and $9=3^2$.

- **Type:** Ellipse.
- **Key features:** Center at $(0,0)$, horizontal semiaxis $a=4$, vertical semiaxis $b=3$, vertices at $(\pm 4,0)$ and $(0,\pm 3)$, stretched horizontally since $4>3$.
- **How we recognize it:** A sum of two positive squares equals $1$, so neither coordinate can grow unboundedly ($|x|\le 4$, $|y|\le 3$), producing a closed oval with different scales along $Ox$ and $Oy$.

```text
            y
           3* (0,3)
       *    |    *
  (-4,0)    |     (4,0)
  ---*------+------*--- x
       *    |    *
          -3* (0,-3)
```

## 3. Third curve: $y^2=8x$

Only $y$ is squared ($y^2\ge 0$), while $x$ is linear with a positive coefficient ($8=2p$, so $p=4$).

- **Type:** Parabola.
- **Key features:** Vertex at $(0,0)$, axis of symmetry is the $x$-axis ($y=0$), opens to the right ($x\ge 0$), focus at $(2,0)$, directrix $x=-2$, passes through $(2,\pm 4)$.
- **How we recognize it:** Because $y$ is squared and $x$ is in the first power, every positive $x$ gives two symmetric values $y=\pm\sqrt{8x}$, while negative $x$ gives no real points.

```text
        y
        |      * (2,4)
        |   *
  (0,0) | *
  ------+--------- x
        | *
        |   *
        |      * (2,-4)
```

## 4. Fourth curve: $\frac{x^2}{9}-\frac{y^2}{4}=1$

Both variables are squared, but they have **opposite signs** ($+$ before $\frac{x^2}{3^2}$ and $-$ before $\frac{y^2}{2^2}$).

- **Type:** Hyperbola.
- **Key features:** Center at $(0,0)$, real semiaxis $a=3$ along $Ox$, imaginary semiaxis $b=2$ along $Oy$, vertices at $(\pm 3,0)$, no $y$-intercepts, asymptotes $y=\pm\frac{2}{3}x$.
- **How we recognize it:** The minus sign allows $x^2$ and $y^2$ to grow arbitrarily large together, while $\frac{x^2}{9}=1+\frac{y^2}{4}\ge 1$ forces $|x|\ge 3$, splitting the curve into two separate branches opening left and right.

```text
        \   y   /
     *   \  |  /   *
      *   \ | /   *
  (-3,0)*  \|/  *(3,0)
  -------*--+--*------- x
      *   / | \   *
     *   /  |  \   *
        /   |   \
```

## Quick verification

Let us check one characteristic point on each curve:

- Circle: $(3,0)\implies 3^2+0^2=9$. ✓
- Ellipse: $(4,0)\implies \frac{16}{16}+\frac{0}{9}=1$, and $(0,3)\implies \frac{0}{16}+\frac{9}{9}=1$. ✓
- Parabola: $(2,4)\implies 4^2=16=8\cdot 2$. ✓
- Hyperbola: $(3,0)\implies \frac{9}{9}-\frac{0}{4}=1$, and $(0,y)$ gives $-\frac{y^2}{4}=1$ (no real solution). ✓

## A concrete example

Suppose we change a single feature in $\frac{x^2}{9}+\frac{y^2}{4}=1$:

- Keep $+$ and make denominators equal ($9$ and $9$): $\frac{x^2}{9}+\frac{y^2}{9}=1 \iff x^2+y^2=9$, which turns the ellipse into a circle.
- Change $+$ to $-$: $\frac{x^2}{9}-\frac{y^2}{4}=1$, which breaks the closed loop into the two unbounded branches of a hyperbola.

## How I would explain this in class

> To recognize a second-degree curve in canonical form, I first check which variables are squared and what signs they have. If only one variable is squared, like $y^2=8x$, it is a parabola. If both are squared with the same sign, the curve is bounded: equal coefficients give a circle ($x^2+y^2=9$ with radius $3$), and different denominators give an ellipse ($\frac{x^2}{16}+\frac{y^2}{9}=1$ with semiaxes $4$ and $3$). If the squared terms have opposite signs, like $\frac{x^2}{9}-\frac{y^2}{4}=1$, it is a hyperbola with vertices at $(\pm 3,0)$ and asymptotes $y=\pm\frac{2}{3}x$.

## Related workbook topics

- [Exercise 3: Ellipse](problem_03_solution.md)
- [Exercise 7: Classifying a Second-Degree Equation](problem_07_solution.md)
