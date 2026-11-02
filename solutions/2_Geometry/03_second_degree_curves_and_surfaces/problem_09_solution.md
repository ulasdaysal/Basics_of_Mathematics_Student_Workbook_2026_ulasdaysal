# Exercise 9. Ellipsoid and Its Cross-Sections

## The question

Consider

$$\frac{x^2}{9}+\frac{y^2}{4}+\frac{z^2}{16}=1.$$

Give the semiaxis lengths, describe the cross-section $z=0$, and explain how the cross-sections $z=c$ change for $|c|<4$.

## Before calculating: what idea do we need?

An **ellipsoid** centered at the origin has the canonical equation

$$\frac{x^2}{a^2}+\frac{y^2}{b^2}+\frac{z^2}{c_0^2}=1.$$

To understand a 3D surface, we slice it with horizontal planes $z=c$ (like a CT scan). Substituting $z=c$ freezes one variable and leaves a 2D equation in $x$ and $y$, whose size depends on $c$.

## 1. Semiaxis lengths

Write the denominators as squares:

$$9 = 3^2,\qquad 4 = 2^2,\qquad 16 = 4^2.$$

Thus the three semiaxis lengths are:
- **Along the $x$-axis ($Ox$):** $a = \sqrt{9} = 3$ (vertices at $(\pm 3,0,0)$).
- **Along the $y$-axis ($Oy$):** $b = \sqrt{4} = 2$ (vertices at $(0,\pm 2,0)$).
- **Along the $z$-axis ($Oz$):** $c_0 = \sqrt{16} = 4$ (vertices at $(0,0,\pm 4)$).

The ellipsoid is longest vertically along $Oz$ ($c_0=4$) and narrowest along $Oy$ ($b=2$).

## 2. The cross-section $z=0$

Substitute $z=0$ into the equation of the ellipsoid:

$$\frac{x^2}{9} + \frac{y^2}{4} + \frac{0^2}{16} = 1 \implies \frac{x^2}{9} + \frac{y^2}{4} = 1\quad\text{in the plane }z=0.$$

This cross-section (the "equator" of the ellipsoid in the $xy$-plane) is an **ellipse** centered at $(0,0,0)$ with semiaxes $a=3$ along $Ox$ and $b=2$ along $Oy$.

## 3. How the cross-sections $z=c$ change for $|c|<4$

Fix a constant height $z=c$ with $|c|<4$ (so $c^2<16$ and $1-\frac{c^2}{16}>0$). Substituting $z=c$ gives:

$$\frac{x^2}{9} + \frac{y^2}{4} + \frac{c^2}{16} = 1 \implies \frac{x^2}{9} + \frac{y^2}{4} = 1 - \frac{c^2}{16}.$$

To put this 2D curve into canonical ellipse form, divide both sides by $1-\frac{c^2}{16} > 0$:

$$\frac{x^2}{9\left(1-\frac{c^2}{16}\right)} + \frac{y^2}{4\left(1-\frac{c^2}{16}\right)} = 1.$$

Let $k(c) = \sqrt{1-\frac{c^2}{16}} \in (0,1]$. Then the slice at height $z=c$ is an **ellipse** with semiaxes

$$a(c) = 3\sqrt{1-\frac{c^2}{16}},\qquad b(c) = 2\sqrt{1-\frac{c^2}{16}}.$$

How the slices behave as $c$ varies:
1. **At $c=0$:** $k(0)=1$, so the ellipse has its **maximum size** ($a(0)=3$, $b(0)=2$).
2. **As $|c|$ increases from $0$ toward $4$:** The factor $\sqrt{1-\frac{c^2}{16}}$ decreases steadily toward $0$. The cross-sections remain **similar ellipses** (their aspect ratio $\frac{a(c)}{b(c)} = \frac{3}{2}$ never changes!), but they **shrink** symmetrically as we move either up ($c>0$) or down ($c<0$).
3. **At the poles $c=\pm 4$:** $1-\frac{c^2}{16}=0$, so the ellipse shrinks to a **single point** $(0,0,\pm 4)$. (For $|c|>4$, the right-hand side is negative and the plane misses the ellipsoid completely.)

## 4. Summary table of horizontal slices

| Height $z=c$ | Scale factor $\sqrt{1-c^2/16}$ | Horizontal semiaxes $(a(c),\,b(c))$ | Geometric slice |
| :---: | :---: | :---: | :--- |
| $c = 0$ | $1$ | $(3,\;2)$ | Largest ellipse (equator) |
| $c = \pm 2$ | $\frac{\sqrt{3}}{2}\approx 0.866$ | $\left(\frac{3\sqrt{3}}{2},\;\sqrt{3}\right)$ | Smaller similar ellipse |
| $c = \pm 2\sqrt{3}$ | $\frac{1}{2} = 0.5$ | $(1.5,\;1)$ | Half-scale ellipse |
| $c = \pm 4$ | $0$ | $(0,\;0)$ | Single point $(0,0,\pm 4)$ |
| $|c| > 4$ | — | — | Empty set |

## Quick verification

Let us check a point on the slice $z = 2\sqrt{3}$ (where the scale factor is $\frac{1}{2}$): its $x$-vertex in that plane is $(x,y,z) = \left(\frac{3}{2}, 0, 2\sqrt{3}\right)$. Substitute into the ellipsoid equation:

$$\frac{(3/2)^2}{9} + \frac{0^2}{4} + \frac{(2\sqrt{3})^2}{16} = \frac{9/4}{9} + 0 + \frac{12}{16} = \frac{1}{4} + \frac{3}{4} = 1.$$

It lies on the ellipsoid. ✓

## A concrete example

At height $z = \frac{12}{5} = 2.4$, the scale factor is

$$\sqrt{1 - \frac{(12/5)^2}{16}} = \sqrt{1 - \frac{144}{400}} = \sqrt{1 - \frac{9}{25}} = \sqrt{\frac{16}{25}} = \frac{4}{5}.$$

So the horizontal cross-section at $z=2.4$ is an ellipse with exact rational semiaxes $a = 3\cdot\frac{4}{5} = 2.4$ and $b = 2\cdot\frac{4}{5} = 1.6$.

## How I would explain this in class

> From $\frac{x^2}{9}+\frac{y^2}{4}+\frac{z^2}{16}=1$, the denominators are $3^2, 2^2, 4^2$, so the semiaxes are $3$ along $Ox$, $2$ along $Oy$, and $4$ along $Oz$. Setting $z=0$ gives the biggest horizontal cross-section, the ellipse $\frac{x^2}{9}+\frac{y^2}{4}=1$ with semiaxes $3$ and $2$. For any height $z=c$ with $|c|<4$, we get $\frac{x^2}{9}+\frac{y^2}{4}=1-\frac{c^2}{16}$, which is a family of ellipses with the same $3:2$ proportion whose semiaxes $3\sqrt{1-c^2/16}$ and $2\sqrt{1-c^2/16}$ shrink as $|c|$ grows, until they collapse to a single point at the top and bottom poles $z=\pm 4$.

## Related workbook topics

- [Exercise 3: Ellipse](problem_03_solution.md)
- [Exercise 13: Intersection of a Sphere and a Plane](problem_13_solution.md)
