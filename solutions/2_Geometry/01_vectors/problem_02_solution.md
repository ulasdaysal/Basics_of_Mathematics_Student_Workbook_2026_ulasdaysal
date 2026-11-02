# Exercise 2. Distance as the Length of a Vector

## The question

The points are $A=(1,2,3)$ and $B=(4,-2,6)$.

1. Construct $\overrightarrow{AB}$.
2. Compute its length.
3. Compute the distance between the points using the coordinate formula.
4. Explain why both calculations give the same result.

## Before calculating: what idea do we need?

Given two points $A=(x_A,y_A,z_A)$ and $B=(x_B,y_B,z_B)$, the displacement from $A$ to $B$ is obtained by **"terminal minus initial"**:

$$\overrightarrow{AB} = B - A = (x_B-x_A,\, y_B-y_A,\, z_B-z_A).$$

The Euclidean length (norm) of any vector $w=(w_1,w_2,w_3)$ is

$$\|w\| = \sqrt{w_1^2 + w_2^2 + w_3^2}.$$

The distance between two points in space is simply the length of the displacement vector connecting them.

## 1. Constructing the vector $\overrightarrow{AB}$

Subtracting the coordinates of the initial point $A=(1,2,3)$ from the terminal point $B=(4,-2,6)$:

$$\overrightarrow{AB} = (4-1,\, -2-2,\, 6-3) = (3,-4,3).$$

## 2. Computing the length of $\overrightarrow{AB}$

Applying the norm formula to $\overrightarrow{AB}=(3,-4,3)$:

$$\|\overrightarrow{AB}\| = \sqrt{3^2 + (-4)^2 + 3^2} = \sqrt{9 + 16 + 9} = \sqrt{34}.$$

## 3. Computing the distance using the coordinate formula

The three-dimensional Euclidean distance formula between $A=(x_A,y_A,z_A)$ and $B=(x_B,y_B,z_B)$ is

$$d(A,B) = \sqrt{(x_B-x_A)^2 + (y_B-y_A)^2 + (z_B-z_A)^2}.$$

Substituting $A=(1,2,3)$ and $B=(4,-2,6)$:

$$d(A,B) = \sqrt{(4-1)^2 + (-2-2)^2 + (6-3)^2} = \sqrt{3^2 + (-4)^2 + 3^2} = \sqrt{9 + 16 + 9} = \sqrt{34}.$$

## 4. Why both calculations give the same result

The two formulas are identical because the differences $(x_B-x_A)$, $(y_B-y_A)$, and $(z_B-z_A)$ inside the distance formula **are** the components of $\overrightarrow{AB}$.

Geometrically, moving from $A$ to $B$ changes the coordinates by $\Delta x=3$, $\Delta y=-4$, and $\Delta z=3$. These three mutually perpendicular displacements form the edges of a $3\times 4\times 3$ rectangular box, and the segment $AB$ (as well as the arrow $\overrightarrow{AB}$) is the space diagonal of that box. By the 3D Pythagorean theorem, the length of that diagonal is $\sqrt{(\Delta x)^2+(\Delta y)^2+(\Delta z)^2}$.

## Quick verification

1. **Adding displacement to the start point recovers the endpoint:**
   $$A + \overrightarrow{AB} = (1,2,3) + (3,-4,3) = (4,-2,6) = B.\quad \checkmark$$
2. **Reversing direction keeps the same distance:**
   $$\overrightarrow{BA} = A - B = (-3,4,-3),\qquad \|\overrightarrow{BA}\| = \sqrt{(-3)^2+4^2+(-3)^2} = \sqrt{34}.\quad \checkmark$$

## A concrete example

Notice the first two components of $\overrightarrow{AB}=(3,-4,3)$: in the horizontal $xy$-plane, the displacement $(3,-4,0)$ has length

$$\sqrt{3^2+(-4)^2} = \sqrt{9+16} = 5$$

(a classic $3\text{–}4\text{–}5$ right triangle). Then we climb $\Delta z = 3$ units vertically, creating a second right triangle with horizontal leg $5$ and vertical leg $3$. Its hypotenuse has length $\sqrt{5^2+3^2}=\sqrt{25+9}=\sqrt{34}\approx 5.83$.

## How I would explain this in class

> To find the vector from $A$ to $B$, we subtract the start point from the end point: $\overrightarrow{AB}=(4-1,-2-2,6-3)=(3,-4,3)$. Its length is $\sqrt{3^2+(-4)^2+3^2}=\sqrt{34}$. The point-distance formula does the exact same calculation in one expression because the distance between $A$ and $B$ is literally the length of the displacement vector $\overrightarrow{AB}$.

## Related workbook topics

- [Exercise 1: Vector operations and their meaning](problem_01_solution.md)
- [Exercise 3: Vector normalization](problem_03_solution.md)
