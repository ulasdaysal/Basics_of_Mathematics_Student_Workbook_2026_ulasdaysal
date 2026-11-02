# Exercise 3. Vector Normalization

## The question

For $v=(3,4)$ find a unit vector $e$ with the same direction and orientation. Check that $\|e\|=1$, reconstruct $v$ in the form $v=\|v\|e$, and explain what changes during normalization and what remains unchanged.

## Before calculating: what idea do we need?

Every nonzero vector $v$ carries two pieces of geometric information:

1. **Its length (magnitude):** $\|v\| = \sqrt{v_1^2+v_2^2}$, which is a positive number.
2. **Its direction and orientation:** the ray along which the arrow points.

**Normalization** separates these two aspects. By dividing $v$ by its own length $\|v\|$ (which is multiplying by the positive scalar $\frac{1}{\|v\|}$), we rescale the vector to length $1$ without rotating or flipping it:

$$e = \frac{1}{\|v\|}v.$$

## 1. Length of $v$ and the unit vector $e$

First, we compute the norm of $v=(3,4)$:

$$\|v\| = \sqrt{3^2+4^2} = \sqrt{9+16} = \sqrt{25} = 5.$$

Next, we divide $v$ by $\|v\|=5$:

$$e = \frac{1}{5}(3,4) = \left(\frac{3}{5},\, \frac{4}{5}\right).$$

Since we multiplied $v$ by a **positive** scalar $\frac15 > 0$, $e$ has the exact same direction and orientation as $v$.

## 2. Checking that $\|e\|=1$

We compute the Euclidean norm of $e=\left(\frac35,\frac45\right)$:

$$\|e\| = \sqrt{\left(\frac{3}{5}\right)^2 + \left(\frac{4}{5}\right)^2} = \sqrt{\frac{9}{25} + \frac{16}{25}} = \sqrt{\frac{25}{25}} = \sqrt{1} = 1.$$

## 3. Reconstructing $v=\|v\|e$

Multiplying the unit direction vector $e$ by the magnitude $\|v\|=5$ gives back the original vector:

$$\|v\|e = 5\left(\frac{3}{5},\, \frac{4}{5}\right) = \left(5\cdot\frac{3}{5},\, 5\cdot\frac{4}{5}\right) = (3,4) = v.$$

## 4. What changes and what remains unchanged

During normalization:

- **What changes:** The **length (norm)** of the vector changes from $\|v\|=5$ to $\|e\|=1$, and its individual coordinates are scaled down by a factor of $5$.
- **What remains unchanged:**
  - The **direction** (the line of action, with slope $\frac{4/5}{3/5} = \frac{4}{3}$),
  - The **orientation** (pointing into the first quadrant, since $\frac15>0$),
  - The **ratio of the components** ($3:4$) and the angles the vector makes with the coordinate axes ($\cos\theta_x = \frac35$, $\cos\theta_y = \frac45$).

## Quick verification

1. **Norm check:** $\left(\frac35\right)^2 + \left(\frac45\right)^2 = 0.36 + 0.64 = 1.00.\quad \checkmark$
2. **Collinearity and orientation check via dot product:**
   $$v\cdot e = 3\cdot\frac{3}{5} + 4\cdot\frac{4}{5} = \frac{9+16}{5} = 5 = \|v\|\,\|e\|,$$
   so $\cos\angle(v,e) = 1$, confirming the angle between $v$ and $e$ is $0^\circ$. $\checkmark$

## A concrete example

Suppose a boat moves with velocity vector $v=(3,4)\text{ m/s}$ (so $3\text{ m/s}$ east and $4\text{ m/s}$ north).

- Its **speed** is $\|v\|=5\text{ m/s}$.
- Its **pure heading** is the unit vector $e=(0.6, 0.8)$: for every $1\text{ m}$ of travel along its path, the boat advances $0.6\text{ m}$ east and $0.8\text{ m}$ north.

Writing $v = 5\cdot(0.6, 0.8)$ cleanly factors the velocity into $\text{speed} \times \text{heading}$. If the boat speeds up to $10\text{ m/s}$ along the same heading, its new velocity is simply $10e = (6,8)\text{ m/s}$.

## How I would explain this in class

> A vector $v=(3,4)$ has length $\sqrt{3^2+4^2}=5$. To turn it into a unit vector pointing the same way, we divide by its length: $e=\frac15(3,4)=(\frac35,\frac45)$. Normalization changes the length to $1$, while keeping the direction, orientation, and component ratio $3:4$ completely unchanged. Writing $v=5\cdot(\frac35,\frac45)$ separates "how far" ($5$) from "which way" ($e$).

## Related workbook topics

- [Exercise 2: Distance as the length of a vector](problem_02_solution.md)
- [Exercise 15: Comparing directions using the cosine of the angle](problem_15_solution.md)
