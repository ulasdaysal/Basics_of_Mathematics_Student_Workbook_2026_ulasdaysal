# Exercise 15. Recognition and Sketch Without a Given Name

## The question

Consider the two equations:

$$4x^2+9y^2-8x+36y+4=0,$$

$$4x^2+y^2=z^2.$$

For the first equation, reduce it to canonical form, recognize the curve, give its most important features, and make a sketch.

For the second equation, do not begin by using a ready-made name for the surface. First describe the cross-sections $z=c$ and the cross-sections by the planes $x=0$ and $y=0$, paying attention to the different scales along the axes. Only then identify the surface and make a sketch.

## Before calculating: what idea do we need?

This exercise brings together the two central tools of the entire set:
1. **Completing the square (for shifted equations):** Factor out the leading coefficients of $x^2$ and $y^2$ to find the center and semiaxes of a shifted 2D curve.
2. **Slicing by coordinate planes (for 3D surfaces):** Freeze one variable at a time ($z=c$, $x=0$, $y=0$) to read the 2D cross-sections and their axis scales before naming the 3D surface.

## 1. First equation: reducing $4x^2+9y^2-8x+36y+4=0$ to canonical form

Group the $x$-terms and $y$-terms, and move the constant $+4$ to the right-hand side:

$$(4x^2-8x) + (9y^2+36y) = -4.$$

Factor out $4$ from the $x$-group and $9$ from the $y$-group:

$$4(x^2-2x) + 9(y^2+4y) = -4.$$

Complete the square inside each bracket:
- $x^2-2x = (x-1)^2 - 1$,
- $y^2+4y = (y+2)^2 - 4$.

Substitute back:

$$4\big((x-1)^2 - 1\big) + 9\big((y+2)^2 - 4\big) = -4$$

$$4(x-1)^2 - 4 + 9(y+2)^2 - 36 = -4$$

$$4(x-1)^2 + 9(y+2)^2 = 36.$$

Divide both sides by $36$ to get the canonical form:

$$\frac{(x-1)^2}{9} + \frac{(y+2)^2}{4} = 1.$$

## 2. Recognizing the first curve, its features, and sketch

- **Type of curve:** **Shifted ellipse**.
- **Center:** $C = (1,-2)$.
- **Semiaxes:** Horizontal semiaxis $a = \sqrt{9} = 3$ (along $Ox$), vertical semiaxis $b = \sqrt{4} = 2$ (along $Oy$). The ellipse is stretched horizontally since $a=3>b=2$.
- **Vertices:**
  - Horizontal vertices: $(1\pm 3, -2) = (-2,-2)$ and $(4,-2)$.
  - Vertical vertices: $(1, -2\pm 2) = (1,-4)$ and $(1,0)$ (tangent to the $x$-axis at $(1,0)$!).

```text
            y
            |  (1,0)
  ----------+---*---------- x
       *    |   :    *
  (-2,-2)*..+...C(1,-2)..*(4,-2)
       *    |   :    *
            |   *(1,-4)
```

## 3. Second equation: cross-sections of $4x^2+y^2=z^2$

Let us analyze the slices of $4x^2+y^2=z^2$ **before** naming the surface:

1. **Horizontal cross-sections $z=c$:**
   - For $c = 0$: $4x^2+y^2 = 0 \implies (0,0,0)$, a **single point** at the origin.
   - For $c \neq 0$: $4x^2+y^2 = c^2$. Divide by $c^2>0$:
     $$\frac{x^2}{(c/2)^2} + \frac{y^2}{c^2} = 1.$$
     This is an **ellipse** centered at $(0,0,c)$ with horizontal semiaxes
     $$a(c) = \frac{|c|}{2}\quad\text{(along }Ox\text{)},\qquad b(c) = |c|\quad\text{(along }Oy\text{)}.$$
     Notice the different scales: at every height $z=c\neq 0$, the ellipse is **twice as wide along the $y$-axis as along the $x$-axis**, and both semiaxes grow linearly with $|c|$.

