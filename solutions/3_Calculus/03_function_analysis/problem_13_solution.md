# Exercise 13. A Logarithm and an Asymptote

## The question

Perform a complete analysis of

$$f(x)=\frac{\ln x}{x},\qquad x>0.$$

Find the maximum and the behavior at the ends of the domain. Explain which information is necessary for a correct sketch.

## Before calculating: what idea do we need?

Just as $xe^{-x}$ pits linear growth against exponential decay, $f(x) = \frac{\ln x}{x}$ pits slow logarithmic growth in the numerator against faster linear growth in the denominator:

- Near $x = 0^+$, $\ln x \to -\infty$ and dividing by a tiny positive $x$ makes it plunge to $-\infty$ even faster.
- For large $x$, $\ln x$ grows much more slowly than $x$, so the ratio $\frac{\ln x}{x}$ peaks and then decays back toward $0$.

## 1. Domain, zero, and sign

- **Domain:** $D = (0, \infty)$ (since $\ln x$ requires $x > 0$).
- **Zero and sign:** Since $x > 0$, $f(x)$ has the same sign as $\ln x$:
  - $f(1) = \frac{\ln 1}{1} = 0$ is the unique zero ($x$-intercept at $(1, 0)$),
  - $f(x) < 0$ on $(0, 1)$,
  - $f(x) > 0$ on $(1, \infty)$.

## 2. Limits at the ends of the domain and asymptotes

- **Right-hand limit at $x = 0^+$ (vertical asymptote):**
  As $x \to 0^+$, $\ln x \to -\infty$ and $\frac{1}{x} \to +\infty$, so their product is not indeterminate:
  $$\lim_{x\to 0^+} \frac{\ln x}{x} = (-\infty)\cdot(+\infty) = -\infty.$$
  Thus **$x = 0$ (the $y$-axis) is a vertical asymptote**.
- **Limit as $x \to \infty$ (horizontal asymptote):**
  This is of type $\frac{\infty}{\infty}$. By L'Hôpital's rule (or standard growth rates):
  $$\lim_{x\to\infty} \frac{\ln x}{x} \stackrel{\text{H}}{=} \lim_{x\to\infty} \frac{\frac{1}{x}}{1} = 0.$$
  Thus **$y = 0$ (the positive $x$-axis) is a horizontal asymptote** as $x \to \infty$, approached from above.

## 3. First and second derivatives: maximum, monotonicity, and convexity

Using the quotient rule on $(0, \infty)$:

$$f'(x) = \frac{\frac{1}{x}\cdot x - (\ln x)\cdot 1}{x^2} = \frac{1 - \ln x}{x^2}.$$

Since $x^2 > 0$, the sign of $f'(x)$ is the sign of $1 - \ln x$:

$$1 - \ln x = 0 \iff \ln x = 1 \iff x = e \approx 2.718.$$

| Interval / Point | $(0, e)$ | $x = e$ | $(e, \infty)$ |
| :--- | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+$ | $0$ | $-$ |
| Behavior of $f(x)$ | $\nearrow$ ($-\infty$ to $\frac{1}{e}$) | **Global max** ($\frac{1}{e}$) | $\searrow$ ($\frac{1}{e}$ to $0$) |

- **Strictly increasing** on $(0, e]$ and **strictly decreasing** on $[e, \infty)$.
- **Global and local maximum** at $x = e$ with value $f(e) = \frac{\ln e}{e} = \frac{1}{e} \approx 0.368$.

Differentiating $f'(x) = (1 - \ln x)x^{-2}$ gives the second derivative:

$$f''(x) = \frac{-\frac{1}{x}\cdot x^2 - (1 - \ln x)\cdot 2x}{x^4} = \frac{2\ln x - 3}{x^3}.$$

Setting $2\ln x - 3 = 0$ gives $\ln x = \frac{3}{2} \implies x = e^{3/2} = e\sqrt{e} \approx 4.482$:

- **Concave ($\cap$)** on $(0, e^{3/2}]$,
- **Convex ($\cup$)** on $[e^{3/2}, \infty)$,
- **Inflection point** at $\left(e^{3/2}, \frac{3}{2e^{3/2}}\right) \approx (4.48, 0.335)$.

## 4. Which information is necessary for a correct sketch?

To avoid drawing a misleading graph, five pieces of information are indispensable:

1. **The domain $(0, \infty)$ and vertical asymptote $x = 0$** ($\lim_{x\to 0^+} f(x) = -\infty$), which confines the graph to the right of the $y$-axis.
2. **The unique zero $(1, 0)$**, where the curve crosses from below the $x$-axis to above it.
3. **The global maximum at $(e, \frac{1}{e})$**, where the curve stops rising and turns downward.
4. **The horizontal asymptote $\lim_{x\to\infty} f(x) = 0$**, which shows the curve does not dive back below the $x$-axis after $x = e$, but instead stays positive and approaches $y = 0$ from above.
5. **The inflection point at $x = e^{3/2}$**, where the curve switches from concave ($\cap$) to convex ($\cup$) so it can flatten out along $y = 0$.

## Quick verification

- Substitute $t = \ln x$ (so $x = e^t$): then $f(e^t) = \frac{t}{e^t} = te^{-t}$, which is the exact function from Exercise 5! Since $te^{-t}$ attains its maximum $\frac{1}{e}$ at $t = 1$ and has an inflection point at $t = 2$ (for $t$ as the variable, whereas in $x$-coordinates $f''(x) = 0$ at $t = \frac{3}{2}$), the maximum $\frac{1}{e}$ at $\ln x = 1 \iff x = e$ is confirmed immediately. ✓

## A concrete example

A famous bonus of analyzing $f(x) = \frac{\ln x}{x}$ is that it compares $a^b$ vs. $b^a$ without a calculator! For instance, which is larger: $e^\pi$ or $\pi^e$?

Since $\pi > e$ and $f(x) = \frac{\ln x}{x}$ is strictly decreasing on $[e, \infty)$, we have

$$f(e) > f(\pi) \implies \frac{\ln e}{e} > \frac{\ln \pi}{\pi} \implies \pi \ln e > e \ln \pi \implies \ln(e^\pi) > \ln(\pi^e) \implies e^\pi > \pi^e.$$

## How I would explain this in class

> On $(0, \infty)$, the function $f(x) = \frac{\ln x}{x}$ starts at $-\infty$ along the vertical asymptote $x = 0$, crosses the $x$-axis at $(1, 0)$, and climbs to a single global maximum of $\frac{1}{e}$ at $x = e$ where $f'(x) = \frac{1 - \ln x}{x^2} = 0$. For $x > e$, $\ln x > 1$ makes the derivative negative, so the graph decreases, flips from concave to convex at $x = e^{3/2}$, and glides down toward the horizontal asymptote $y = 0$ from above.

## Related workbook topics

- [Exercise 5: An Exponential Function with a Maximum](problem_05_solution.md)
- [Exercise 6: A Logarithmic Function](problem_06_solution.md)
