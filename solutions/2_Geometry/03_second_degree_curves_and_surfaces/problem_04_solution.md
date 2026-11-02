# Exercise 4. Parabola

## The question

For

$$y^2=12x,$$

identify the vertex, axis of symmetry, and opening direction. Find points on the parabola for $x=3$ and use them to make a sketch.

## Before calculating: what idea do we need?

A parabola in canonical form has one variable squared and the other variable linear:

$$y^2 = 2px \qquad\text{or}\qquad x^2 = 2py.$$

For $y^2 = 12x$:
- Because $y^2\ge 0$ for every real $y$, the right-hand side must satisfy $12x\ge 0$, so $x\ge 0$.
- Replacing $y$ with $-y$ leaves $y^2$ unchanged, which means the curve is symmetric across the line $y=0$ (the $x$-axis).

## 1. Vertex, axis of symmetry, and opening direction

From the equation $y^2=12x$:

- **Vertex:** $(0,0)$, the extreme point where $x$ takes its minimum value $x=0$ (giving $y=0$).
- **Axis of symmetry:** The $x$-axis ($y=0$), because $(-y)^2 = y^2 = 12x$ pairs every point $(x,y)$ with $(x,-y)$.
- **Opening direction:** Opens **to the right** (along the positive $x$-axis), since real solutions exist only when $12x\ge 0 \iff x\ge 0$.
- *(Optional focal parameter)*: Comparing $y^2=12x$ with $y^2=2px$ (or $4fx$) gives $p=6$, so the focus is $(3,0)$ and the directrix is $x=-3$.

## 2. Points on the parabola for $x=3$

Substitute $x=3$ into $y^2=12x$:

$$y^2 = 12\cdot 3 = 36 \implies y = \pm\sqrt{36} = \pm 6.$$

This gives two symmetric points on the parabola:

$$A = (3,6)\qquad\text{and}\qquad B = (3,-6).$$

## 3. Additional reference points and coordinate table

To make an accurate sketch, we can also check $x=0$ and $x=\frac{3}{4} = 0.75$:

| $x$ | $y^2=12x$ | $y=\pm\sqrt{12x}$ | Points $(x,y)$ |
| :---: | :---: | :---: | :---: |
| $0$ | $0$ | $0$ | $(0,0)$ (vertex) |
| $\frac{3}{4}$ | $9$ | $\pm 3$ | $(\frac{3}{4},3),\;(\frac{3}{4},-3)$ |
| $3$ | $36$ | $\pm 6$ | $(3,6),\;(3,-6)$ |

## 4. Sketch of the parabola

```text
        y
       6|         * (3,6)
        |     *
       3|  * (0.75,3)
  (0,0) |*
  ------+---------*---- x
        |*        3
      -3|  * (0.75,-3)
        |     *
      -6|         * (3,-6)
```

## Quick verification

Substitute $A=(3,6)$ and $B=(3,-6)$ into $y^2=12x$:

- Left-hand side: $(\pm 6)^2 = 36$.
- Right-hand side: $12\cdot 3 = 36$. ✓

Also check $x=-1$: $y^2 = -12$ has no real solutions, confirming the curve does not enter the left half-plane $x<0$. ✓

## A concrete example

Notice that at $x=3$, the segment connecting $(3,6)$ and $(3,-6)$ passes right through the focus $F=(3,0)$ and has total length $6-(-6)=12$, which matches the coefficient $2p=12$ in $y^2=12x$ (this segment is called the *latus rectum* of the parabola).

## How I would explain this in class

> In $y^2=12x$, only $y$ is squared, so the curve is a parabola with vertex at $(0,0)$. Since $y^2\ge 0$, we need $x\ge 0$, so the parabola opens to the right, and because $(\pm y)^2$ gives the same value, the $x$-axis ($y=0$) is the axis of symmetry. Plugging in $x=3$ gives $y^2=36$, so $y=\pm 6$; plotting $(0,0)$, $(3,6)$, and $(3,-6)$ immediately gives the shape of the parabola.

## Related workbook topics

- [Exercise 1: Recognizing Curves from Canonical Form](problem_01_solution.md)
- [Exercise 10: Paraboloids](problem_10_solution.md)
