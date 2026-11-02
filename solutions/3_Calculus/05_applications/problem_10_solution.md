# Exercise 10. A Cable Through Water and Land

## The question

Point $A$ lies on one bank of a straight river of width $100\text{ m}$, and point $B$ lies on the opposite bank, $500\text{ m}$ along the bank from the point $O$ directly opposite $A$.

The cost per meter of laying cable underwater is twice the cost per meter of laying cable on land.

Build a cost function depending on the point where the cable comes out of the water, determine the domain, and find the solution that minimizes the cost.

## Before calculating: what idea do we need?

Let $O$ be the point on the opposite bank directly across from $A$, so segment $AO\perp OB$ with $|AO|=100\text{ m}$ and $|OB|=500\text{ m}$. Suppose the cable runs straight underwater from $A$ to a landing point $P$ on segment $OB$ at distance $x=|OP|$ from $O$, and then runs straight along the bank from $P$ to $B$:
- Underwater length $|AP|=\sqrt{100^2+x^2}$ (by the Pythagorean theorem on right triangle $AOP$),
- Land length $|PB|=500-x$.

Increasing $x$ shortens the cheap land route at unit rate $1$, while lengthening the expensive underwater diagonal at rate $\frac{x}{\sqrt{100^2+x^2}}$. The optimal landing point occurs where the marginal land savings exactly match the marginal underwater expense.

## 1. Building the cost function and determining the domain

Let $c>0$ be the cost per meter of cable on land; then the cost per meter underwater is $2c$. If the cable exits the water at distance $x\text{ m}$ downstream from $O$ toward $B$:

- Underwater distance: $\sqrt{x^2+100^2}=\sqrt{x^2+10\,000}\text{ m}$, costing $2c\sqrt{x^2+10\,000}$.
- Land distance: $(500-x)\text{ m}$, costing $c(500-x)$.

Thus the total cost function is

$$C(x) = c\left(2\sqrt{x^2+10\,000} + 500 - x\right).$$

Since $P$ lies on the segment $OB$ between $O$ ($x=0$, crossing perpendicular to the river) and $B$ ($x=500$, going entirely underwater), the natural geometric domain is the closed interval

$$D = [0,500]\quad [\text{m}].$$

(Any point with $x<0$ or $x>500$ would strictly increase both the underwater and land distances compared to $x=0$ or $x=500$.)

## 2. Differentiating and finding the critical point

Differentiating $C(x)$ with respect to $x$ on $(0,500)$ gives:

$$C'(x) = c\left(\frac{2x}{\sqrt{x^2+10\,000}} - 1\right).$$

Setting $C'(x)=0$:

$$\frac{2x}{\sqrt{x^2+10\,000}} = 1 \iff 2x = \sqrt{x^2+10\,000}.$$

Since $x\in[0,500]$ is non-negative, squaring both sides is an equivalent transformation:

$$4x^2 = x^2 + 10\,000 \iff 3x^2 = 10\,000 \implies x^* = \frac{100}{\sqrt{3}} = \frac{100\sqrt{3}}{3} \approx 57.74\text{ m}.$$

Clearly $x^*\approx 57.74\text{ m}$ lies inside the domain $[0,500]$.

## 3. Verifying that $x^*$ minimizes the cost

Let us check the sign of $C'(x) = c\left(\frac{2x-\sqrt{x^2+10\,000}}{\sqrt{x^2+10\,000}}\right)$:

- For $x\in\bigl[0,\frac{100}{\sqrt{3}}\bigr)$, we have $4x^2<x^2+10\,000$, so $2x<\sqrt{x^2+10\,000}$ and $C'(x)<0$ ($C$ is strictly decreasing).
- For $x\in\bigl(\frac{100}{\sqrt{3}},500\bigr]$, we have $4x^2>x^2+10\,000$, so $2x>\sqrt{x^2+10\,000}$ and $C'(x)>0$ ($C$ is strictly increasing).

Thus, $x^*=\frac{100\sqrt{3}}{3}\approx 57.74\text{ m}$ is the unique global minimum of $C(x)$ on $[0,500]$.

## 4. Physical interpretation (Snell's Law of Refraction)

Let $\theta$ be the angle between the underwater cable $AP$ and the line $AO$ perpendicular to the river bank. In right triangle $AOP$:

$$\sin\theta = \frac{x}{\sqrt{x^2+100^2}}.$$

The optimality condition $C'(x)=0$ is literally $\frac{2x}{\sqrt{x^2+100^2}}=1$, which says

$$\sin\theta = \frac{1}{2} \implies \theta = 30^\circ, \qquad \tan 30^\circ = \frac{x}{100} = \frac{1}{\sqrt{3}}.$$

Just like light refracting into a faster medium at the critical angle, the cable crosses the river at $30^\circ$ to the normal whenever the destination $B$ is at least $57.74\text{ m}$ downstream!

## Quick verification

Let us compute the exact minimum cost at $x^*=\frac{100}{\sqrt{3}}$ and compare it with the two endpoints:

- At $x^*=\frac{100}{\sqrt{3}}$: underwater length is $\sqrt{\frac{10\,000}{3}+10\,000}=\frac{200}{\sqrt{3}}$, so
  $$C(x^*) = c\left(\frac{400}{\sqrt{3}}+500-\frac{100}{\sqrt{3}}\right) = c\left(500+100\sqrt{3}\right) \approx 673.21c.$$
- Endpoint $x=0$ (straight across, then $500\text{ m}$ on land): $C(0)=c(2\cdot 100+500)=700c > 673.21c$. ✓
- Endpoint $x=500$ (diagonal all the way underwater): $C(500)=2c\sqrt{500^2+100^2}=200\sqrt{26}\,c\approx 1019.80c > 673.21c$. ✓

## A concrete example

Suppose laying cable on land costs $c=100\text{ PLN/m}$ and underwater costs $2c=200\text{ PLN/m}$:
- Crossing straight across ($x=0$) costs $70\,000\text{ PLN}$.
- Going diagonally underwater all the way to $B$ ($x=500\text{ m}$) costs $101\,980\text{ PLN}$.
- Landing at $x^*=\frac{100\sqrt{3}}{3}\approx 57.74\text{ m}$ downstream (spending $115.47\text{ m}$ underwater and $442.26\text{ m}$ on land) reduces the total cost to $67\,321\text{ PLN}$, saving $2\,679\text{ PLN}$ over the perpendicular crossing.

## How I would explain this in class

> Let $x\in[0,500]$ be how far downstream from the opposite point $O$ the cable comes ashore. By Pythagoras, the underwater section has length $\sqrt{x^2+100^2}$ at unit cost $2c$, and the remaining land section has length $500-x$ at unit cost $c$, giving $C(x)=c\bigl(2\sqrt{x^2+10\,000}+500-x\bigr)$. Setting $C'(x)=c\bigl(\frac{2x}{\sqrt{x^2+10\,000}}-1\bigr)=0$ gives $2x=\sqrt{x^2+10\,000}$, so $3x^2=10\,000$ and $x=\frac{100\sqrt{3}}{3}\approx 57.74\text{ m}$. Because $C'(x)$ goes from negative to positive there, exiting the water $57.74\text{ m}$ downstream (at a $30^\circ$ angle) minimizes the cost.

## Related workbook topics

- [Exercise 9: Minimizing the Material Used for a Can](problem_09_solution.md)
- [Exercise 12: Complete Model and Computer Verification](problem_12_solution.md)
