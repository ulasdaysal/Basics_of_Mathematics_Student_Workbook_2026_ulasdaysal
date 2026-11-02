# Exercise 5. Distance from Velocity

## The question

The velocity of a car during the first five seconds is described by the function

$$v(t)=4t+2\quad [\text{m/s}].$$

Compute the distance traveled and explain why the integral of velocity gives the change in position.

Then answer what would have to be changed in the reasoning if the velocity also took negative values.

## Before calculating: what idea do we need?

Position $s(t)$ and velocity $v(t)$ are linked by differentiation: $s'(t)=v(t)$, which means $s(t)$ is an **antiderivative** of $v(t)$. By the Fundamental Theorem of Calculus, integrating the rate of change $v(t)$ over $[0,5]$ accumulates all infinitesimal displacements $ds=v(t)\,dt$:

$$\int_0^5 v(t)\,dt = s(5)-s(0) = \Delta s.$$

When $v(t)\ge 0$ on the entire interval, the car never reverses direction, so the net change in position (displacement) equals the total distance traveled.

## 1. Checking the sign of velocity and computing the distance

For $t\in[0,5]$, the velocity is

$$v(t)=4t+2 \ge 2 > 0.$$

Since the car moves strictly forward throughout $[0,5]$, the distance traveled equals the definite integral of $v(t)$:

$$d=\int_0^5 (4t+2)\,dt = \left[2t^2+2t\right]_0^5 = \bigl(2(5)^2+2(5)\bigr) - 0 = 50+10 = 60\text{ m}.$$

## 2. Why the integral of velocity gives the change in position

Divide the time interval $[a,b]$ into tiny subintervals of duration $\Delta t_i$. On each short subinterval, the velocity is nearly constant at $v(t_i)$, so the small change in position is approximately

$$\Delta s_i \approx v(t_i)\,\Delta t_i.$$

Summing these increments over the whole trip gives the Riemann sum $\sum v(t_i)\,\Delta t_i$, which in the limit $\Delta t_i\to 0$ becomes $\int_a^b v(t)\,dt$. At the same time, the sum of all small position changes telescopes to the total change in position $s(b)-s(a)$ by the Fundamental Theorem of Calculus.

## 3. What changes if velocity takes negative values?

If $v(t)<0$ on part of the interval, the car is moving **backward** during that time:
- The ordinary integral $\int_a^b v(t)\,dt = s(b)-s(a)$ computes the **net displacement** (forward distance minus backward distance).
- To compute the actual **total distance traveled** (what the odometer measures), we must integrate the **speed** $|v(t)|$:

$$d_{\text{total}} = \int_a^b |v(t)|\,dt.$$

In practice, we find the times where $v(t)=0$, split $[a,b]$ into subintervals where $v(t)$ has a constant sign, and integrate $+v(t)$ where $v(t)\ge 0$ and $-v(t)$ where $v(t)<0$.

## 4. Kinematics and geometric interpretation

Notice that $v(t)=4t+2$ describes motion with constant acceleration $a=v'(t)=4\text{ m/s}^2$ and initial velocity $v_0=2\text{ m/s}$. Under the velocity-time graph, the region on $[0,5]$ is a trapezoid of width $5\text{ s}$ and parallel heights $v(0)=2\text{ m/s}$ and $v(5)=22\text{ m/s}$.

## Quick verification

We can check $d=60\text{ m}$ in two independent ways:

- **Area of a trapezoid:** $\text{Area}=\frac{v(0)+v(5)}{2}\cdot 5 = \frac{2+22}{2}\cdot 5 = 12\cdot 5 = 60\text{ m}$. ✓
- **Physics formula for uniform acceleration:** $d=v_0 t + \frac{1}{2}at^2 = 2(5) + \frac{1}{2}(4)(5)^2 = 10 + 50 = 60\text{ m}$. ✓

## A concrete example

Suppose instead that a car had velocity $v(t)=2t-4\text{ m/s}$ on $[0,5]$. Here $v(t)<0$ on $[0,2)$ and $v(t)>0$ on $(2,5]$.
- The **net displacement** is $\int_0^5 (2t-4)\,dt = [t^2-4t]_0^5 = 25-20 = 5\text{ m}$.
- The **total distance traveled** splits at $t=2$:

$$d = \int_0^2 -(2t-4)\,dt + \int_2^5 (2t-4)\,dt = 4 + 9 = 13\text{ m}.$$

The car backed up $4\text{ m}$ during the first $2\text{ s}$ and then drove $9\text{ m}$ forward, traveling $13\text{ m}$ in total to end up $5\text{ m}$ ahead of its starting point.

## How I would explain this in class

> Because velocity is the derivative of position ($s'(t)=v(t)$), integrating velocity over $[0,5]$ sums all the tiny position changes $v(t)\,dt$ to give the net change in position $s(5)-s(0)$. Since $v(t)=4t+2$ is always positive on $[0,5]$, the car only moves forward, and $\int_0^5 (4t+2)\,dt = [2t^2+2t]_0^5 = 60\text{ m}$ is the exact distance traveled. If $v(t)$ became negative, the plain integral would subtract backward motion, so we would have to integrate the speed $|v(t)|$ by splitting the integral at the roots of $v(t)=0$.

## Related workbook topics

- [Exercise 1: Motion — from Position to Velocity](problem_01_solution.md)
- [Exercise 8: Number of Requests Handled by a Server](problem_08_solution.md)
