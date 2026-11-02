# Exercise 11. Two Similar Surfaces

## The question

Compare

$$x^2+y^2-z^2=1$$

and

$$x^2+y^2-z^2=-1.$$

For several values $z=c$, check whether the cross-section exists and what its radius is. Based on this, describe qualitatively the difference between the surfaces and make sketches.

## Before calculating: what idea do we need?

Both surfaces have the exact same left-hand side $x^2+y^2-z^2$ and differ only in the sign of the right-hand side ($+1$ vs. $-1$). To see what each surface looks like without memorizing names, we move $-z^2$ to the right-hand side and slice with horizontal planes $z=c$:

- First surface: $x^2+y^2 = 1 + c^2$.
- Second surface: $x^2+y^2 = c^2 - 1$.

In each plane $z=c$, the equation $x^2+y^2 = R^2$ describes a circle of radius $R$ whenever the right-hand side is positive, a single point when it is $0$, and the empty set when it is negative.

## 1. First surface: $x^2+y^2-z^2 = 1$

For $z=c$, the horizontal slice is

$$x^2+y^2 = 1 + c^2.$$

Since $1+c^2 \ge 1 > 0$ for **every** real number $c\in\mathbb{R}$, the cross-section **always exists** and is a circle of radius

$$r_1(c) = \sqrt{1+c^2}.$$

Let us check several values of $z=c$:
- $c = 0$: circle $x^2+y^2=1$, radius $r_1(0) = 1$ (the narrowest "waist" or "neck" of the surface).
- $c = \pm 1$: circle $x^2+y^2=2$, radius $r_1(\pm 1) = \sqrt{2} \approx 1.41$.
- $c = \pm 2$: circle $x^2+y^2=5$, radius $r_1(\pm 2) = \sqrt{5} \approx 2.24$.

Because a circle exists at every height $z=c$, all these circles stack continuously into **one connected piece** shaped like a cooling tower (**hyperboloid of one sheet**).

## 2. Second surface: $x^2+y^2-z^2 = -1$

For $z=c$, the horizontal slice is

$$x^2+y^2 = c^2 - 1.$$

Here a real cross-section exists **only when $c^2 - 1 \ge 0 \iff |c| \ge 1$**:
- $c = 0$: $x^2+y^2 = -1$, **does not exist** (empty set). In fact, for any $|c|<1$, there are no real points!
- $c = \pm 1$: $x^2+y^2 = 0$, a **single point** $(0,0,1)$ and $(0,0,-1)$ (radius $r_2(\pm 1) = 0$).
- $c = \pm\sqrt{2}$: circle $x^2+y^2 = 1$, radius $r_2(\pm\sqrt{2}) = 1$.
- $c = \pm 2$: circle $x^2+y^2 = 3$, radius $r_2(\pm 2) = \sqrt{3} \approx 1.73$.

In general, for $|c|\ge 1$, the slice is a circle of radius $r_2(c) = \sqrt{c^2-1}$. Because the slab $-1 < z < 1$ is completely empty, the surface is split into **two separate bowls**—one opening upward for $z\ge 1$ and one opening downward for $z\le -1$ (**hyperboloid of two sheets**).

## 3. Comparison table of horizontal cross-sections

| Height $z=c$ | First Surface: $x^2+y^2 = 1+c^2$ | Second Surface: $x^2+y^2 = c^2-1$ |
| :---: | :--- | :--- |
| $c = 0$ | Circle, $r = 1$ (narrowest waist) | Empty ($c^2-1 = -1 < 0$) |
| $c = \pm 0.5$ | Circle, $r = \sqrt{1.25} \approx 1.12$ | Empty ($c^2-1 = -0.75 < 0$) |
| $c = \pm 1$ | Circle, $r = \sqrt{2} \approx 1.41$ | Single points $(0,0,\pm 1)$ ($r = 0$) |
| $c = \pm 2$ | Circle, $r = \sqrt{5} \approx 2.24$ | Circle, $r = \sqrt{3} \approx 1.73$ |
| $c = \pm 3$ | Circle, $r = \sqrt{10} \approx 3.16$ | Circle, $r = \sqrt{8} \approx 2.83$ |

## 4. Qualitative difference and sketches

- **$x^2+y^2-z^2=1$ (Hyperboloid of one sheet):** One connected, hourglass/cooling-tower tube surrounding the $z$-axis, narrowest at $z=0$ ($r=1$) and flaring out as $|z|\to\infty$.
- **$x^2+y^2-z^2=-1$ (Hyperboloid of two sheets):** Two disconnected sheets separated by the forbidden gap $-1<z<1$, with vertices at $(0,0,1)$ and $(0,0,-1)$.

```text
   x^2 + y^2 - z^2 = 1                  x^2 + y^2 - z^2 = -1
  (One connected sheet)                 (Two separate sheets)

           z                                      z
     \     |     /                          \     |     /
      \  .-+-.  /                            \  .-+-.  /
       )|  |  |(  r=1 at z=0                  '---*---'  (0,0,1)
  -----+-*-+-*-+----- x,y               ----------+---------- x,y
       )|  |  |(                               .---*---.  (0,0,-1)
      /  '-+-'  \                            /  '-+-'  \
     /     |     \                          /     |     \
```

## Quick verification

Look at the vertical slice $y=0$ (in the $xz$-plane) for both surfaces:
- First surface ($y=0$): $x^2-z^2 = 1$, a hyperbola opening left/right with vertices $(\pm 1,0,0)$. Rotating this around the $z$-axis sweeps out a single connected tube of minimum radius $1$. ✓
- Second surface ($y=0$): $z^2-x^2 = 1$, a hyperbola opening up/down with vertices $(0,0,\pm 1)$. Rotating this around the $z$-axis sweeps out two separate bowls. ✓

## A concrete example

Notice that both surfaces share the exact same asymptotic cone $x^2+y^2-z^2=0$ (where $r(c)=|c|$): at $z=10$, the first surface has radius $\sqrt{101}\approx 10.05$, the cone has radius $10$, and the second surface has radius $\sqrt{99}\approx 9.95$. Far from the origin, both surfaces hug the cone $x^2+y^2=z^2$, one just outside it and the other just inside it.

## How I would explain this in class

> I rewrite the equations as $x^2+y^2 = 1+z^2$ and $x^2+y^2 = z^2-1$ and slice with $z=c$. For the first equation, $1+c^2$ is always at least $1$, so every horizontal slice is a circle of radius $\sqrt{1+c^2}$: it starts with a waist of radius $1$ at $z=0$ and flares out into a single connected hourglass (a hyperboloid of one sheet). For the second equation, $c^2-1$ is negative for $|c|<1$, so there are no points between $z=-1$ and $z=1$; at $z=\pm 1$ we get two points $(0,0,\pm 1)$, and for $|c|>1$ we get circles of radius $\sqrt{c^2-1}$, forming two separate bowls (a hyperboloid of two sheets).

## Related workbook topics

- [Exercise 5: Hyperbola and Asymptotes](problem_05_solution.md)
- [Exercise 14: Cone and Cylinder](problem_14_solution.md)
