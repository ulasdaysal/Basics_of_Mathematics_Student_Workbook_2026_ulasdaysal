# Exercise 7. Classifying a Second-Degree Equation

## The question

Determine the type of object described by:
1. $4x^2+9y^2=36$,
2. $x^2-y^2=1$,
3. $x^2-4y=0$,
4. $x^2+y^2+1=0$.

In the last case, explain why there are no real points.

## Before calculating: what idea do we need?

To classify a second-degree equation in the plane:
1. Check **which variables are squared** (both $x$ and $y$, or only one).
2. If both are squared, check the **signs of the squared terms** and the **sign of the constant term** after bringing constants to the right-hand side.
3. Always verify whether the equation admits **real solutions**—a sum of squares of real numbers can never be negative!

## 1. Equation 1: $4x^2+9y^2=36$

Divide both sides by $36$ to put the equation in canonical form:

$$\frac{4x^2}{36} + \frac{9y^2}{36} = 1 \implies \frac{x^2}{9} + \frac{y^2}{4} = 1.$$

- Both $x^2$ and $y^2$ have positive coefficients, the right-hand side is $+1>0$, and the denominators $9=3^2$ and $4=2^2$ are different.
- **Type of object:** **Ellipse** centered at $(0,0)$ with semiaxes $a=3$ (horizontal) and $b=2$ (vertical).

## 2. Equation 2: $x^2-y^2=1$

This is already in the canonical form

$$\frac{x^2}{1^2} - \frac{y^2}{1^2} = 1.$$

- Both $x$ and $y$ are squared, but their coefficients have **opposite signs** ($+1$ and $-1$).
- **Type of object:** **Hyperbola** (specifically a *rectangular* or *equilateral* hyperbola, since $a=b=1$ and the asymptotes $y=\pm x$ are perpendicular), with vertices at $(\pm 1,0)$.

## 3. Equation 3: $x^2-4y=0$

Move $4y$ to the right-hand side:

$$x^2 = 4y.$$

- Only $x$ is squared, while $y$ appears in the first power.
- **Type of object:** **Parabola** with vertex at $(0,0)$, symmetric across the $y$-axis ($x=0$), opening upward ($y = \frac{1}{4}x^2 \ge 0$).

## 4. Equation 4: $x^2+y^2+1=0$ (and why there are no real points)

Move $1$ to the right-hand side:

$$x^2 + y^2 = -1.$$

- **Type of object:** **Empty set** in the real plane $\mathbb{R}^2$ (often called an *imaginary circle*).
- **Why there are no real points:** For any real numbers $x,y\in\mathbb{R}$, their squares are non-negative:
  $$x^2 \ge 0 \qquad\text{and}\qquad y^2 \ge 0.$$
  Therefore, their sum satisfies
  $$x^2 + y^2 \ge 0,$$
  so $x^2+y^2+1 \ge 1 > 0$. It can never equal $0$ for any pair of real coordinates $(x,y)$.

## Quick verification

Let us summarize and verify with test points for the first three and a bound for the fourth:

| Equation | Canonical Form | Object Type | Sample Real Point | Check |
| :--- | :--- | :--- | :--- | :--- |
| $4x^2+9y^2=36$ | $\frac{x^2}{9}+\frac{y^2}{4}=1$ | Ellipse | $(3,0)$ | $4(9)+0=36$ ✓ |
| $x^2-y^2=1$ | $\frac{x^2}{1}-\frac{y^2}{1}=1$ | Hyperbola | $(1,0)$ | $1-0=1$ ✓ |
| $x^2-4y=0$ | $x^2=4y$ | Parabola | $(2,1)$ | $4-4(1)=0$ ✓ |
| $x^2+y^2+1=0$ | $x^2+y^2=-1$ | Empty set (no real points) | None ($\min(x^2+y^2+1)=1$) | $1\neq 0$ ✓ |

## A concrete example

Compare the family of equations $x^2+y^2 = c$ as the constant $c$ changes:
- For $c = 1$: $x^2+y^2=1$ is the **unit circle** of radius $1$.
- For $c = 0$: $x^2+y^2=0$ has only the **single point** $(0,0)$.
- For $c = -1$: $x^2+y^2=-1$ (which is $x^2+y^2+1=0$) has **no real points at all**, because shrinking the radius past $0$ makes the circle disappear from the real plane.

## How I would explain this in class

> To classify these four equations, I put each one into standard form. First, $4x^2+9y^2=36$ divides by $36$ to give $\frac{x^2}{9}+\frac{y^2}{4}=1$, an ellipse with semiaxes $3$ and $2$. Second, $x^2-y^2=1$ has opposite signs on the squared terms, so it is a hyperbola. Third, $x^2-4y=0$ or $x^2=4y$ has only $x$ squared and $y$ linear, so it is a parabola opening upward. Fourth, $x^2+y^2+1=0$ means $x^2+y^2=-1$; since squares of real numbers are never negative ($x^2+y^2\ge 0$), no real point $(x,y)$ can satisfy the equation, so it describes the empty set.

## Related workbook topics

- [Exercise 1: Recognizing Curves from Canonical Form](problem_01_solution.md)
- [Exercise 5: Hyperbola and Asymptotes](problem_05_solution.md)
