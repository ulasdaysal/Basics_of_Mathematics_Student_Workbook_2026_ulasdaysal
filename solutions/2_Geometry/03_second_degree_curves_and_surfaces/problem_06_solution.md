# Exercise 6. Shifted Ellipse

## The question

Reduce

$$4x^2+9y^2-16x+18y-11=0$$

to canonical form. Give the center and semiaxis lengths. Check that substituting the coordinates of the center into the left-hand side gives a value consistent with the form you obtained.

## Before calculating: what idea do we need?

When $x^2$ and $y^2$ have different positive coefficients ($4$ and $9$), the curve is an **ellipse**, and the linear terms $-16x$ and $+18y$ indicate that its center has been shifted away from $(0,0)$.

Before completing the square in each variable, we must **factor out the leading coefficient** ($4$ from the $x$-terms and $9$ from the $y$-terms) so that the expression inside each parenthesis starts with a plain $x^2$ or $y^2$.

## 1. Factoring and completing the square

Group the $x$-terms and $y$-terms, and move $-11$ to the right-hand side:

$$(4x^2-16x) + (9y^2+18y) = 11.$$

Factor $4$ from the $x$-group and $9$ from the $y$-group:

$$4(x^2-4x) + 9(y^2+2y) = 11.$$

Complete the square inside each parenthesis:
- $x^2-4x = (x-2)^2 - 4$,
- $y^2+2y = (y+1)^2 - 1$.

Substitute these back, remembering to multiply the subtracted constants by the outside factors $4$ and $9$:

$$4\big((x-2)^2 - 4\big) + 9\big((y+1)^2 - 1\big) = 11$$

$$4(x-2)^2 - 16 + 9(y+1)^2 - 9 = 11$$

$$4(x-2)^2 + 9(y+1)^2 = 11 + 16 + 9 = 36.$$

## 2. Dividing to obtain canonical form

Divide both sides of $4(x-2)^2 + 9(y+1)^2 = 36$ by $36$:

$$\frac{4(x-2)^2}{36} + \frac{9(y+1)^2}{36} = 1 \implies \frac{(x-2)^2}{9} + \frac{(y+1)^2}{4} = 1.$$

This is the canonical form of the shifted ellipse.

## 3. Center and semiaxis lengths

Comparing $\frac{(x-2)^2}{3^2} + \frac{(y-(-1))^2}{2^2} = 1$ with $\frac{(x-x_0)^2}{a^2} + \frac{(y-y_0)^2}{b^2} = 1$:

- **Center:** $C = (2,-1)$.
- **Horizontal semiaxis (along $Ox$):** $a = \sqrt{9} = 3$.
- **Vertical semiaxis (along $Oy$):** $b = \sqrt{4} = 2$.

## 4. Checking the center in the left-hand side

Before dividing by $36$, the completed-square form of the left-hand side is

$$L(x,y) = 4x^2+9y^2-16x+18y-11 = 4(x-2)^2 + 9(y+1)^2 - 36.$$

If we substitute the center $(x,y)=(2,-1)$ into the completed-square form, both squared brackets vanish and we get

$$L(2,-1) = 4(0)^2 + 9(0)^2 - 36 = -36.$$

Now let us substitute $(2,-1)$ directly into the original left-hand side:

$$L(2,-1) = 4(2)^2 + 9(-1)^2 - 16(2) + 18(-1) - 11 = 16 + 9 - 32 - 18 - 11 = -36.$$

Both expressions evaluate to $-36$ (and in the normalized form $\frac{(x-2)^2}{9}+\frac{(y+1)^2}{4}-1$, substituting $(2,-1)$ gives $-1 = \frac{-36}{36}$).

## Quick verification

Let us also check one vertex of the shifted ellipse, say $(2+3,-1) = (5,-1)$, in the original equation:

$$4(5)^2 + 9(-1)^2 - 16(5) + 18(-1) - 11 = 100 + 9 - 80 - 18 - 11 = 0.$$

It satisfies the original equation. ✓

## A concrete example

By introducing shifted coordinates $X = x-2$ and $Y = y+1$, the origin $(X,Y)=(0,0)$ is placed at $(x,y)=(2,-1)$, and our equation becomes the standard centered ellipse

$$\frac{X^2}{9} + \frac{Y^2}{4} = 1.$$

Thus the four vertices in $(x,y)$-coordinates are $(2\pm 3, -1) = (-1,-1),\;(5,-1)$ and $(2, -1\pm 2) = (2,-3),\;(2,1)$.

## How I would explain this in class

> First, I group the $x$- and $y$-terms and factor out the leading coefficients: $4(x^2-4x)+9(y^2+2y)=11$. Completing the squares gives $4(x-2)^2-16+9(y+1)^2-9=11$, so $4(x-2)^2+9(y+1)^2=36$. Dividing by $36$ yields the canonical form $\frac{(x-2)^2}{9}+\frac{(y+1)^2}{4}=1$, which is an ellipse centered at $(2,-1)$ with semiaxes $a=3$ and $b=2$. Plugging $(2,-1)$ into the original left-hand side gives $16+9-32-18-11=-36$, matching $4(x-2)^2+9(y+1)^2-36$ at the center.

## Related workbook topics

- [Exercise 2: Circle by Completing the Square](problem_02_solution.md)
- [Exercise 15: Recognition and Sketch Without a Given Name](problem_15_solution.md)
