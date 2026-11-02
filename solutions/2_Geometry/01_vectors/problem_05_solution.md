# Exercise 5. Angle Between Vectors

## The question

Given $u=(1,1,0)$ and $v=(1,0,1)$:

1. Use the sign of $u\cdot v$ to predict the type of angle.
2. Compute the angle.
3. Compare the result with the prediction.

## Before calculating: what idea do we need?

The geometric formula for the dot product of two nonzero vectors $u$ and $v$ is

$$u\cdot v = \|u\|\,\|v\|\cos\theta, \qquad \theta \in [0,\pi].$$

Because the norms $\|u\|$ and $\|v\|$ are strictly positive, **the sign of $\cos\theta$ is the same as the sign of $u\cdot v$**:

- $u\cdot v > 0 \iff \cos\theta > 0 \iff \theta \in \left[0,\frac{\pi}{2}\right)$ (**acute angle**),
- $u\cdot v = 0 \iff \cos\theta = 0 \iff \theta = \frac{\pi}{2}$ (**right angle**),
- $u\cdot v < 0 \iff \cos\theta < 0 \iff \theta \in \left(\frac{\pi}{2},\pi\right]$ (**obtuse angle**).

This allows us to classify the angle qualitatively before computing any square roots or inverse trig functions.

## 1. Predicting the type of angle from the sign of $u\cdot v$

We compute the dot product of $u=(1,1,0)$ and $v=(1,0,1)$:

$$u\cdot v = 1\cdot 1 + 1\cdot 0 + 0\cdot 1 = 1 + 0 + 0 = 1.$$

Since $u\cdot v = 1 > 0$, we have $\cos\theta > 0$, so the angle $\theta$ between $u$ and $v$ must be **acute** ($\theta < 90^\circ$).

## 2. Computing the exact angle

First, we compute the lengths of both vectors:

$$\|u\| = \sqrt{1^2+1^2+0^2} = \sqrt{2},\qquad \|v\| = \sqrt{1^2+0^2+1^2} = \sqrt{2}.$$

Now we substitute $u\cdot v = 1$ and $\|u\|=\|v\|=\sqrt{2}$ into the cosine formula:

$$\cos\theta = \frac{u\cdot v}{\|u\|\,\|v\|} = \frac{1}{\sqrt{2}\cdot\sqrt{2}} = \frac{1}{2}.$$

Since $\theta \in [0,\pi]$ and $\cos\theta = \frac{1}{2}$, we get

$$\theta = \frac{\pi}{3} \text{ radians} = 60^\circ.$$

## 3. Comparing the result with the prediction

Our exact calculation gives $\theta = 60^\circ$ ($\frac{\pi}{3}$), which lies strictly between $0^\circ$ and $90^\circ$. This matches our qualitative prediction from Step 1 that the angle is **acute**.

## Quick verification

Let us check the triangle formed by the origin $O=(0,0,0)$ and the endpoints $P=(1,1,0)$ and $Q=(1,0,1)$:

- $\|u\| = d(O,P) = \sqrt{2}$,
- $\|v\| = d(O,Q) = \sqrt{2}$,
- $\|u-v\| = \|(0,1,-1)\| = \sqrt{0^2+1^2+(-1)^2} = \sqrt{2}$.

All three sides have the same length $\sqrt{2}$! Therefore, $\triangle OPQ$ is an **equilateral triangle**, and every interior angle of an equilateral triangle is $60^\circ$ ($\frac{\pi}{3}$). $\checkmark$

## A concrete example

Consider the unit cube $[0,1]^3$ with one corner at the origin $(0,0,0)$:

- $u=(1,1,0)$ is the diagonal of the bottom face (in the $xy$-plane).
- $v=(1,0,1)$ is the diagonal of the front face (in the $xz$-plane).
- The segment connecting their tips $(1,1,0)$ and $(1,0,1)$ has vector $(0,-1,1)$, which is a diagonal of the right face (in the $yz$-plane).

Because all three segments are face diagonals of the same unit cube, they have equal length $\sqrt{2}$ and meet at $60^\circ$.

## How I would explain this in class

> First, $u\cdot v = 1\cdot 1 + 1\cdot 0 + 0\cdot 1 = 1 > 0$. Because the lengths are positive, a positive dot product immediately tells us $\cos\theta > 0$, so the angle is acute. Next, both vectors have length $\sqrt{2}$, so $\cos\theta = \frac{1}{\sqrt{2}\sqrt{2}} = \frac{1}{2}$, which gives $\theta = 60^\circ$ ($\frac{\pi}{3}$)—confirming our prediction.

## Related workbook topics

- [Exercise 4: Dot product and perpendicularity](problem_04_solution.md)
- [Exercise 15: Comparing directions using the cosine of the angle](problem_15_solution.md)
