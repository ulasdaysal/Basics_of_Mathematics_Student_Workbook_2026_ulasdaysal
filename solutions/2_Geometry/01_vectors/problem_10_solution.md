# Exercise 10. Triangle Area from Vectors

## The question

The points $A=(0,0,0)$, $B=(2,1,0)$, and $C=(1,3,2)$ form a triangle. Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$, compute the area of the parallelogram using the cross product, and then find the area of the triangle. Explain the factor $\frac12$.

## Before calculating: what idea do we need?

For two vectors $u=\overrightarrow{AB}$ and $v=\overrightarrow{AC}$ sharing the initial point $A$ in $\mathbb R^3$, the **length of their cross product** equals the area of the parallelogram they span:

$$\text{Area}_{\text{parallelogram}} = \|u\times v\| = \|u\|\,\|v\|\sin\theta,$$

where $\|u\|$ is the base of the parallelogram and $\|v\|\sin\theta$ is its perpendicular height.

Because the triangle $\triangle ABC$ is formed by cutting this parallelogram in half along the diagonal $BC$, the area of the triangle is half the area of the parallelogram:

$$\text{Area}_{\triangle ABC} = \frac{1}{2}\left\|\overrightarrow{AB}\times\overrightarrow{AC}\right\|.$$

## 1. Constructing $\overrightarrow{AB}$ and $\overrightarrow{AC}$

Since $A=(0,0,0)$ is at the origin, subtracting $A$ from $B=(2,1,0)$ and $C=(1,3,2)$ gives:

$$\overrightarrow{AB} = B - A = (2-0,\, 1-0,\, 0-0) = (2,1,0),$$

$$\overrightarrow{AC} = C - A = (1-0,\, 3-0,\, 2-0) = (1,3,2).$$

## 2. Computing the cross product and the parallelogram area

First we compute the cross product $\overrightarrow{AB}\times\overrightarrow{AC}$:

$$\overrightarrow{AB}\times\overrightarrow{AC} = \begin{vmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\2&1&0\\1&3&2\end{vmatrix} = \left(\begin{vmatrix}1&0\\3&2\end{vmatrix},\; -\begin{vmatrix}2&0\\1&2\end{vmatrix},\; \begin{vmatrix}2&1\\1&3\end{vmatrix}\right).$$

Evaluating the $2\times 2$ determinants:

- First component: $1\cdot 2 - 0\cdot 3 = 2$,
- Second component: $-(2\cdot 2 - 0\cdot 1) = -4$,
- Third component: $2\cdot 3 - 1\cdot 1 = 6 - 1 = 5$.

So

$$\overrightarrow{AB}\times\overrightarrow{AC} = (2,-4,5).$$

The area of the parallelogram spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$ is the norm of this cross product:

$$\text{Area}_{\text{parallelogram}} = \left\|\overrightarrow{AB}\times\overrightarrow{AC}\right\| = \sqrt{2^2 + (-4)^2 + 5^2} = \sqrt{4 + 16 + 25} = \sqrt{45} = 3\sqrt{5}.$$

## 3. Finding the area of $\triangle ABC$

Dividing the parallelogram area by $2$:

$$\text{Area}_{\triangle ABC} = \frac{1}{2}\text{Area}_{\text{parallelogram}} = \frac{3\sqrt{5}}{2}.$$

## 4. Explaining the factor $\frac{1}{2}$

Let $D = B + \overrightarrow{AC} = (3,4,2)$ be the fourth vertex of the parallelogram spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$:

- The diagonal segment $BC$ splits the parallelogram $ABDC$ into two triangles: $\triangle ABC$ and $\triangle DCB$.
- These two triangles have identical side lengths ($\|\overrightarrow{AB}\|=\|\overrightarrow{CD}\|$, $\|\overrightarrow{AC}\|=\|\overrightarrow{BD}\|$, and common side $BC$), so they are **congruent** by Side-Side-Side (SSS) and have equal area.
- Therefore, $\triangle ABC$ occupies **exactly half** of the parallelogram's area. This is the exact same $\frac12$ that appears in the familiar formula $\text{Area}_{\triangle} = \frac12\cdot\text{base}\cdot\text{height}$, whereas a parallelogram has $\text{Area} = \text{base}\cdot\text{height}$.

## Quick verification

Let us verify the area without the cross product using $\text{Area}_{\triangle ABC} = \frac{1}{2}\sqrt{\|\overrightarrow{AB}\|^2\|\overrightarrow{AC}\|^2 - (\overrightarrow{AB}\cdot\overrightarrow{AC})^2}$:

- $\|\overrightarrow{AB}\|^2 = 2^2+1^2+0^2 = 5$,
- $\|\overrightarrow{AC}\|^2 = 1^2+3^2+2^2 = 14$,
- $\overrightarrow{AB}\cdot\overrightarrow{AC} = 2(1)+1(3)+0(2) = 5$.

Then:

$$\text{Area}_{\triangle ABC} = \frac{1}{2}\sqrt{5\cdot 14 - 5^2} = \frac{1}{2}\sqrt{70 - 25} = \frac{1}{2}\sqrt{45} = \frac{3\sqrt{5}}{2}.\quad \checkmark$$

Also check orthogonality of the cross product: $(2,-4,5)\cdot(2,1,0)=4-4=0$ and $(2,-4,5)\cdot(1,3,2)=2-12+10=0$. $\checkmark$

## A concrete example

Notice the three components of $\overrightarrow{AB}\times\overrightarrow{AC} = (2,-4,5)$:

- If we project $\triangle ABC$ onto the $yz$-plane (setting $x=0$), its shadow has vertices $(0,0)$, $(1,0)$, $(3,2)$ and area $\frac12|2| = 1$.
- Its shadow on the $xz$-plane has area $\frac12|-4| = 2$.
- Its shadow on the $xy$-plane has area $\frac12|5| = \frac52$.

By the 3D Pythagorean theorem for areas (De Gua's / Cauchy–Binet formula), the true tilted triangle area satisfies

$$\text{Area}_{\triangle ABC} = \sqrt{1^2 + 2^2 + \left(\frac{5}{2}\right)^2} = \sqrt{1 + 4 + \frac{25}{4}} = \sqrt{\frac{45}{4}} = \frac{3\sqrt{5}}{2}.$$

## How I would explain this in class

> First, the edge vectors from $A$ are $\overrightarrow{AB}=(2,1,0)$ and $\overrightarrow{AC}=(1,3,2)$. Their cross product is $\overrightarrow{AB}\times\overrightarrow{AC}=(2,-4,5)$. The length of that cross product gives the area of the full parallelogram they span: $\sqrt{4+16+25}=\sqrt{45}=3\sqrt{5}$. Finally, because the diagonal $BC$ cuts the parallelogram into two congruent triangles, the area of $\triangle ABC$ is half of the parallelogram's area, giving $\frac{3\sqrt{5}}{2}$.

## Related workbook topics

- [Exercise 9: Cross product as a perpendicular direction](problem_09_solution.md)
- [Exercise 12: A normal vector to a plane](problem_12_solution.md)
