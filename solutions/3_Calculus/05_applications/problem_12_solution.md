# Exercise 12. Complete Model and Computer Verification

## The question

A museum wants to create a rectangular exhibition room next to an existing straight wall. The side along the wall does not need to be built. The remaining three sides are to be constructed to two different standards: the two sides perpendicular to the wall cost $300\text{ PLN/m}$ each, while the side parallel to the wall costs $500\text{ PLN/m}$. The budget is $30\,000\text{ PLN}$.

Build a model that maximizes the area of the room and prepare a complete analysis: variables and units, mathematical model, domain, derivative, determination and verification of the optimum, interpretation, graph description, numerical verification near the optimum, and a distinction between the modeling and calculation stages.

## Before calculating: what idea do we need?

To maximize the area of the exhibition room, we should use the entire available budget of $30\,000\text{ PLN}$. Because the two perpendicular walls ($2\times 300=600\text{ PLN/m}$ combined) and the single parallel wall ($500\text{ PLN/m}$) have different unit costs, the optimal shape will not be a square. Instead, the budget constraint ties the two side lengths linearly, turning the area into a downward-opening quadratic function of a single variable.

## 1. Definition of variables, units, and mathematical model

- Let $x\ [\text{m}]$ be the length of each of the **two sides perpendicular** to the existing wall.
- Let $y\ [\text{m}]$ be the length of the **single side parallel** to the existing wall.
- Let $A\ [\text{m}^2]$ be the floor area of the rectangular exhibition room:

$$A(x,y) = xy\quad [\text{m}^2].$$

Building two perpendicular walls of length $x$ at $300\text{ PLN/m}$ each costs $2\cdot 300x = 600x\text{ PLN}$, and building one parallel wall of length $y$ at $500\text{ PLN/m}$ costs $500y\text{ PLN}$. Using the full budget of $30\,000\text{ PLN}$ gives the constraint equation:

$$600x + 500y = 30\,000.$$

Dividing both sides by $100$ and solving for $y$:

$$6x + 5y = 300 \implies y = 60 - \frac{6}{5}x = 60 - 1.2x.$$

Substituting $y=60-1.2x$ into $A=xy$ yields the single-variable objective function:

$$A(x) = x\left(60 - \frac{6}{5}x\right) = 60x - \frac{6}{5}x^2 = 60x - 1.2x^2\quad [\text{m}^2].$$

## 2. Domain resulting from the problem statement

For a physical room, both dimensions $x$ and $y$ must be strictly positive:

$$x > 0 \quad\text{and}\quad y = 60 - \frac{6}{5}x > 0 \implies \frac{6}{5}x < 60 \implies x < 50.$$

Thus the feasible domain is the open interval

$$D = (0,50)\quad [\text{m}].$$

## 3. Derivative, determination, and verification of the optimum

Differentiating $A(x)=60x-\frac{6}{5}x^2$ on $D=(0,50)$ gives:

$$A'(x) = 60 - \frac{12}{5}x = 60 - 2.4x.$$

Setting $A'(x)=0$ to find the critical point:

$$60 - \frac{12}{5}x = 0 \iff \frac{12}{5}x = 60 \implies x^* = 25\text{ m}.$$

Clearly $x^*=25\in(0,50)$. We verify that $x^*=25\text{ m}$ is the global maximum on $(0,50)$:
- **First derivative sign:** $A'(x)>0$ for $x\in(0,25)$ and $A'(x)<0$ for $x\in(25,50)$.
- **Second derivative test:** $A''(x)=-\frac{12}{5}=-2.4<0$ for all $x\in(0,50)$.

Substituting $x^*=25\text{ m}$ into the constraint and objective function gives:

$$y^* = 60 - \frac{6}{5}(25) = 60 - 30 = 30\text{ m},\qquad A_{\max} = A(25) = 25\cdot 30 = 750\text{ m}^2.$$

