# Exercise 13. Intersection of a Sphere and a Plane

## The question

Given the sphere

$$x^2+y^2+z^2=25$$

and the plane $z=3$, find the equation of the intersection curve and its radius. Then describe what happens for $z=c$ depending on $c$.

## Before calculating: what idea do we need?

The equation $x^2+y^2+z^2=25$ describes a sphere centered at the origin $(0,0,0)$ with radius $R = \sqrt{25} = 5$.

A point lies on the intersection of the sphere and the horizontal plane $z=c$ if and only if its coordinates satisfy **both equations simultaneously**. Algebraically, we substitute $z=c$ into the sphere's equation; geometrically, $c^2 + r^2 = R^2$ forms a right triangle with hypotenuse $R=5$ (sphere radius), vertical leg $|c|$ (plane height), and horizontal leg $r = \sqrt{25-c^2}$ (cross-section radius).

## 1. Intersection curve and radius for $z=3$

Substitute $z=3$ into $x^2+y^2+z^2=25$:

$$x^2 + y^2 + 3^2 = 25 \implies x^2 + y^2 + 9 = 25 \implies x^2 + y^2 = 16.$$

Thus, the intersection curve is given by the system

$$\begin{cases} x^2+y^2 = 16, \\ z = 3. \end{cases}$$

Geometrically, this is a **circle** lying in the horizontal plane $z=3$, centered at $(0,0,3)$ on the $z$-axis, with **radius**

$$r = \sqrt{16} = 4.$$

```text
          z
         5* (0,0,5) North pole
      *   |   *
    *  r=4|     *
   *------*------*  <-- Plane z = 3: circle x^2+y^2 = 16
   |      |3   / |
  -+------+---/--+-- x, y
   |      |0/R=5 |
```

## 2. What happens for $z=c$ depending on $c$

Substitute a general height $z=c$ into $x^2+y^2+z^2=25$:

$$x^2 + y^2 = 25 - c^2.$$

Depending on the sign of $25-c^2$, there are three distinct geometric regimes:

1. **Case 1: $|c| < 5$ (i.e., $-5 < c < 5$):**
   Here $25-c^2 > 0$. The plane cuts through the interior of the sphere, and the intersection is a **circle** centered at $(0,0,c)$ of radius
   $$r(c) = \sqrt{25-c^2}.$$
   - At $c=0$ (the equator), the radius is maximal: $r(0) = 5$.
   - As $|c|$ increases from $0$ toward $5$, the circle shrinks.

2. **Case 2: $|c| = 5$ (i.e., $c = 5$ or $c = -5$):**
   Here $25-c^2 = 0$, so $x^2+y^2 = 0 \implies x=0,\;y=0$. The plane is **tangent** to the sphere at the north pole $(0,0,5)$ or south pole $(0,0,-5)$, so the intersection is a **single point** (a degenerate circle of radius $r=0$).

3. **Case 3: $|c| > 5$ (i.e., $c > 5$ or $c < -5$):**
   Here $25-c^2 < 0$. Since $x^2+y^2\ge 0$ for all real $x,y$, there are **no real solutions**. The plane passes completely above or below the sphere, so the intersection is the **empty set**.

## 3. Summary table across values of $c$

| Parameter $c$ | Equation $x^2+y^2 = 25-c^2$ | Intersection Geometry | Radius $r(c)$ |
| :---: | :---: | :--- | :---: |
| $c = 0$ | $x^2+y^2 = 25$ | Great circle (equator) | $5$ |
| $c = \pm 3$ | $x^2+y^2 = 16$ | Circle in plane $z=\pm 3$ | $4$ |
| $c = \pm 4$ | $x^2+y^2 = 9$ | Circle in plane $z=\pm 4$ | $3$ |
| $c = \pm 5$ | $x^2+y^2 = 0$ | Single tangent point $(0,0,\pm 5)$ | $0$ |
| $|c| > 5$ | $x^2+y^2 < 0$ | Empty set (no intersection) | — |

## Quick verification

Pick a point on the circle $x^2+y^2=16$ in the plane $z=3$, for instance $(4,0,3)$ or $(0,-4,3)$:

$$4^2 + 0^2 + 3^2 = 16 + 0 + 9 = 25.$$

It satisfies the sphere equation $x^2+y^2+z^2=25$ and has $z=3$. ✓

## A concrete example

Notice the Pythagorean triple $(3,4,5)$:
- When we slice at height $z=3$, the circle has radius $r=4$.
- When we slice higher at height $z=4$, the circle has radius $r=\sqrt{25-4^2}=3$.
Swapping the height $3$ and $4$ swaps the horizontal radius $4$ and $3$ because $3^2+4^2=5^2$.

## How I would explain this in class

> Plugging $z=3$ into the sphere equation $x^2+y^2+z^2=25$ gives $x^2+y^2=25-9=16$, which is a circle of radius $r=4$ centered at $(0,0,3)$ in the plane $z=3$. More generally, for any plane $z=c$ we get $x^2+y^2=25-c^2$: for $|c|<5$ the intersection is a circle of radius $\sqrt{25-c^2}$ (largest at $c=0$ with radius $5$, shrinking as $|c|$ grows); for $c=\pm 5$ the plane just touches the north or south pole in a single point $(0,0,\pm 5)$; and for $|c|>5$ the right-hand side is negative, so the plane misses the sphere completely.

## Related workbook topics

- [Exercise 8: Sphere](problem_08_solution.md)
- [Exercise 9: Ellipsoid and Its Cross-Sections](problem_09_solution.md)
