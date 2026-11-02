# Exercise 9. Minimizing the Material Used for a Can

## The question

A closed right circular cylinder has a fixed volume $V>0$.

1. Write the volume constraint.
2. Eliminate one of the variables.
3. Express the total surface area as a function of the radius $r$.
4. Find the relation between the height $h$ and the radius $r$ for which the material usage (surface area) is minimal, and interpret the obtained relation geometrically.

## Before calculating: what idea do we need?

A closed cylindrical can of base radius $r>0$ and height $h>0$ consists of:
- **Two circular bases** (top and bottom), each of area $\pi r^2$,
- **A lateral wall**, which unrolls into a rectangle of circumference $2\pi r$ and height $h$, having area $2\pi rh$.

Thus the total surface area is $S=2\pi r^2+2\pi rh$. Because the volume $V=\pi r^2 h$ is fixed, choosing $r$ automatically determines $h$. Eliminating $h$ gives a single-variable function $S(r)$ on $(0,\infty)$ that balances wide, flat cans (huge base area) against tall, thin cans (huge lateral area).

## 1. Writing the volume constraint

The volume of a cylinder with base radius $r>0$ and height $h>0$ is

$$V = \pi r^2 h.$$

## 2. Eliminating one of the variables

Since $r>0$, we can solve the volume constraint easily for the first-power variable $h$:

$$h = \frac{V}{\pi r^2}.$$

## 3. Expressing the surface area as a function of $r$

The total surface area of the closed cylinder is

$$S(r,h) = 2\pi r^2 + 2\pi rh.$$

Substituting $h=\dfrac{V}{\pi r^2}$ into this expression eliminates $h$:

$$S(r) = 2\pi r^2 + 2\pi r\left(\frac{V}{\pi r^2}\right) = 2\pi r^2 + \frac{2V}{r},\qquad r\in(0,\infty).$$

## 4. Finding the optimal relation between $h$ and $r$ and its geometric meaning

We differentiate $S(r)=2\pi r^2 + 2Vr^{-1}$ with respect to $r$:

$$S'(r) = 4\pi r - \frac{2V}{r^2} = \frac{4\pi r^3 - 2V}{r^2}.$$

Setting $S'(r)=0$ gives

$$4\pi r^3 - 2V = 0 \iff 2\pi r^3 = V \implies r = \sqrt[3]{\frac{V}{2\pi}}.$$

To find the direct relation between $h$ and $r$ at the optimum without carrying cube roots, we substitute $V=\pi r^2 h$ back into the optimality condition $2\pi r^3 = V$:

$$2\pi r^3 = \pi r^2 h \implies h = 2r.$$

To verify that this critical point is a global minimum on $(0,\infty)$, compute the second derivative:

$$S''(r) = 4\pi + \frac{4V}{r^3} > 0 \qquad\text{for all } r>0.$$

Since $S''(r)>0$ everywhere on $(0,\infty)$, $S(r)$ is strictly convex and $h=2r$ gives the unique global minimum.

**Geometric interpretation:** Since $2r=d$ is the diameter of the base, the relation $h=2r$ means the cylinder's **height equals its diameter**. If you slice the optimal can vertically through its central axis, the cross-section is a **square** of side $2r\times 2r$ (and the can fits snugly inside a cube of side $2r$).

## Quick verification

Let us check the sign of $S'(r)=\frac{2(2\pi r^3-V)}{r^2}$ around $r^*=\sqrt[3]{\frac{V}{2\pi}}$ and check the surface area split:

- For $0<r<r^*$, $2\pi r^3<V$, so $S'(r)<0$ ($S$ decreases). For $r>r^*$, $2\pi r^3>V$, so $S'(r)>0$ ($S$ increases). ✓
- At $h=2r$, the two bases have area $2\pi r^2$ and the lateral wall has area $2\pi r(2r)=4\pi r^2$, so the lateral wall uses exactly twice the material of the two lids combined, giving $S_{\min}=6\pi r^2$. ✓

## A concrete example

Suppose a beverage company designs a closed cylindrical can of volume $V=1000\text{ cm}^3$ ($1\text{ liter}$):
- **Optimal square-profile can ($h=2r$):** $r=\sqrt[3]{\frac{1000}{2\pi}}\approx 5.42\text{ cm}$ and $h\approx 10.84\text{ cm}$, which requires $S\approx 553.6\text{ cm}^2$ of aluminum.
- **Tall, slim can ($r=3\text{ cm}$):** $h=\frac{1000}{9\pi}\approx 35.37\text{ cm}$, requiring $S=18\pi+\frac{2000}{3}\approx 723.2\text{ cm}^2$ ($30.6\%$ more metal!).
- **Wide, flat tin ($r=10\text{ cm}$):** $h=\frac{1000}{100\pi}\approx 3.18\text{ cm}$, requiring $S=200\pi+200\approx 828.3\text{ cm}^2$ ($49.6\%$ more metal!).

## How I would explain this in class

> A closed cylinder has volume $V=\pi r^2 h$ and surface area $S=2\pi r^2+2\pi rh$ (two circular lids plus the side wall). Solving the volume equation for $h=\frac{V}{\pi r^2}$ and plugging it into $S$ gives $S(r)=2\pi r^2+\frac{2V}{r}$ for $r>0$. Differentiating gives $S'(r)=4\pi r-\frac{2V}{r^2}=0$, so $V=2\pi r^3$. Replacing $V$ with $\pi r^2 h$ yields $\pi r^2 h = 2\pi r^3$, which simplifies to $h=2r$. Because $S''(r)=4\pi+\frac{4V}{r^3}>0$, this is a minimum: the most material-efficient closed can has height equal to its base diameter, so its vertical cross-section is a square.

## Related workbook topics

- [Exercise 2: Maximum Area of a Rectangle](problem_02_solution.md)
- [Exercise 3: A Box Made from Cardboard](problem_03_solution.md)
