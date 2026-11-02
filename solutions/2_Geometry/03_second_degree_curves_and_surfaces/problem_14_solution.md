# Exercise 14. Cone and Cylinder

## The question

Compare

$$x^2+y^2=z^2$$

and

$$x^2+y^2=4.$$

For each surface, describe the cross-sections $z=c$, $x=0$, and $y=0$, make a sketch, and explain why the radius of the cross-section depends on $z$ in the first case but is constant in the second.

## Before calculating: what idea do we need?

In three-dimensional space $(x,y,z)$, the quantity $\sqrt{x^2+y^2}$ is the **horizontal distance** of a point $(x,y,z)$ from the vertical $Oz$ axis:

- In $x^2+y^2 = z^2$, the squared distance from the $z$-axis is set equal to $z^2$, so the distance grows proportionally with $|z|$ (**circular cone**).
- In $x^2+y^2 = 4$, the variable $z$ does not appear in the equation at all! That means $z$ is completely free while the distance from the $z$-axis is locked at $2$ (**circular cylinder**).

## 1. First surface: $x^2+y^2 = z^2$ (Circular Cone)

Let us find its cross-sections:
- **Horizontal cross-sections $z=c$:** $x^2+y^2 = c^2$.
  - For $c = 0$: $x^2+y^2 = 0$, a **single point** $(0,0,0)$ (the apex/vertex of the cone).
  - For $c \neq 0$: a **circle** of radius $r(c) = \sqrt{c^2} = |c|$, growing linearly with $|c|$.
- **Vertical cross-section $x=0$ (in the $yz$-plane):** $y^2 = z^2 \iff z = \pm y$, a **pair of intersecting straight lines** passing through the origin at $45^\circ$.
- **Vertical cross-section $y=0$ (in the $xz$-plane):** $x^2 = z^2 \iff z = \pm x$, a **pair of intersecting straight lines** passing through the origin at $45^\circ$.

```text
          z
     \    |    /   z = c: circle of radius |c|
      \ .-+-./
       \  |  /     x=0 or y=0: crossed lines z = +-x, z = +-y
        \ | /
         \|/ (0,0,0) apex
  --------+-------- x, y
         /|\
        / | \
       /.-+-.\
      /   |   \
```

## 2. Second surface: $x^2+y^2 = 4$ (Circular Cylinder)

Now find the cross-sections of $x^2+y^2 = 4$ in $\mathbb{R}^3$:
- **Horizontal cross-sections $z=c$:** $x^2+y^2 = 4$. For **every** real value $c\in\mathbb{R}$, this is the exact same **circle** of radius $r = \sqrt{4} = 2$ centered at $(0,0,c)$.
- **Vertical cross-section $x=0$ (in the $yz$-plane):** $0 + y^2 = 4 \iff y = \pm 2$ (with $z$ arbitrary). This is a **pair of parallel vertical lines** $(0,2,z)$ and $(0,-2,z)$.
- **Vertical cross-section $y=0$ (in the $xz$-plane):** $x^2 + 0 = 4 \iff x = \pm 2$ (with $z$ arbitrary). This is a **pair of parallel vertical lines** $(2,0,z)$ and $(-2,0,z)$.

```text
          z
      | .-f-. |    z = c: circle of constant radius 2
      | '---' |
      |   |   |    x=0: parallel lines y = +-2
  ----+---+---+---- x, y
      |   |   |    y=0: parallel lines x = +-2
      | .-f-. |
      | '---' |
```

## 3. Why the radius depends on $z$ in the first case but is constant in the second

In any horizontal plane $z=c$, the left-hand side $x^2+y^2$ represents $r^2$, the square of the horizontal radius:

- **In $x^2+y^2=z^2$:** The right-hand side is $z^2$, which **explicitly contains $z$**. When we slice at height $z=c$, the equation sets $r^2 = c^2$, forcing the radius $r = |c|$ to scale directly with the height $|z|$.
- **In $x^2+y^2=4$:** The right-hand side is the constant $4=2^2$, and the variable **$z$ is absent** from the equation (its coefficient is $0\cdot z^2 + 0\cdot z$). Because the equation places no restriction on $z$ and does not link $x,y$ to $z$, shifting the slice to any height $z=c$ leaves the 2D equation $x^2+y^2=4$ unchanged, so the radius stays constant at $r=2$.

## Quick verification

Let us check what happens to the point $(2,0,z)$ on both surfaces:
- On the cylinder $x^2+y^2=4$: $2^2+0^2=4$ holds for **every** $z\in\mathbb{R}$, confirming the vertical line $(2,0,z)$ lies entirely on the cylinder. ✓
- On the cone $x^2+y^2=z^2$: $2^2+0^2=z^2 \implies z=\pm 2$, so a radius of $2$ occurs **only** at the two heights $z=2$ and $z=-2$. ✓

## A concrete example

Compare the horizontal slices at heights $z=0, 1, 2, 3$:

| Height $z=c$ | Cone $x^2+y^2=z^2$ radius $r=|c|$ | Cylinder $x^2+y^2=4$ radius $r=2$ |
| :---: | :---: | :---: |
| $z=0$ | $0$ (point) | $2$ |
| $z=1$ | $1$ | $2$ |
| $z=2$ | $2$ (cone & cylinder intersect!) | $2$ |
| $z=3$ | $3$ | $2$ |

In fact, the cone $x^2+y^2=z^2$ and the cylinder $x^2+y^2=4$ intersect precisely in the two circles at $z=2$ and $z=-2$ where $|z|=2$.

## How I would explain this in class

> Both equations have $x^2+y^2$ on the left, so every horizontal slice $z=c$ is a circle (or a point). In $x^2+y^2=z^2$, the right-hand side depends on $z$, so at height $z=c$ the radius is $r=|c|$; it shrinks to a point at $z=0$ and its vertical slices $x=0$ and $y=0$ are crossed lines $z=\pm y$ and $z=\pm x$, forming a double cone. In $x^2+y^2=4$, the variable $z$ does not appear at all, so at every height $z=c$ we get the exact same circle of radius $r=2$, and its vertical slices $x=0$ and $y=0$ are parallel vertical lines $y=\pm 2$ and $x=\pm 2$, forming an infinite vertical cylinder.

## Related workbook topics

- [Exercise 11: Two Similar Surfaces](problem_11_solution.md)
- [Exercise 15: Recognition and Sketch Without a Given Name](problem_15_solution.md)