2. **Cross-section by the plane $x=0$ (in the $yz$-plane):**
   $$y^2 = z^2 \iff z = \pm y.$$
   This is a **pair of intersecting straight lines** through the origin with slopes $\pm 1$ (wide opening: $|y|=|z|$).

3. **Cross-section by the plane $y=0$ (in the $xz$-plane):**
   $$4x^2 = z^2 \iff z = \pm 2x.$$
   This is a **pair of intersecting straight lines** through the origin with steeper slopes $\pm 2$ (narrower opening: $|x|=\frac{1}{2}|z|$).

## 4. Identifying and sketching the second surface

Putting the cross-sections together—a single vertex at $(0,0,0)$, straight-line generators in vertical planes through $Oz$ with steeper slope along $Ox$ than $Oy$, and horizontal cross-sections that are ellipses expanding linearly with $|z|$—we identify the surface as an **elliptic cone** (double cone with elliptical horizontal slices stretched along $Oy$).

```text
             z
       \  \  |  /  /      z = c: ellipse x^2/(c/2)^2 + y^2/c^2 = 1
        \ .--+--. /       (semiaxis |c|/2 along Ox, |c| along Oy)
         \ \ | / /
          \ \|/ /         x = 0: wider lines z = +-y
           \ * /          y = 0: steeper lines z = +-2x
  -----------+----------- x, y
           / * \ (0,0,0)
          / /|\ \
         / .-+-. \
        / /  |  \ \
```

## Quick verification

- **First equation:** Substitute the top vertex $(1,0)$ and right vertex $(4,-2)$ into $4x^2+9y^2-8x+36y+4$:
  - At $(1,0)$: $4(1) + 0 - 8(1) + 0 + 4 = 0$. ✓
  - At $(4,-2)$: $4(16) + 9(4) - 8(4) + 36(-2) + 4 = 64 + 36 - 32 - 72 + 4 = 0$. ✓
- **Second equation:** At height $z=2$, the ellipse vertices are $(1,0,2)$ along $Ox$ and $(0,2,2)$ along $Oy$:
  - At $(1,0,2)$: $4(1)^2 + 0^2 = 4 = 2^2$. ✓
  - At $(0,2,2)$: $4(0)^2 + 2^2 = 4 = 2^2$. ✓

## A concrete example

At height $z=4$ on the surface $4x^2+y^2=z^2$, the horizontal cross-section is $4x^2+y^2=16$, or

$$\frac{x^2}{2^2} + \frac{y^2}{4^2} = 1.$$

Thus, at $z=4$, the surface extends from $x=-2$ to $x=2$ along the $x$-axis (total width $4$), and from $y=-4$ to $y=4$ along the $y$-axis (total width $8$).

## How I would explain this in class

> For the first equation, I factor out $4$ and $9$ and complete the squares: $4(x-1)^2-4+9(y+2)^2-36+4=0$, which simplifies to $\frac{(x-1)^2}{9}+\frac{(y+2)^2}{4}=1$. That is a shifted ellipse centered at $(1,-2)$ with horizontal semiaxis $3$ and vertical semiaxis $2$. For the second equation $4x^2+y^2=z^2$, slicing with $z=c\neq 0$ gives $\frac{x^2}{(c/2)^2}+\frac{y^2}{c^2}=1$, which is a family of ellipses twice as wide along $Oy$ ($b=|c|$) as along $Ox$ ($a=|c|/2$), shrinking to a single point at $z=0$. Slicing with $x=0$ gives the lines $z=\pm y$ and slicing with $y=0$ gives the steeper lines $z=\pm 2x$. Together, these slices show that the surface is an elliptic cone with vertex at the origin.

## Related workbook topics

- [Exercise 6: Shifted Ellipse](problem_06_solution.md)
- [Exercise 14: Cone and Cylinder](problem_14_solution.md)
