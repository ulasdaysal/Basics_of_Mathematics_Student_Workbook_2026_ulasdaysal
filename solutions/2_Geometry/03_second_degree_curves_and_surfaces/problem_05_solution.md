# Exercise 5. Hyperbola and Asymptotes

## The question

For

$$\frac{x^2}{16}-\frac{y^2}{9}=1,$$

find the intercepts with the $x$-axis, the asymptotes, and make a sketch. Explain why the asymptotes describe the behavior of the curve far from the center.

## Before calculating: what idea do we need?

A hyperbola in canonical form

$$\frac{x^2}{a^2}-\frac{y^2}{b^2}=1$$

has a positive term in $x^2$ and a negative term in $y^2$. From $\frac{x^2}{a^2} = 1 + \frac{y^2}{b^2} \ge 1$, we see that $|x|\ge a$: the curve has two separate branches ($x\le -a$ and $x\ge a$) and never crosses the $y$-axis. Its global opening is guided by the rectangle of dimensions $2a\times 2b$ centered at the origin and its diagonal lines $y=\pm\frac{b}{a}x$, called the **asymptotes**.

## 1. Semiaxes and intercepts with the $x$-axis

From the denominators $16=4^2$ and $9=3^2$, we read:
- **Real semiaxis:** $a = 4$ (along $Ox$).
- **Imaginary semiaxis:** $b = 3$ (along $Oy$).

To find the intercepts with the $x$-axis, set $y=0$:

$$\frac{x^2}{16} - 0 = 1 \implies x^2 = 16 \implies x = \pm 4.$$

Thus the $x$-intercepts (the vertices of the hyperbola) are $(-4,0)$ and $(4,0)$. (Setting $x=0$ gives $-\frac{y^2}{9}=1$, which has no real solutions, so there are no $y$-intercepts.)

## 2. Finding the asymptotes

Replace the $1$ on the right-hand side with $0$ to find the asymptotic directions:

$$\frac{x^2}{16}-\frac{y^2}{9}=0 \iff \frac{y^2}{9}=\frac{x^2}{16} \iff y = \pm\frac{3}{4}x.$$

The two asymptotes are the lines $y = \frac{3}{4}x$ and $y = -\frac{3}{4}x$.

## 3. Why the asymptotes describe the curve far from the center

Solve the hyperbola equation for $y^2$ and factor out $x^2$ (for $|x|\ge 4$):

$$\frac{y^2}{9} = \frac{x^2}{16}-1 = \frac{x^2}{16}\left(1-\frac{16}{x^2}\right) \implies y = \pm\frac{3}{4}x\sqrt{1-\frac{16}{x^2}}.$$

When $|x|$ is very large (far from the center $(0,0)$), the fraction $\frac{16}{x^2}$ becomes tiny and approaches $0$. Consequently, the square root $\sqrt{1-\frac{16}{x^2}}$ approaches $1$, and the $y$-coordinate on the hyperbola approaches $\pm\frac{3}{4}x$. Equivalently, the vertical distance between the curve and the line $y=\frac{3}{4}x$ in the first quadrant is

$$\frac{3}{4}x - \frac{3}{4}\sqrt{x^2-16} = \frac{3}{4}\cdot\frac{16}{x+\sqrt{x^2-16}} = \frac{12}{x+\sqrt{x^2-16}} \xrightarrow{x\to\infty} 0.$$

## 4. Sketch of the hyperbola and its asymptotes

Draw the central reference box $[-4,4]\times[-3,3]$, its diagonals $y=\pm\frac{3}{4}x$, and the two branches passing through $(\pm 4,0)$ approaching the diagonals:

```text
       \      y      /
   *    \    3+     /    *   y = (3/4)x
     *   \  ..|..  /   *
       *  \ : | : /  *
  (-4,0) * \: | :/ * (4,0)
  ---------*--+--*--------- x
       *  / : | : \  *
     *   /  ..|..  \   *
   *    /   -3+     \    *   y = -(3/4)x
       /      |      \
```

## Quick verification

Let us test $x=5$:

- On the hyperbola: $\frac{25}{16}-\frac{y^2}{9}=1 \implies \frac{y^2}{9}=\frac{9}{16} \implies y=\pm\frac{9}{4}=\pm 2.25$. ✓
- On the asymptote: $y=\pm\frac{3}{4}(5)=\pm\frac{15}{4}=\pm 3.75$.

Now test $x=20$:

- On the hyperbola: $y=\frac{3}{4}\sqrt{400-16}=\frac{3}{4}\sqrt{384}\approx 14.697$.
- On the asymptote: $y=\frac{3}{4}(20)=15$.

The gap shrinks from $1.5$ at $x=5$ down to $0.303$ at $x=20$. ✓

## A concrete example

At $x=4$, the hyperbola is at $(4,0)$ while the asymptote is at $(4,3)$ (gap $=3$). By $x=40$, the hyperbola is at $y=\frac{3}{4}\sqrt{1584}\approx 29.85$ while the asymptote is at $y=30$ (gap $\approx 0.15$). Far from the origin, the constant $1$ on the right-hand side of $\frac{x^2}{16}-\frac{y^2}{9}=1$ becomes negligible compared to the huge numbers $\frac{x^2}{16}$ and $\frac{y^2}{9}$.

## How I would explain this in class

> For $\frac{x^2}{16}-\frac{y^2}{9}=1$, we have $a=4$ and $b=3$. Setting $y=0$ gives the $x$-intercepts $(\pm 4,0)$, and replacing $1$ by $0$ gives the asymptotes $y=\pm\frac{3}{4}x$. Rewriting the equation as $y=\pm\frac{3}{4}x\sqrt{1-\frac{16}{x^2}}$ shows why the asymptotes control the shape far from the origin: as $|x|\to\infty$, the term $\frac{16}{x^2}$ vanishes, so the curve becomes indistinguishable from the lines $y=\pm\frac{3}{4}x$.

## Related workbook topics

- [Exercise 1: Recognizing Curves from Canonical Form](problem_01_solution.md)
- [Exercise 7: Classifying a Second-Degree Equation](problem_07_solution.md)
