# Exercise 11. Volume of a Solid of Revolution

## The question

The region under the graph

$$y=\sqrt{x},\qquad x\in[0,4],$$

is rotated about the $x$-axis.

1. Construct the integral describing the volume using the disk method.
2. Compute the volume.
3. Explain where the factor $\pi y^2$ in the integral comes from.

## Before calculating: what idea do we need?

When a planar region under $y=f(x)$ ($f(x)\ge 0$) on $[a,b]$ is rotated a full $360^\circ$ around the $x$-axis, it sweeps out a three-dimensional solid of revolution. If we slice this solid perpendicular to the $x$-axis at position $x$ with a thin slab of thickness $dx$, the cross-section is a circle of radius $R(x)=y=f(x)$. Summing the volumes of these thin circular disks via an integral gives the total volume.

## 1. Constructing the volume integral (disk method)

At each point $x\in[0,4]$, the distance from the axis of rotation (the $x$-axis) to the boundary curve $y=\sqrt{x}$ is the disk radius

$$R(x) = y = \sqrt{x}.$$

The cross-sectional area of the circular slice at $x$ is

$$A(x) = \pi [R(x)]^2 = \pi(\sqrt{x})^2 = \pi x.$$

Integrating the cross-sectional area $A(x)$ from $x=0$ to $x=4$ yields the volume integral:

$$V = \int_0^4 \pi (\sqrt{x})^2\,dx = \pi \int_0^4 x\,dx.$$

## 2. Computing the volume

Evaluating the definite integral using the Fundamental Theorem of Calculus:

$$V = \pi \left[\frac{x^2}{2}\right]_0^4 = \pi\left(\frac{4^2}{2}-\frac{0^2}{2}\right) = \pi\cdot\frac{16}{2} = 8\pi \approx 25.13.$$

## 3. Where the factor $\pi y^2$ comes from

Let us trace the geometry of a single vertical strip at position $x$ of height $y=f(x)$ and infinitesimal width $dx$:
1. Before rotation, the strip is a thin rectangle of height $y$ and width $dx$ resting on the $x$-axis.
2. As the graph revolves around the $x$-axis, the top point $(x,y)$ traces a circle of radius $r=y$ in the plane perpendicular to the $x$-axis.
3. The area of a circle of radius $r=y$ is $\pi r^2 = \pi y^2$.
4. Multiplying the circular face area $\pi y^2$ by the slab thickness $dx$ gives the volume of an elemental cylinder (disk):

$$dV = (\text{area of circular face})\times(\text{thickness}) = \pi y^2\,dx.$$

## 4. Special property of the paraboloid of revolution

Rotating $y=\sqrt{x}$ around the $x$-axis produces a **paraboloid** (since $y^2=x$, the 3D surface is $y^2+z^2=x$). Because the cross-sectional area $A(x)=\pi y^2=\pi x$ grows **linearly** with $x$, the average cross-sectional area on $[0,4]$ is simply half the base area at $x=4$.

## Quick verification

We can verify $V=8\pi$ by comparing our paraboloid of height $H=4$ and base radius $R=\sqrt{4}=2$ against inscribed and circumscribed standard solids:

- **Circumscribed cylinder** of radius $R=2$ and height $H=4$: $V_{\text{cyl}}=\pi R^2 H = \pi(2^2)(4)=16\pi$.
- **Inscribed cone** sharing the vertex $(0,0)$ and circular base at $x=4$: $V_{\text{cone}}=\frac{1}{3}\pi R^2 H = \frac{16\pi}{3}\approx 5.33\pi$.
- Our paraboloid lies strictly outside the cone (since $\sqrt{x}>\frac{x}{2}$ on $(0,4)$) and inside the cylinder, and satisfies Archimedes' classic paraboloid theorem:

$$V_{\text{paraboloid}} = \frac{1}{2}V_{\text{cyl}} = \frac{1}{2}(16\pi) = 8\pi, \qquad \frac{16\pi}{3} < 8\pi < 16\pi. \quad \checkmark$$

## A concrete example

Headlight reflectors and satellite dishes are shaped as paraboloids of revolution. If a laboratory glass cup has an interior profile $y=\sqrt{x}$ (with $x$ and $y$ in centimeters) and depth $4\text{ cm}$ (so its rim has radius $2\text{ cm}$ and diameter $4\text{ cm}$), its capacity is $8\pi\approx 25.13\text{ cm}^3$ ($\text{mL}$)—exactly half the volume of a straight cylindrical cup of the same depth and rim diameter ($16\pi\approx 50.27\text{ mL}$).

## How I would explain this in class

> Rotating the curve $y=\sqrt{x}$ around the $x$-axis turns each vertical segment of height $y$ at coordinate $x$ into a circular disk of radius $y$. Since a circle of radius $y$ has area $\pi y^2$, a thin disk of thickness $dx$ has volume $\pi y^2\,dx$. Substituting $y=\sqrt{x}$ gives $(\sqrt{x})^2=x$, so the volume integral is $\int_0^4 \pi x\,dx = \pi\bigl[\frac{x^2}{2}\bigr]_0^4 = 8\pi$, which is exactly half the volume of the surrounding cylinder of radius $2$ and length $4$.

## Related workbook topics

- [Exercise 4: Area Between Curves](problem_04_solution.md)
- [Exercise 6: Average Value of a Function](problem_06_solution.md)
