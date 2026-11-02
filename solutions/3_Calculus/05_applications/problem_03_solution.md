# Exercise 3. A Box Made from Cardboard

## The question

From a $30\text{ cm}\times 40\text{ cm}$ sheet of cardboard, squares of side length $x$ are cut from the four corners and the resulting flaps are folded up to form an open rectangular box.

Write the volume as a function of $x$, determine the physically meaningful domain, and find the value of $x$ for which the volume is greatest.

## Before calculating: what idea do we need?

When we cut a square of side $x$ from each corner of a $30\text{ cm}\times 40\text{ cm}$ rectangle and fold up the four flaps:
- Each original side loses $2x$ of length (one cut of length $x$ at each end), so the base of the box has dimensions $(30-2x)\text{ cm}$ by $(40-2x)\text{ cm}$.
- The folded flaps become the vertical walls, so the height of the box is $x\text{ cm}$.

Multiplying length, width, and height produces a cubic polynomial $V(x)$ that we maximize over the interval where all three dimensions are strictly positive.

## 1. Volume as a function of $x$

The volume of the open box is the product of its base dimensions and height:

$$V(x)=x(30-2x)(40-2x).$$

Expanding the product so we can differentiate easily:

$$V(x)=x(1200-140x+4x^2)=4x^3-140x^2+1200x\quad [\text{cm}^3].$$

## 2. Physically meaningful domain

All three dimensions of the box must be strictly positive:

$$x>0,\qquad 30-2x>0 \implies x<15,\qquad 40-2x>0 \implies x<20.$$

The shorter side of the cardboard ($30\text{ cm}$) is the binding constraint: once $x\ge 15\text{ cm}$, the two corner cuts meet in the middle of the $30\text{ cm}$ side and no base remains. Thus, the physical domain is

$$D=(0,15)\quad [\text{cm}].$$

## 3. Finding the critical points

Differentiating $V(x)=4x^3-140x^2+1200x$ with respect to $x$ gives

$$V'(x)=12x^2-280x+1200=4(3x^2-70x+300).$$

Setting $V'(x)=0$ yields the quadratic equation

$$3x^2-70x+300=0.$$

The discriminant is

$$\Delta=(-70)^2-4\cdot 3\cdot 300=4900-3600=1300=100\cdot 13,$$

so $\sqrt{\Delta}=10\sqrt{13}$. The two roots are

$$x_{1,2}=\frac{70\pm 10\sqrt{13}}{6}=\frac{35\pm 5\sqrt{13}}{3}.$$

## 4. Selecting and justifying the maximum in the domain

Since $\sqrt{13}\approx 3.6056$, the two critical points are approximately

$$x_1=\frac{35-5\sqrt{13}}{3}\approx 5.66\text{ cm},\qquad x_2=\frac{35+5\sqrt{13}}{3}\approx 17.68\text{ cm}.$$

Because $x_2\approx 17.68\notin(0,15)$, the only critical point inside our physical domain $D=(0,15)$ is

$$x^*=\frac{35-5\sqrt{13}}{3}\approx 5.66\text{ cm}.$$

Since $V'(x)=4(3x^2-70x+300)$ is an upward-opening parabola with roots $x_1\approx 5.66$ and $x_2\approx 17.68$:
- For $x\in(0,x^*)$, $V'(x)>0$, so $V(x)$ is strictly increasing.
- For $x\in(x^*,15)$, $V'(x)<0$, so $V(x)$ is strictly decreasing.

Therefore, $x^*=\dfrac{35-5\sqrt{13}}{3}\approx 5.66\text{ cm}$ gives the global maximum volume on $(0,15)$.

## Quick verification

Let us evaluate the second derivative and check volume values around $x^*\approx 5.66\text{ cm}$:

- Second derivative test: $V''(x)=24x-280$. At $x^*=\frac{35-5\sqrt{13}}{3}$, we have $V''(x^*)=8(35-5\sqrt{13})-280=-40\sqrt{13}<0$, confirming a local maximum. ✓
- Boundary behavior: $\lim_{x\to 0^+}V(x)=0$ and $\lim_{x\to 15^-}V(x)=0$, while $V(x^*)>0$. ✓

## A concrete example

Let us compare the volume at $x^*\approx 5.66\text{ cm}$ with nearby integer cuts:

- For $x=5\text{ cm}$: base is $20\text{ cm}\times 30\text{ cm}$, so $V(5)=5\cdot 20\cdot 30=3000\text{ cm}^3$.
- For $x=6\text{ cm}$: base is $18\text{ cm}\times 28\text{ cm}$, so $V(6)=6\cdot 18\cdot 28=3024\text{ cm}^3$.
- For $x^*\approx 5.66\text{ cm}$: base is $18.69\text{ cm}\times 28.69\text{ cm}$, giving the maximum volume $V(x^*)\approx 3032.3\text{ cm}^3$.

Both shallow cuts ($x=5$) and deeper cuts ($x=6$) produce smaller volumes than the optimal cut $x^*\approx 5.66\text{ cm}$.

## How I would explain this in class

> Cutting squares of side $x$ from the four corners reduces the cardboard's sides from $30$ and $40$ to $30-2x$ and $40-2x$, while folding up the flaps gives height $x$. For all three dimensions to be positive, $x$ must lie in $(0,15)$. Expanding $V(x)=x(30-2x)(40-2x)=4x^3-140x^2+1200x$ and solving $V'(x)=0$ gives two roots, $(35\pm 5\sqrt{13})/3$. Only $x=(35-5\sqrt{13})/3\approx 5.66\text{ cm}$ fits in $(0,15)$, and because $V'(x)$ changes sign from $+$ to $-$ there, it maximizes the volume.

## Related workbook topics

- [Exercise 2: Maximum Area of a Rectangle](problem_02_solution.md)
- [Exercise 9: Minimizing the Material Used for a Can](problem_09_solution.md)
