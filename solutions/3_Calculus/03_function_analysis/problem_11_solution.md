# Exercise 11. A Parameter and the Number of Extrema

## The question

For

$$f_a(x)=x^3-3ax$$

depending on $a$, determine the number of critical points and their character. Separate the parameter cases and justify why the structure of the graph changes.

## Before calculating: what idea do we need?

When a function depends on a parameter $a \in \mathbb{R}$, its derivative $f_a'(x)$ is a family of quadratics whose discriminant depends on $a$. A critical point produces a local extremum **only if $f_a'(x)$ changes sign** across it:

- Two simple roots of $f_a'(x)$ $\implies$ two sign changes $\implies$ two local extrema,
- One double root of $f_a'(x)$ $\implies$ no sign change $\implies$ a horizontal inflection point (no extrema),
- No real roots of $f_a'(x)$ $\implies$ no critical points $\implies$ strictly monotonic everywhere.

## 1. Derivative of the family $f_a(x)$

For every $a \in \mathbb{R}$, the domain of $f_a(x) = x^3 - 3ax$ is $\mathbb{R}$, and its derivative is

$$f_a'(x) = 3x^2 - 3a = 3(x^2 - a).$$

The equation for critical points is

$$f_a'(x) = 0 \iff x^2 = a.$$

Since $x^2 \ge 0$ for all real $x$, the number of real solutions depends on the sign of $a$: $a < 0$, $a = 0$, or $a > 0$.

## 2. Case-by-case analysis of the parameter $a$

### Case 1: $a < 0$ (no critical points, no extrema)
When $a < 0$, $-a > 0$, so $x^2 - a \ge -a > 0$ for every $x \in \mathbb{R}$.
- **Number of critical points:** $0$.
- **Monotonicity and extrema:** $f_a'(x) = 3(x^2 - a) > 0$ for all $x \in \mathbb{R}$, so $f_a$ is **strictly increasing on all of $\mathbb{R}$** and has **no local extrema**.

### Case 2: $a = 0$ (one critical point, no extrema)
When $a = 0$, $f_0(x) = x^3$ and $f_0'(x) = 3x^2$.
- **Number of critical points:** $1$, at $x = 0$.
- **Character of $x = 0$:** Since $3x^2 \ge 0$ on both sides of $x = 0$ ($+$ on $(-\infty, 0)$ and $+$ on $(0, \infty)$), $f_0'(x)$ **does not change sign**. Thus $f_0$ is strictly increasing on $\mathbb{R}$, and $x = 0$ is a **saddle / horizontal inflection point**, not a local extremum.

### Case 3: $a > 0$ (two critical points, two local extrema)
When $a > 0$, we can factor $f_a'(x) = 3(x - \sqrt{a})(x + \sqrt{a})$.
- **Number of critical points:** $2$, at $x = -\sqrt{a}$ and $x = \sqrt{a}$.

| Interval / Point | $(-\infty, -\sqrt{a})$ | $x = -\sqrt{a}$ | $(-\sqrt{a}, \sqrt{a})$ | $x = \sqrt{a}$ | $(\sqrt{a}, \infty)$ |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Sign of $f_a'(x)$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| Behavior of $f_a(x)$ | $\nearrow$ | **Local max** ($2a\sqrt{a}$) | $\searrow$ | **Local min** ($-2a\sqrt{a}$) | $\nearrow$ |

- **Local maximum** at $x = -\sqrt{a}$ with value $f_a(-\sqrt{a}) = (-a\sqrt{a}) - 3a(-\sqrt{a}) = 2a\sqrt{a}$.
- **Local minimum** at $x = \sqrt{a}$ with value $f_a(\sqrt{a}) = a\sqrt{a} - 3a\sqrt{a} = -2a\sqrt{a}$.

## 3. Why the structure of the graph changes

Write $f_a(x) = x^3 + (-3a)x$ as the sum of $x^3$ (which always pulls upward) and the linear term $-3ax$:

- For **$a < 0$**, the linear term $-3ax$ has a **positive slope** ($-3a > 0$), so both $x^3$ and $-3ax$ pull upward together; the graph rises everywhere without ever flattening out.
- For **$a = 0$**, the linear term disappears; the graph flattens momentarily at the origin ($f_0'(0) = 0$) before continuing upward.
- For **$a > 0$**, the linear term $-3ax$ has a **negative slope** ($-3a < 0$). Near $x = 0$ where $|x|$ is small, $-3ax$ dominates $x^3$ and forces the graph downward on $[-\sqrt{a}, \sqrt{a}]$; for $|x| > \sqrt{a}$, $x^3$ takes back control, creating a local maximum and a local minimum that coalesce and vanish as $a \to 0^+$.

## Quick verification

Check the second derivative $f_a''(x) = 6x$ for $a > 0$:

- $f_a''(-\sqrt{a}) = -6\sqrt{a} < 0 \implies$ local maximum at $x = -\sqrt{a}$. ✓
- $f_a''(\sqrt{a}) = 6\sqrt{a} > 0 \implies$ local minimum at $x = \sqrt{a}$. ✓
- For $a = 0$, $f_0''(0) = 0$ and $f_0'''(0) = 6 \neq 0$, confirming an inflection point at $x = 0$. ✓

## A concrete example

Compare three representative members of the family ($a = -1, \, 0, \, 1$):

- **$a = -1$:** $f_{-1}(x) = x^3 + 3x$, $f_{-1}'(x) = 3(x^2 + 1) \ge 3 > 0$ (always rising, minimum slope is $3$).
- **$a = 0$:** $f_0(x) = x^3$, $f_0'(x) = 3x^2 \ge 0$ (always rising, pauses with slope $0$ at $x = 0$).
- **$a = 1$:** $f_1(x) = x^3 - 3x$, $f_1'(x) = 3(x - 1)(x + 1)$ (local max $2$ at $x = -1$, local min $-2$ at $x = 1$).

## How I would explain this in class

> Differentiating $f_a(x) = x^3 - 3ax$ gives $f_a'(x) = 3(x^2 - a)$, so critical points satisfy $x^2 = a$. When $a < 0$, $x^2 = a$ has no real solutions and the cubic is strictly increasing. When $a = 0$, the two roots merge into a double root at $x = 0$, where $f_0'(x) = 3x^2$ doesn't change sign, giving a flat inflection point. When $a > 0$, $x^2 = a$ splits into two simple roots $x = \pm\sqrt{a}$ where $f_a'$ changes sign, creating a local maximum at $-\sqrt{a}$ and a local minimum at $+\sqrt{a}$.

## Related workbook topics

- [Exercise 1: A Cubic Polynomial](problem_01_solution.md)
- [Exercise 15: Find the Error in the Monotonicity Analysis](problem_15_solution.md)
