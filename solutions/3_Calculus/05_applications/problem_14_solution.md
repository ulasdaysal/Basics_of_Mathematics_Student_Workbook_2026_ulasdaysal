# Exercise 14. Work Done by a Variable Force

## The question

A nonlinear mechanical spring exerts a restoring force that requires an external force

$$F(x) = 40x + 6x^2\quad [\text{N}]$$

to hold it stretched a distance $x\ [\text{m}]$ beyond its natural length ($x=0$).

1. Set up and evaluate the definite integral for the work $W$ done in stretching the spring from its natural length $x=0$ to $x=2\text{ m}$.
2. Compute the additional work required to stretch it from $x=2\text{ m}$ to $x=3\text{ m}$.
3. Find the average force exerted on $[0,2]$ and verify that $(\text{average force})\times(\text{displacement}) = W$.

## Before calculating: what idea do we need?

When a force $F$ is constant along a straight displacement $\Delta x$, the mechanical work done is simply $W = F\cdot\Delta x$. However, when stretching a spring, the force $F(x)$ grows stronger as $x$ increases. Over an infinitesimal displacement $dx$ at position $x$, the force is practically constant at $F(x)$, so the elemental work is

$$dW = F(x)\,dx.$$

Integrating $F(x)$ from $x=a$ to $x=b$ accumulates all these tiny work increments into the total work:

$$W = \int_a^b F(x)\,dx.$$

## 1. Work done in stretching the spring from $x=0$ to $x=2\text{ m}$

Integrating the force function $F(x)=40x+6x^2$ over $[0,2]$ gives:

$$W_{0\to 2} = \int_0^2 (40x + 6x^2)\,dx.$$

Finding the antiderivative and applying the Fundamental Theorem of Calculus:

$$W_{0\to 2} = \left[20x^2 + 2x^3\right]_0^2 = \bigl(20(2)^2 + 2(2)^3\bigr) - 0 = 80 + 16 = 96\text{ J (joules)}.$$

## 2. Additional work required from $x=2\text{ m}$ to $x=3\text{ m}$

To stretch the spring by just $1\text{ m}$ more—from $x=2\text{ m}$ to $x=3\text{ m}$—we integrate over $[2,3]$:

$$W_{2\to 3} = \int_2^3 (40x + 6x^2)\,dx = \left[20x^2 + 2x^3\right]_2^3.$$

Evaluating at $x=3$ and subtracting the value at $x=2$:

$$W_{2\to 3} = \bigl(20(3)^2 + 2(3)^3\bigr) - 96 = (180 + 54) - 96 = 234 - 96 = 138\text{ J}.$$

Notice the physical insight: stretching the spring by $1\text{ m}$ from $x=2$ to $x=3$ requires $138\text{ J}$, which is significantly more than the $96\text{ J}$ needed to stretch it by the entire first $2\text{ m}$ from $x=0$ to $x=2$, because the spring is already under heavy tension at $x=2\text{ m}$.

## 3. Average force on $[0,2]$ and connection to work

By the average value formula for a function on $[0,2]$:

$$F_{\text{avg}} = \frac{1}{2-0}\int_0^2 F(x)\,dx = \frac{96\text{ J}}{2\text{ m}} = 48\text{ N}.$$

Multiplying this constant equivalent force by the total displacement $\Delta x = 2\text{ m}$ recovers the exact work done:

$$F_{\text{avg}}\cdot\Delta x = (48\text{ N})\cdot(2\text{ m}) = 96\text{ J} = W_{0\to 2}.$$

## 4. Physical decomposition into Hookean and nonlinear hardening terms

The force $F(x)=40x+6x^2$ is the sum of:
- A standard linear (Hooke's law) spring term $F_1(x)=kx=40x$, which contributes $\frac{1}{2}k(2)^2 = 80\text{ J}$ on $[0,2]$,
- A cubic stiffening term $F_2(x)=6x^2$, which contributes $\int_0^2 6x^2\,dx = 16\text{ J}$ on $[0,2]$.

## Quick verification

Let us verify the additivity of work over $[0,3]$ and bound $W_{0\to 2}$:

- **Interval additivity:** Total work from $0$ to $3$ is $\int_0^3 (40x+6x^2)\,dx = [20x^2+2x^3]_0^3 = 180+54 = 234\text{ J}$, which equals $W_{0\to 2}+W_{2\to 3} = 96 + 138 = 234\text{ J}$. ✓
- **Trapezoidal overestimate check on $[0,2]$:** Since $F''(x)=12>0$, $F(x)$ is convex on $[0,2]$, so the integral $96\text{ J}$ must be slightly less than the trapezoid area $\frac{F(0)+F(2)}{2}\cdot 2 = \frac{0+104}{2}\cdot 2 = 104\text{ J}$. Indeed, $96 < 104$. ✓

## A concrete example

In an automotive suspension coil, progressive springs are designed with a rising stiffness like $F(x)=40x+6x^2$:
- During normal driving over small bumps ($x\in[0,1]\text{ m}$), the work absorbed is $\int_0^1 (40x+6x^2)\,dx = 20+2 = 22\text{ J}$ (a soft, comfortable ride).
- During a severe pothole impact ($x\in[2,3]\text{ m}$), that final meter of compression absorbs $138\text{ J}$—more than six times the energy of the first meter—preventing the suspension from bottoming out.

## How I would explain this in class

> Because the force $F(x)=40x+6x^2$ changes with position $x$, we cannot just multiply force by distance; instead we integrate $dW=F(x)\,dx$. From $x=0$ to $x=2$, the work is $\int_0^2 (40x+6x^2)\,dx = [20x^2+2x^3]_0^2 = 80+16 = 96\text{ J}$. From $x=2$ to $x=3$, the work is $[20x^2+2x^3]_2^3 = 234-96 = 138\text{ J}$. Dividing the $96\text{ J}$ work on $[0,2]$ by the $2\text{ m}$ displacement gives the average force $F_{\text{avg}}=48\text{ N}$.

## Related workbook topics

- [Exercise 5: Distance from Velocity](problem_05_solution.md)
- [Exercise 8: Number of Requests Handled by a Server](problem_08_solution.md)
