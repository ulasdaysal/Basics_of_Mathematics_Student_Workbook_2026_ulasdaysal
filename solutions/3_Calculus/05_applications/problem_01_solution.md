# Exercise 1. Motion — from Position to Velocity

## The question

The position of a point along an axis is given by

$$s(t)=t^3-6t^2+9t+2,\qquad t\ge0.$$

1. Determine the velocity and acceleration.
2. Find the times at which the point stops.
3. Determine on which intervals the point moves in the positive direction of the axis and on which intervals it moves in the negative direction.

## Before calculating: what idea do we need?

In kinematics, derivatives measure instantaneous rates of change with respect to time $t$:

- **Velocity** $v(t)=s'(t)$ is the rate of change of position. Its sign tells us the direction of motion:
  - $v(t)>0$: the point moves in the **positive direction** ($s(t)$ increases),
  - $v(t)<0$: the point moves in the **negative direction** ($s(t)$ decreases),
  - $v(t)=0$: the point is **instantaneously at rest** (it stops and may reverse direction).
- **Acceleration** $a(t)=v'(t)=s''(t)$ is the rate of change of velocity.

## 1. Velocity and acceleration

Differentiating the position function $s(t)=t^3-6t^2+9t+2$ term by term gives the velocity:

$$v(t)=s'(t)=3t^2-12t+9.$$

Factoring out $3$ makes the algebraic structure immediately visible:

$$v(t)=3(t^2-4t+3)=3(t-1)(t-3).$$

Differentiating $v(t)$ once more gives the acceleration:

$$a(t)=v'(t)=s''(t)=6t-12=6(t-2).$$

## 2. Times at which the point stops

The point stops when its instantaneous velocity is zero:

$$v(t)=0 \iff 3(t-1)(t-3)=0.$$

Since $t\ge0$, both roots lie in the physical domain:

$$t_1=1,\qquad t_2=3.$$

At these two moments, the point reaches local extrema of position:
- At $t=1$: $s(1)=1^3-6(1)^2+9(1)+2=6$ (a local turnaround point),
- At $t=3$: $s(3)=3^3-6(3)^2+9(3)+2=27-54+27+2=2$ (a second turnaround point).

## 3. Direction of motion on time intervals

We examine the sign of $v(t)=3(t-1)(t-3)$ on $[0,\infty)$:

- On $[0,1)$: both $(t-1)<0$ and $(t-3)<0$, so their product is positive and $v(t)>0$.
- On $(1,3)$: $(t-1)>0$ while $(t-3)<0$, so $v(t)<0$.
- On $(3,\infty)$: both $(t-1)>0$ and $(t-3)>0$, so $v(t)>0$.

Therefore:
- The point moves in the **positive direction** on $[0,1)$ and on $(3,\infty)$.
- The point moves in the **negative direction** on $(1,3)$.

## 4. Physical trajectory summary

Starting at $s(0)=2$, the point moves forward to $s(1)=6$, stops at $t=1$, reverses direction and moves backward to $s(3)=2$, stops again at $t=3$, and then moves forward indefinitely for $t>3$. Notice that at $t=2$, $a(2)=0$ and $v(2)=-3$: this is the moment of maximum backward speed.

## Quick verification

Let us check the position values and test velocities in each interval:

- At $t=0$: $s(0)=2$, and $v(0)=9>0$ (moving forward from $2$ to $s(1)=6$). ✓
- At $t=2\in(1,3)$: $v(2)=3(2-1)(2-3)=-3<0$, and indeed $s(t)$ drops from $s(1)=6$ to $s(3)=2$. ✓
- At $t=4\in(3,\infty)$: $v(4)=3(4-1)(4-3)=9>0$, and $s(4)=64-96+36+2=6>s(3)$. ✓

## A concrete example

Suppose $s(t)$ is measured in meters and $t$ in seconds. If we only look at the net displacement between $t=0$ and $t=3$, we see

$$\Delta s = s(3)-s(0) = 2-2 = 0\text{ m}.$$

However, the point was not standing still! From $t=0$ to $t=1$ it traveled $|6-2|=4\text{ m}$ forward, and from $t=1$ to $t=3$ it traveled $|2-6|=4\text{ m}$ backward, for a total distance traveled of $4+4=8\text{ m}$. Tracking the sign of $v(t)$ is what lets us distinguish net displacement from actual motion.

## How I would explain this in class

> To study motion from a position formula $s(t)$, we differentiate once to get velocity $v(t)=3t^2-12t+9=3(t-1)(t-3)$ and a second time to get acceleration $a(t)=6t-12$. Setting $v(t)=0$ shows the object stops at $t=1$ and $t=3$. Because $v(t)$ is a parabola opening upward, the velocity is positive on $[0,1)$ and $(3,\infty)$, meaning forward motion, and negative on $(1,3)$, meaning the object backs up between $t=1$ and $t=3$.

## Related workbook topics

- [Exercise 5: Distance from Velocity](problem_05_solution.md)
- [Exercise 14: Work Done by a Variable Force](problem_14_solution.md)
