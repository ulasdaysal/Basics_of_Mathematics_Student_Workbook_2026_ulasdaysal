# Exercise 7. A Trigonometric Function

## The question

On $[0,2\pi]$, find the intervals of monotonicity and the extrema of

$$f(x)=\sin x+\cos x.$$

Include the endpoints of the interval and compare the function values at the critical points and at the endpoints.

## Before calculating: what idea do we need?

When analyzing a continuous function on a **closed, bounded interval** $[a, b]$, local extrema inside the open interval $(a, b)$ occur at critical points where $f'(x) = 0$. However, the global (and interval-boundary) behavior also depends on the **endpoints** $x = a$ and $x = b$, so we must evaluate $f$ at both the interior critical points and the endpoints.

## 1. Derivative and critical points in $(0, 2\pi)$

Differentiating $f(x) = \sin x + \cos x$:

$$f'(x) = \cos x - \sin x.$$

Set $f'(x) = 0$ on $(0, 2\pi)$:

$$\cos x - \sin x = 0 \iff \sin x = \cos x \iff \tan x = 1$$

(noting that $\cos x = 0$ does not give a solution since $\sin x = \pm 1 \neq 0$ there). Within $[0, 2\pi]$, $\tan x = 1$ yields two critical points:

$$x_1 = \frac{\pi}{4} \quad (\text{first quadrant}), \qquad x_2 = \frac{5\pi}{4} \quad (\text{third quadrant}).$$

## 2. Sign of $f'(x)$ and intervals of monotonicity

We can see the sign of $f'(x) = \cos x - \sin x$ by comparing $\cos x$ and $\sin x$ (or writing $f'(x) = -\sqrt{2}\sin(x - \frac{\pi}{4})$):

- On $[0, \frac{\pi}{4})$: $\cos x > \sin x \implies f'(x) > 0$,
- On $(\frac{\pi}{4}, \frac{5\pi}{4})$: $\cos x < \sin x \implies f'(x) < 0$,
- On $(\frac{5\pi}{4}, 2\pi]$: $\cos x > \sin x \implies f'(x) > 0$.

| Interval / Point | $x = 0$ | $(0, \frac{\pi}{4})$ | $x = \frac{\pi}{4}$ | $(\frac{\pi}{4}, \frac{5\pi}{4})$ | $x = \frac{5\pi}{4}$ | $(\frac{5\pi}{4}, 2\pi)$ | $x = 2\pi$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+1$ | $+$ | $0$ | $-$ | $0$ | $+$ | $+1$ |
| Behavior of $f(x)$ | Endpoint ($1$) | $\nearrow$ | **Max** ($\sqrt{2}$) | $\searrow$ | **Min** ($-\sqrt{2}$) | $\nearrow$ | Endpoint ($1$) |

- **Strictly increasing** on $\left[0, \frac{\pi}{4}\right]$ and on $\left[\frac{5\pi}{4}, 2\pi\right]$.
- **Strictly decreasing** on $\left[\frac{\pi}{4}, \frac{5\pi}{4}\right]$.

## 3. Comparing values at the critical points and endpoints

Evaluate $f(x) = \sin x + \cos x$ at all four key points:

- Left endpoint $x = 0$: $f(0) = \sin 0 + \cos 0 = 0 + 1 = 1$.
- First critical point $x = \frac{\pi}{4}$: $f\left(\frac{\pi}{4}\right) = \frac{\sqrt{2}}{2} + \frac{\sqrt{2}}{2} = \sqrt{2} \approx 1.414$.
- Second critical point $x = \frac{5\pi}{4}$: $f\left(\frac{5\pi}{4}\right) = -\frac{\sqrt{2}}{2} - \frac{\sqrt{2}}{2} = -\sqrt{2} \approx -1.414$.
- Right endpoint $x = 2\pi$: $f(2\pi) = \sin 2\pi + \cos 2\pi = 0 + 1 = 1$.

Ordering these values gives $-\sqrt{2} < 1 < \sqrt{2}$:

- **Global and local maximum:** $f\left(\frac{\pi}{4}\right) = \sqrt{2}$.
- **Global and local minimum:** $f\left(\frac{5\pi}{4}\right) = -\sqrt{2}$.
- **Endpoint values:** $f(0) = f(2\pi) = 1$, which match because $f$ has period $2\pi$; starting at height $1$, the wave climbs to $\sqrt{2}$, drops to $-\sqrt{2}$, and climbs back to height $1$ at $2\pi$.

## Quick verification

Rewrite $f(x)$ using the auxiliary-angle identity:

$$f(x) = \sin x + \cos x = \sqrt{2}\left(\frac{1}{\sqrt{2}}\sin x + \frac{1}{\sqrt{2}}\cos x\right) = \sqrt{2}\sin\left(x + \frac{\pi}{4}\right).$$

Since $\sin\theta$ attains its maximum $1$ at $\theta = \frac{\pi}{2}$ ($x = \frac{\pi}{4}$) and its minimum $-1$ at $\theta = \frac{3\pi}{2}$ ($x = \frac{5\pi}{4}$), the extreme values of $f$ are indeed $\pm\sqrt{2}$ at $x = \frac{\pi}{4}$ and $x = \frac{5\pi}{4}$. ✓

## A concrete example

Check the intermediate quadrant angles to trace the wave between endpoints and extrema:

- $x = 0$: $f(0) = 1$,
- $x = \frac{\pi}{4}$: $f(\frac{\pi}{4}) = \sqrt{2} \approx 1.414$ (peak),
- $x = \frac{\pi}{2}$: $f(\frac{\pi}{2}) = 1 + 0 = 1$,
- $x = \pi$: $f(\pi) = 0 + (-1) = -1$,
- $x = \frac{5\pi}{4}$: $f(\frac{5\pi}{4}) = -\sqrt{2} \approx -1.414$ (trough),
- $x = \frac{3\pi}{2}$: $f(\frac{3\pi}{2}) = -1 + 0 = -1$,
- $x = 2\pi$: $f(2\pi) = 1$.

## How I would explain this in class

> Setting $f'(x) = \cos x - \sin x = 0$ on $[0, 2\pi]$ gives $\tan x = 1$, so the critical points are $x = \frac{\pi}{4}$ and $x = \frac{5\pi}{4}$. The function starts at $f(0) = 1$, increases to its maximum $\sqrt{2}$ at $\frac{\pi}{4}$, decreases all the way to its minimum $-\sqrt{2}$ at $\frac{5\pi}{4}$, and then increases back to $f(2\pi) = 1$ at the right endpoint.

## Related workbook topics

- [Exercise 1: A Cubic Polynomial](problem_01_solution.md)
- [Exercise 2: A Parabola from the Perspective of the Derivative](problem_02_solution.md)