**Interpretation:** The museum achieves the maximum exhibition area of $750\text{ m}^2$ by building two perpendicular walls of length $25\text{ m}$ each and one parallel wall of length $30\text{ m}$. Notice the **equal budget split**: the perpendicular walls cost $600\cdot 25 = 15\,000\text{ PLN}$ (half the budget), and the parallel wall costs $500\cdot 30 = 15\,000\text{ PLN}$ (the other half of the budget).

## 4. Graph of the objective function and modeling vs. calculation breakdown

**Graph of $A(x)=60x-1.2x^2$ on $(0,50)$:** The graph is a downward-opening parabola with $x$-intercepts at $(0,0)$ and $(50,0)$, symmetric about the vertical line $x=25$, and reaching its vertex (peak) at $(25, 750)$.

```
Area A(x) [m^2]
  750 +                 * (25, 750)
      |            *         *
  480 +         *               *
      |      *                     *
    0 +---*-------------+-------------*---> x [m]
          0            25            50
```

**Distinguishing modeling from calculation:**
- **Modeling stage:** Choosing variables $x,y$ and their units, recognizing that one side is free along the existing wall, translating the two construction standards into the budget equation $600x+500y=30\,000$, determining the physical domain $x\in(0,50)$, and interpreting $(25\text{ m}, 30\text{ m}, 750\text{ m}^2)$ in the museum context.
- **Calculation stage:** Solving $600x+500y=30\,000$ for $y$, expanding $A(x)=60x-1.2x^2$, differentiating to get $A'(x)=60-2.4x$, solving $A'(x)=0$ for $x=25$, and evaluating $A(25)=750$.

## Quick verification

Let us check the budget constraint and perform a numerical verification table for values of $x$ near $x^*=25\text{ m}$:

| $x\ [\text{m}]$ | $y = 60-1.2x\ [\text{m}]$ | Cost $600x+500y\ [\text{PLN}]$ | Area $A(x)=xy\ [\text{m}^2]$ | Difference from $A_{\max}$ |
| :---: | :---: | :---: | :---: | :---: |
| $20$ | $36.0$ | $30\,000$ | $720.0$ | $-30.0\text{ m}^2$ |
| $24$ | $31.2$ | $30\,000$ | $748.8$ | $-1.2\text{ m}^2$ |
| **$25$** | **$30.0$** | **$30\,000$** | **$750.0$** | **$0\text{ m}^2$ (MAX)** |
| $26$ | $28.8$ | $30\,000$ | $748.8$ | $-1.2\text{ m}^2$ |
| $30$ | $24.0$ | $30\,000$ | $720.0$ | $-30.0\text{ m}^2$ |

Both $x=24\text{ m}$ and $x=26\text{ m}$ yield $748.8\text{ m}^2 < 750.0\text{ m}^2$, confirming the peak at $x=25\text{ m}$. ✓

## A concrete example

Notice that $A(25\pm\Delta x) = 750 - 1.2(\Delta x)^2$. If structural pillars in the museum hall force the architect to shift the perpendicular wall length by $\Delta x = 1\text{ m}$ (to $24\text{ m}$ or $26\text{ m}$), the museum loses only $1.2(1)^2=1.2\text{ m}^2$ ($0.16\%$ of the floor area) because the derivative $A'(25)=0$ makes the objective function flat right at the optimum.

## How I would explain this in class

> If the two walls perpendicular to the existing wall have length $x$ and the parallel wall has length $y$, the budget equation is $2(300x)+500y=600x+500y=30\,000$, which gives $y=60-1.2x$ on the domain $x\in(0,50)$. Substituting this into the area $A=xy$ produces the parabola $A(x)=60x-1.2x^2$. Setting $A'(x)=60-2.4x=0$ gives $x=25\text{ m}$, $y=30\text{ m}$, and a maximum area of $750\text{ m}^2$, where exactly half the budget ($15\,000\text{ PLN}$) is spent on each direction.

## Related workbook topics

- [Exercise 2: Maximum Area of a Rectangle](problem_02_solution.md)
- [Exercise 10: A Cable Through Water and Land](problem_10_solution.md)
