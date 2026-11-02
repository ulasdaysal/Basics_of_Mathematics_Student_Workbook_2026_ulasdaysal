# Exercise 15. Marginal Cost, Total Cost, and Average Cost Optimization

## The question

A manufacturing plant has fixed overhead costs of $C(0)=900\text{ PLN}$, and its marginal cost of producing at level $q>0$ units is modeled by

$$C'(q) = 2q + 10\quad [\text{PLN/unit}].$$

1. Use integration to find the total cost function $C(q)$.
2. Write the average cost per unit $A(q)=\dfrac{C(q)}{q}$ for $q>0$.
3. Find the production level $q^*$ that minimizes the average cost per unit, and verify that at the minimum average cost, marginal cost equals average cost: $C'(q^*)=A(q^*)$.

## Before calculating: what idea do we need?

This synthesis problem combines **both** branches of calculus:
1. **Integration (from marginal to total):** Marginal cost $C'(q)$ is the derivative of total cost $C(q)$. Integrating $C'(q)$ from $0$ to $q$ accumulates the variable production cost, and adding the fixed cost $C(0)$ gives the total cost $C(q)$.
2. **Differentiation (minimizing average cost):** Dividing $C(q)$ by $q$ gives the average unit cost $A(q)=\frac{C(q)}{q}$. When $q$ is very small, the fixed cost $900\text{ PLN}$ is spread over too few units; when $q$ is very large, the rising marginal cost $2q+10$ drives up unit costs. Differentiating $A(q)$ finds the sweet spot $q^*$.

## 1. Finding the total cost function $C(q)$ via integration

By the Fundamental Theorem of Calculus, total cost equals fixed cost plus the definite integral of marginal cost from $0$ to $q$:

$$C(q) = C(0) + \int_0^q C'(u)\,du = 900 + \int_0^q (2u+10)\,du.$$

Evaluating the integral:

$$C(q) = 900 + \left[u^2 + 10u\right]_0^q = q^2 + 10q + 900\quad [\text{PLN}].$$

## 2. Constructing the average cost function $A(q)$

For any production level $q\in(0,\infty)$, the average cost per unit is

$$A(q) = \frac{C(q)}{q} = \frac{q^2 + 10q + 900}{q} = q + 10 + \frac{900}{q}\quad [\text{PLN/unit}].$$

Notice the three economic components of $A(q)$:
- $\frac{900}{q}$ is the **average fixed cost** (which decreases as $q$ grows),
- $q+10$ is the **average variable cost** (which increases linearly as $q$ grows).

## 3. Finding the production level $q^*$ that minimizes average cost

We differentiate $A(q) = q + 10 + 900q^{-1}$ on $(0,\infty)$:

$$A'(q) = 1 - \frac{900}{q^2} = \frac{q^2 - 900}{q^2}.$$

Setting $A'(q)=0$ for $q>0$:

$$q^2 - 900 = 0 \implies q^* = 30\text{ units}.$$

To verify that $q^*=30$ is the global minimum on $(0,\infty)$:
- **First derivative sign:** $A'(q)<0$ on $(0,30)$ and $A'(q)>0$ on $(30,\infty)$.
- **Second derivative test:** $A''(q) = \frac{1800}{q^3} > 0$ for all $q>0$.

At $q^*=30\text{ units}$, the minimum average cost per unit is

$$A(30) = 30 + 10 + \frac{900}{30} = 30 + 10 + 30 = 70\text{ PLN/unit}.$$

## 4. Verifying the economic law $C'(q^*) = A(q^*)$

Let us evaluate the marginal cost $C'(q)=2q+10$ at $q^*=30$:

$$C'(30) = 2(30) + 10 = 70\text{ PLN/unit} = A(30).$$

Why does marginal cost always equal average cost at the minimum of $A(q)$? Differentiating $A(q)=\frac{C(q)}{q}$ by the quotient rule for any smooth cost function gives

$$A'(q) = \frac{C'(q)\cdot q - C(q)\cdot 1}{q^2} = \frac{1}{q}\left(C'(q) - \frac{C(q)}{q}\right) = \frac{C'(q) - A(q)}{q}.$$

Therefore, $A'(q^*)=0 \iff C'(q^*)=A(q^*)$: as long as producing one more unit costs less than the current average ($C'(q)<A(q)$), it pulls the average down; once an extra unit costs more than the current average ($C'(q)>A(q)$), it pulls the average up!

## Quick verification

Let us verify the derivative of $C(q)$ and check values of $A(q)$ near $q^*=30$:

- Differentiating $C(q)=q^2+10q+900$ gives $C'(q)=2q+10$, and $C(0)=900$. ✓
- At $q=15$: $A(15) = 15 + 10 + \frac{900}{15} = 25 + 60 = 85\text{ PLN/unit} > 70$. ✓
- At $q=30$: $A(30) = 30 + 10 + \frac{900}{30} = 40 + 30 = 70\text{ PLN/unit}$ (Minimum). ✓
- At $q=45$: $A(45) = 45 + 10 + \frac{900}{45} = 55 + 20 = 75\text{ PLN/unit} > 70$. ✓

## A concrete example

Compare how the $31\text{st}$ unit affects average cost:
- At $q=30$, total cost is $C(30)=30^2+300+900=2100\text{ PLN}$, so average cost is $2100/30 = 70\text{ PLN/unit}$.
- Producing one more unit ($q=31$) has marginal cost approximately $C'(30)=70\text{ PLN}$ (exact additional cost $C(31)-C(30)=2171-2100=71\text{ PLN}$), raising the new average slightly to $2171/31\approx 70.03\text{ PLN/unit}$.

## How I would explain this in class

> First we integrate the marginal cost $C'(q)=2q+10$ and add the fixed cost $C(0)=900$ to get the total cost $C(q)=q^2+10q+900$. Dividing by $q$ gives the average cost per unit $A(q)=q+10+\frac{900}{q}$ for $q>0$. Setting $A'(q)=1-\frac{900}{q^2}=0$ gives $q^*=30$ units and a minimum average cost of $A(30)=70\text{ PLN/unit}$, which matches the marginal cost $C'(30)=2(30)+10=70\text{ PLN/unit}$ because the average stops falling right when the next unit costs as much as the current average.

## Related workbook topics

- [Exercise 8: Number of Requests Handled by a Server](problem_08_solution.md)
- [Exercise 9: Minimizing the Material Used for a Can](problem_09_solution.md)
