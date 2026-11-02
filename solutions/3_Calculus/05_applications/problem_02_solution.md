# Exercise 2. Maximum Area of a Rectangle

## The question

A rectangle has perimeter $40$.

1. Write its area as a function of the length of one side.
2. Determine the domain of this function resulting from the geometry of the problem.
3. Find the dimensions that give the maximum area.
4. Justify that the point found actually gives a maximum.

## Before calculating: what idea do we need?

A rectangle has two independent side lengths $x$ and $y$, so its area $A=xy$ initially depends on two variables. However, the fixed perimeter $2x+2y=40$ acts as a **constraint equation**. Using the constraint to express $y$ in terms of $x$ reduces the problem to a single-variable function $A(x)$ on an open interval, which we can optimize using the derivative.

## 1. Area as a function of one side

Let $x$ and $y$ denote the lengths of the adjacent sides of the rectangle. The perimeter constraint is

$$2x+2y=40 \implies x+y=20 \implies y=20-x.$$

Substituting $y=20-x$ into the area formula $A=xy$ gives the objective function of a single variable:

$$A(x)=x(20-x)=20x-x^2.$$

## 2. Geometric domain of the function

For a non-degenerate rectangle to exist, both side lengths must be strictly positive:

$$x>0 \quad\text{and}\quad y=20-x>0 \implies x<20.$$

Thus, the natural geometric domain of $A(x)$ is the open interval

$$D=(0,20).$$

## 3. Finding the dimensions that maximize the area

We differentiate $A(x)=20x-x^2$ with respect to $x$:

$$A'(x)=20-2x.$$

Setting the derivative equal to zero gives the critical point:

$$A'(x)=0 \iff 20-2x=0 \iff x=10.$$

Notice that $x=10$ lies inside the domain $D=(0,20)$. The corresponding second side is

$$y=20-10=10.$$

Thus, the optimal dimensions are $10\times 10$ (a square), yielding a maximum area of

$$A(10)=10\cdot 10=100.$$

## 4. Justification that the critical point gives a maximum

We can justify that $x=10$ is a global maximum on $(0,20)$ in three complementary ways:

- **First derivative sign test:** For $x\in(0,10)$, we have $A'(x)=20-2x>0$, so $A(x)$ is strictly increasing. For $x\in(10,20)$, we have $A'(x)=20-2x<0$, so $A(x)$ is strictly decreasing. Therefore, $x=10$ is the unique global maximum on $(0,20)$.
- **Second derivative test:** $A''(x)=-2<0$ everywhere, so $A(x)$ is strictly concave down and its stationary point is a global maximum.
- **Completing the square:** $A(x)=100-(x-10)^2\le 100$, with equality if and only if $x=10$.

## Quick verification

Let us compare $A(10)=100$ with nearby and extreme rectangles of perimeter $40$:

- If $x=9$, then $y=11$ and $A(9)=9\cdot 11=99 < 100$. ✓
- If $x=11$, then $y=9$ and $A(11)=11\cdot 9=99 < 100$. ✓
- Near the endpoints: as $x\to 0^+$ or $x\to 20^-$, $A(x)\to 0$. ✓

## A concrete example

Suppose you have $40\text{ m}$ of fencing to enclose a rectangular garden.
- A long, narrow strip of dimensions $2\text{ m}\times 18\text{ m}$ uses all $40\text{ m}$ of fence ($2(2+18)=40$) but encloses only $36\text{ m}^2$.
- A $5\text{ m}\times 15\text{ m}$ rectangle encloses $75\text{ m}^2$.
- Balancing the sides equally to $10\text{ m}\times 10\text{ m}$ encloses $100\text{ m}^2$, illustrating the classic isoperimetric principle: among all rectangles of a fixed perimeter, the square encloses the largest area.

## How I would explain this in class

> Since the perimeter is $40$, half the perimeter is $x+y=20$, so the second side is $y=20-x$. Both sides must be positive, which restricts $x$ to $(0,20)$. The area function is $A(x)=x(20-x)=20x-x^2$. Its derivative $A'(x)=20-2x$ equals zero at $x=10$, where $y=10$ as well. Because $A'(x)$ switches from positive to negative at $x=10$ (and $A''(x)=-2<0$), the $10\times 10$ square gives the maximum area of $100$.

## Related workbook topics

- [Exercise 3: A Box Made from Cardboard](problem_03_solution.md)
- [Exercise 12: Complete Model and Computer Verification](problem_12_solution.md)
