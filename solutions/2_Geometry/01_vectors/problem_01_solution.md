# Exercise 1. Vector Operations and Their Meaning

## The question

For $u=(2,-1,3)$ and $v=(-1,4,2)$ compute

$$u+v,\qquad u-v,\qquad 3u-2v.$$

Then verify that $(u+v)-v=u$, and explain geometrically what adding two vectors means.

## Before calculating: what idea do we need?

In $\mathbb R^3$, vector addition, subtraction, and scalar multiplication act **component by component**:

- **Addition** combines two displacements performed one after another.
- **Subtraction** $u-v=u+(-v)$ adds the opposite of $v$, or represents the displacement needed to go from the tip of $v$ to the tip of $u$.
- **Scalar multiplication** stretches or shrinks a vector by a factor (and reverses its orientation if the factor is negative) before we combine it with another vector.

## 1. Vector sum $u+v$

We add corresponding coordinates:

$$u+v = (2,-1,3) + (-1,4,2) = (2+(-1),\, -1+4,\, 3+2) = (1,3,5).$$

## 2. Vector difference $u-v$

We subtract the coordinates of $v$ from the coordinates of $u$:

$$u-v = (2,-1,3) - (-1,4,2) = (2-(-1),\, -1-4,\, 3-2) = (3,-5,1).$$

## 3. Linear combination $3u-2v$

First we scale each vector separately:

$$3u = 3(2,-1,3) = (6,-3,9),\qquad 2v = 2(-1,4,2) = (-2,8,4).$$

Now we subtract $2v$ from $3u$:

$$3u-2v = (6,-3,9) - (-2,8,4) = (6-(-2),\, -3-8,\, 9-4) = (8,-11,5).$$

## 4. Geometric meaning of vector addition

Geometrically, each vector represents a **directed displacement** in space:

- **Tip-to-tail rule (triangle law):** Start at the origin, move along $u$ to reach $(2,-1,3)$, and from there move by $v=(-1,4,2)$. You land at $u+v=(1,3,5)$. The sum vector is the direct shortcut from the starting point to the final point.
- **Parallelogram law:** Place $u$ and $v$ with the same starting point. They span a parallelogram, and $u+v$ is the diagonal starting at their common origin.

Subtracting $v$ after adding $v$ simply walks back along $-v$ from the tip of $u+v$ to the tip of $u$.

## Quick verification

We check that $(u+v)-v=u$ directly using our computed sum $u+v=(1,3,5)$:

$$(u+v)-v = (1,3,5) - (-1,4,2) = (1-(-1),\, 3-4,\, 5-2) = (2,-1,3) = u.\quad \checkmark$$

We can also check the linear combination $3u-2v$ by using the algebraic identity $3u-2v = (u+v) + 2(u-v) - v$:

$$(1,3,5) + 2(3,-5,1) - (-1,4,2) = (1+6+1,\, 3-10-4,\, 5+2-2) = (8,-11,5).\quad \checkmark$$

## A concrete example

Imagine walking in a room where coordinates $(x,y,z)$ are measured in meters (east, north, up):

- Displacement $u=(2,-1,3)$ moves you $2\text{ m}$ east, $1\text{ m}$ south, and $3\text{ m}$ up.
- Displacement $v=(-1,4,2)$ moves you $1\text{ m}$ west, $4\text{ m}$ north, and $2\text{ m}$ up.

Combined, your net change in position is $u+v=(1,3,5)$: $1\text{ m}$ east, $3\text{ m}$ north, and $5\text{ m}$ up. If you then undo the second move by applying $-v=(1,-4,-2)$, you return to $(2,-1,3)$, which is your position after $u$ alone.

## How I would explain this in class

> Vector operations in $\mathbb R^3$ happen coordinate by coordinate. Adding $u$ and $v$ gives $(1,3,5)$, subtracting gives $(3,-5,1)$, and the combination $3u-2v$ gives $(8,-11,5)$. Geometrically, $u+v$ is the net displacement when we follow $u$ and then $v$ tip-to-tail. That also explains why $(u+v)-v=u$: adding $v$ and then subtracting $v$ just steps forward along $v$ and immediately steps back along $-v$.

## Related workbook topics

- [Exercise 2: Distance as the length of a vector](problem_02_solution.md)
- [Exercise 8: Linear combination and checking the result](problem_08_solution.md)
