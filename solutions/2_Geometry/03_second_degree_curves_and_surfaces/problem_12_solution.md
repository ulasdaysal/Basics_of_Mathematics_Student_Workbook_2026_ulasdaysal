# Exercise 12. Recognizing a Surface from Cross-Sections

## The question

A certain surface has the following properties:
- the cross-section $z=0$ is a point,
- for $z>0$, the cross-sections $z=\text{const}$ are circles with increasing radius,
- vertical cross-sections through the $Oz$ axis are parabolas.

Propose a simple equation for such a surface and justify your choice.

## Before calculating: what idea do we need?

Here we reverse the usual workflow: instead of starting from an equation and finding its slices, we **translate each geometric slice condition into an algebraic requirement** on $x,y,z$:

1. Horizontal cross-sections $z=\text{const}$ are **circles** centered on the $z$-axis $\implies x$ and $y$ must appear together in the rotational combination $x^2+y^2$.
2. Vertical cross-sections through the $Oz$ axis are **parabolas** $\implies$ the height $z$ must be a **first-degree** (linear) term while the horizontal distance is squared.

## 1. Translating the circular cross-sections into algebra

Since every horizontal cross-section $z=c$ ($c>0$) is a circle centered on the $Oz$ axis, the equation in the plane $z=c$ must have the form

$$x^2+y^2 = r(c)^2,$$

where $r(c)>0$ is the radius of the circle at height $z=c$, and $r(c)$ increases with $c$.

## 2. Using the vertical cross-sections to determine $r(c)^2$

The third property states that vertical planes through the $Oz$ axis—for example, the plane $y=0$ (the $xz$-plane) or $x=0$ (the $yz$-plane)—cut the surface in **parabolas**.

- In the plane $y=0$, our equation $x^2+y^2 = f(z)$ becomes $x^2 = f(z)$.
- For $x^2 = f(z)$ to be a parabola opening upward from $z=0$, $f(z)$ must be a positive constant multiple of $z$ (the simplest choice is $f(z)=z$).

*(Note: If we chose $f(z)=z^2$, then $x^2=z^2 \iff z=\pm x$ would give straight lines—a cone—rather than parabolas!)*

## 3. Proposed equation and full justification

The simplest equation satisfying all three conditions is the circular paraboloid:

$$z = x^2+y^2.$$

Let us verify each of the three given properties directly from $z = x^2+y^2$:

1. **Cross-section $z=0$ is a point:**
   Setting $z=0$ gives $x^2+y^2=0$. Since $x^2\ge 0$ and $y^2\ge 0$ for real $x,y$, the only real solution is the single point $(0,0,0)$.
2. **For $z>0$, cross-sections $z=c$ are circles with increasing radius:**
   Setting $z=c>0$ gives $x^2+y^2=c$, which is a circle of radius $r(c)=\sqrt{c}$. Because $\sqrt{c}$ is strictly increasing for $c>0$, the radius grows as $c$ increases.
3. **Vertical cross-sections through $Oz$ are parabolas:**
   Any vertical plane through the $Oz$ axis is parameterized by setting $x = t\cos\theta$, $y = t\sin\theta$ where $t\in\mathbb{R}$ is the signed horizontal coordinate in that plane. Substituting into $z=x^2+y^2$ gives
   $$z = t^2(\cos^2\theta+\sin^2\theta) = t^2,$$
   which is a standard parabola in every vertical plane through $Oz$ (in particular, $z=x^2$ when $y=0$ and $z=y^2$ when $x=0$).

## Quick verification

Let us check a few concrete slices of $z=x^2+y^2$:
- At $z=0$: $x^2+y^2=0 \implies (0,0,0)$ (1 point). ✓
- At $z=1$: $x^2+y^2=1$ (circle of radius $1$). ✓
- At $z=4$: $x^2+y^2=4$ (circle of radius $2 > 1$). ✓
- At $y=0$: $z=x^2$ (parabola). ✓

*(Any positive scaling $z = a(x^2+y^2)$ with $a>0$ is also a valid answer.)*

## A concrete example

Why couldn't the surface be the upper half-cone $z = \sqrt{x^2+y^2}$ (i.e., $x^2+y^2=z^2$ for $z\ge 0$)?
- For the cone, $z=0$ is also a point $(0,0,0)$, and $z=c>0$ is also a circle of increasing radius $r=c$.
- **However**, setting $y=0$ on the cone gives $z=|x|$, which is a V-shaped pair of rays, **not a smooth parabola**. The third condition ("vertical cross-sections through $Oz$ are parabolas") uniquely picks out the quadratic relation $z = x^2+y^2$ instead of $z^2 = x^2+y^2$.

## How I would explain this in class

> Because the horizontal slices $z=c>0$ are circles centered on the $z$-axis, $x$ and $y$ must appear as $x^2+y^2$. Because the vertical slices through the $z$-axis (like $x=0$ or $y=0$) are parabolas, $z$ must be in the first power while $x$ and $y$ are squared. Putting those together with the vertex at $z=0$ gives $z=x^2+y^2$: at $z=0$ we get the single point $(0,0,0)$, for $z=c>0$ we get circles $x^2+y^2=c$ of increasing radius $\sqrt{c}$, and slicing with $x=0$ or $y=0$ gives the parabolas $z=y^2$ and $z=x^2$.

## Related workbook topics

- [Exercise 10: Paraboloids](problem_10_solution.md)
- [Exercise 14: Cone and Cylinder](problem_14_solution.md)
