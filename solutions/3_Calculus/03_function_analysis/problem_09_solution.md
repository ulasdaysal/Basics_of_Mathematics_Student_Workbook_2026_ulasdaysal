# Exercise 9. An Oblique Asymptote

## The question

Analyze the asymptotes of

$$f(x)=\frac{x^2+1}{x-1}.$$

Perform polynomial division and explain why the remainder term vanishes for large $|x|$.

## Before calculating: what idea do we need?

When the degree of the numerator of a rational function is **exactly $1$ greater** than the degree of the denominator, polynomial division splits $f(x)$ into a linear polynomial plus a proper fraction:

$$f(x) = \underbrace{(mx + b)}_{\text{linear part}} + \underbrace{\frac{r}{x - c}}_{\text{remainder term}}.$$

As $|x| \to \infty$, the remainder term shrinks to zero, meaning the graph of $f(x)$ becomes indistinguishable from the straight line $y = mx + b$ — an **oblique (slant) asymptote**.

## 1. Domain and polynomial division

- **Domain:** $x - 1 \neq 0 \implies D = \mathbb{R} \setminus \{1\} = (-\infty, 1) \cup (1, \infty)$.
- **Polynomial division:** Write $x^2 + 1 = (x^2 - 1) + 2 = (x - 1)(x + 1) + 2$ and divide by $x - 1$:

$$f(x) = \frac{x^2 + 1}{x - 1} = \frac{(x - 1)(x + 1) + 2}{x - 1} = x + 1 + \frac{2}{x - 1}.$$

Here the quotient is the linear function $y = x + 1$ and the remainder term is $\frac{2}{x - 1}$.

## 2. Vertical asymptote

At the excluded point $x = 1$, the numerator $x^2 + 1$ approaches $1^2 + 1 = 2 > 0$, while $x - 1 \to 0$:

$$\lim_{x\to 1^-} f(x) = \lim_{x\to 1^-} \left(x + 1 + \frac{2}{x - 1}\right) = 2 + (-\infty) = -\infty,$$

$$\lim_{x\to 1^+} f(x) = \lim_{x\to 1^+} \left(x + 1 + \frac{2}{x - 1}\right) = 2 + (+\infty) = +\infty.$$

Therefore, **$x = 1$ is a two-sided vertical asymptote**.

## 3. Oblique asymptote and why the remainder vanishes

Consider the vertical distance between the graph of $f(x)$ and the line $y = x + 1$:

$$f(x) - (x + 1) = \frac{2}{x - 1}.$$

Why does $\frac{2}{x - 1}$ vanish for large $|x|$? Because the numerator $2$ is fixed while the denominator $x - 1$ grows without bound in magnitude as $x \to +\infty$ or $x \to -\infty$. Dividing a fixed constant by an arbitrarily large number produces a result arbitrarily close to zero:

$$\lim_{x\to \pm\infty} \bigl(f(x) - (x + 1)\bigr) = \lim_{x\to \pm\infty} \frac{2}{x - 1} = 0.$$

Hence **$y = x + 1$ is a two-sided oblique asymptote** (and there are no horizontal asymptotes). Moreover, the sign of $\frac{2}{x-1}$ tells us which side of the asymptote the graph is on:

- For $x > 1$: $\frac{2}{x-1} > 0$, so the graph approaches $y = x + 1$ **from above**.
- For $x < 1$: $\frac{2}{x-1} < 0$, so the graph approaches $y = x + 1$ **from below**.

## Quick verification

Use the general limit formulas for an oblique asymptote $y = mx + b$:

$$m = \lim_{x\to\pm\infty} \frac{f(x)}{x} = \lim_{x\to\pm\infty} \frac{x^2 + 1}{x^2 - x} = 1,$$

$$b = \lim_{x\to\pm\infty} \bigl(f(x) - mx\bigr) = \lim_{x\to\pm\infty} \left(\frac{x^2 + 1}{x - 1} - x\right) = \lim_{x\to\pm\infty} \frac{x + 1}{x - 1} = 1.$$

This gives the exact same line $y = x + 1$. ✓

## A concrete example

Compare $f(x)$ with the line $y = x + 1$ for increasing values of $x$:

| $x$ | Line $y = x + 1$ | Remainder $\frac{2}{x-1}$ | Function $f(x)$ |
| :---: | :---: | :---: | :---: |
| $11$ | $12$ | $0.2$ | $12.2$ |
| $101$ | $102$ | $0.02$ | $102.02$ |
| $1001$ | $1002$ | $0.002$ | $1002.002$ |

Each time $x - 1$ is multiplied by $10$, the gap between the curve $f(x)$ and the line $y = x + 1$ shrinks by a factor of $10$.

## How I would explain this in class

> By dividing $x^2 + 1$ by $x - 1$, we rewrite $f(x)$ as $(x + 1) + \frac{2}{x - 1}$. Near $x = 1$, the fraction $\frac{2}{x-1}$ blows up, creating the vertical asymptote $x = 1$. Far away from the origin ($|x| \to \infty$), dividing $2$ by a huge number $x - 1$ gives almost zero, so the fraction $\frac{2}{x-1}$ disappears and the graph hugs the slant line $y = x + 1$.

## Related workbook topics

- [Exercise 3: A Rational Function](problem_03_solution.md)
- [Exercise 4: A Function with Two Vertical Asymptotes](problem_04_solution.md)
