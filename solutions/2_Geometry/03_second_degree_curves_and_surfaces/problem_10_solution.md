# Exercise 10. Paraboloids

## The question

Compare

$$z=x^2+y^2$$

and

$$z=x^2-y^2.$$

For each surface, describe the cross-sections $x=0$, $y=0$, and $z=c$, then make a qualitative sketch.

## Before calculating: what idea do we need?

In both equations, $z$ appears linearly while $x$ and $y$ are squared—this is the signature of a **paraboloid**. The entire geometric difference between the two surfaces comes from the **relative sign** of $x^2$ and $y^2$:

- Same sign ($z=x^2+y^2$): both vertical coordinate slices curve in the **same direction** (upward), forming a bowl (**elliptic/circular paraboloid**).
- Opposite signs ($z=x^2-y^2$): the two vertical coordinate slices curve in **opposite directions** (one upward, one downward), forming a saddle (**hyperbolic paraboloid**).

## 1. First surface: $z = x^2+y^2$ (Elliptic / Circular Paraboloid)

Let us examine its three families of cross-sections:

- **Cross-section $x=0$ (in the $yz$-plane):** $z = y^2$, a parabola with vertex at $(0,0,0)$ opening **upward** ($+Oz$).
- **Cross-section $y=0$ (in the $xz$-plane):** $z = x^2$, an identical parabola with vertex at $(0,0,0)$ opening **upward** ($+Oz$).
- **Horizontal cross-sections $z=c$:** $x^2+y^2 = c$.
  - For $c < 0$: **empty set** (no real points, since $x^2+y^2\ge 0$).
  - For $c = 0$: the **single point** $(0,0,0)$ (the vertex/bottom of the bowl).
  - For $c > 0$: a **circle** of radius $r = \sqrt{c}$, which expands as we move higher.

```text
          z
          |   .-"""-.     z = c > 0 (circles)
          |  '---+---'
          |   \  |  /     z = x^2 and z = y^2
          |    \ | /      (both open upward)
          |     \|/
  --------+------*------- x, y
                (0,0,0)
```

## 2. Second surface: $z = x^2-y^2$ (Hyperbolic Paraboloid)

Now examine the same three cross-sections when $+y^2$ is replaced by $-y^2$:

- **Cross-section $x=0$ (in the $yz$-plane):** $z = -y^2$, a parabola with vertex at $(0,0,0)$ opening **downward** ($-Oz$).
- **Cross-section $y=0$ (in the $xz$-plane):** $z = x^2$, a parabola with vertex at $(0,0,0)$ opening **upward** ($+Oz$).
- **Horizontal cross-sections $z=c$:** $x^2-y^2 = c$.
  - For $c > 0$: a **hyperbola** $x^2-y^2=c$ opening along the $x$-axis (vertices at $(\pm\sqrt{c},0,c)$).
  - For $c = 0$: $x^2-y^2 = (x-y)(x+y) = 0$, a **pair of intersecting lines** $y=x$ and $y=-x$ in the plane $z=0$.
  - For $c < 0$: $y^2-x^2 = |c|$, a **hyperbola** opening along the $y$-axis (vertices at $(0,\pm\sqrt{|c|},c)$).

```text
          z
      *   |   *      y = 0: z = x^2 (curves up along Ox)
       \  |  /
        \ | / (0,0,0) saddle point
  -------*+*-------
        / | \
       /  |  \       x = 0: z = -y^2 (curves down along Oy)
      *   |   *
```

## 3. Side-by-side comparison table

| Slice / Feature | $z = x^2+y^2$ (Bowl) | $z = x^2-y^2$ (Saddle) |
| :--- | :--- | :--- |
| Slice $x=0$ | Parabola $z=y^2$ (opens **up**) | Parabola $z=-y^2$ (opens **down**) |
| Slice $y=0$ | Parabola $z=x^2$ (opens **up**) | Parabola $z=x^2$ (opens **up**) |
| Slice $z=c>0$ | Circle of radius $\sqrt{c}$ | Hyperbola along $Ox$ |
| Slice $z=0$ | Single point $(0,0,0)$ | Two crossed lines $y=\pm x$ |
| Slice $z=c<0$ | Empty set | Hyperbola along $Oy$ |
| Origin $(0,0,0)$ | Global minimum ($z\ge 0$) | Saddle point ($z$ takes both signs) |

## Quick verification

Check the points $(2,1,z)$ and $(1,2,z)$ on both surfaces:

- On $z=x^2+y^2$: both give $z = 4+1 = 5 > 0$, lying on the circle $x^2+y^2=5$ at height $z=5$. ✓
- On $z=x^2-y^2$: $(2,1)$ gives $z = 4-1 = +3$ (on the hyperbola $x^2-y^2=3$ above $z=0$), while $(1,2)$ gives $z = 1-4 = -3$ (on the hyperbola $y^2-x^2=3$ below $z=0$). ✓

## A concrete example

Imagine walking across the origin $(0,0,0)$ on the surface $z=x^2-y^2$:
- If you walk along the $x$-axis ($y=0$), your elevation is $z=x^2$, so $(0,0,0)$ is the bottom of a valley.
- If you walk along the $y$-axis ($x=0$), your elevation is $z=-y^2$, so $(0,0,0)$ is the top of a mountain ridge.
- If you walk diagonally along $y=x$, your elevation is $z=x^2-x^2=0$, so you walk along a completely flat horizontal straight line!

## How I would explain this in class

> Both $z=x^2+y^2$ and $z=x^2-y^2$ are paraboloids because $z$ is in the first power and $x,y$ are squared. For $z=x^2+y^2$, setting $x=0$ or $y=0$ gives upward-opening parabolas $z=y^2$ and $z=x^2$, and horizontal slices $z=c>0$ are circles of radius $\sqrt{c}$, forming a rotational bowl above $z=0$. For $z=x^2-y^2$, the slice $y=0$ is an upward parabola $z=x^2$ while $x=0$ is a downward parabola $z=-y^2$; horizontal slices are hyperbolas opening along $Ox$ for $c>0$, two crossed lines $y=\pm x$ for $c=0$, and hyperbolas opening along $Oy$ for $c<0$, giving a saddle surface.

## Related workbook topics

- [Exercise 4: Parabola](problem_04_solution.md)
- [Exercise 12: Recognizing a Surface from Cross-Sections](problem_12_solution.md)
