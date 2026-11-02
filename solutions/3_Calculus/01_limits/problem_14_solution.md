# Exercise 14. A $0/0$ Limit with Trigonometry

## The question

Compute

$$\lim_{x\to0}\frac{1-\cos x}{x^2}.$$

Justify the result without using l'Hôpital's rule, using a trigonometric identity and the fundamental limit.

## Before calculating: what idea do we need?

When $x\to0$, $\cos x\to \cos 0 = 1$, so both the numerator $1-\cos x$ and the denominator $x^2$ approach $0$, giving the indeterminate form $\dfrac{0}{0}$.

Notice the $x^2$ in the denominator: this is a clue that $1-\cos x$ vanishes like the **square** of a sine! We have two classic trigonometric identities to turn $1-\cos x$ into a square of sine:

1. **Half-angle identity:** $1-\cos x = 2\sin^2\left(\dfrac{x}{2}\right)$, or
2. **Pythagorean conjugate:** multiplying top and bottom by $1+\cos x$ gives $(1-\cos x)(1+\cos x)=1-\cos^2 x=\sin^2 x$.

Let us carry out the half-angle method step by step, and then use the conjugate method as our verification!

## 1. Apply the half-angle trigonometric identity

Recall the double-angle formula $\cos x = 1 - 2\sin^2\left(\dfrac{x}{2}\right)$, which rearranges to:

$$1-\cos x = 2\sin^2\left(\frac{x}{2}\right).$$

Substituting this into the quotient gives:

$$\frac{1-\cos x}{x^2} = \frac{2\sin^2\left(\dfrac{x}{2}\right)}{x^2}.$$

## 2. Match the argument $\dfrac{x}{2}$ in the denominator

Because $\sin\left(\dfrac{x}{2}\right)$ is squared, we need $\left(\dfrac{x}{2}\right)^2 = \dfrac{x^2}{4}$ in the denominator. Writing $x^2 = 4\left(\dfrac{x}{2}\right)^2$:

$$\frac{2\sin^2\left(\dfrac{x}{2}\right)}{x^2} = \frac{2\sin^2\left(\dfrac{x}{2}\right)}{4\left(\dfrac{x}{2}\right)^2} = \frac{1}{2}\left(\frac{\sin\left(\dfrac{x}{2}\right)}{\dfrac{x}{2}}\right)^2.$$

## 3. Apply the fundamental trigonometric limit

Let $u=\dfrac{x}{2}$. As $x\to0$, $u\to0$, so by the fundamental trigonometric limit:

$$\lim_{x\to0}\frac{\sin\left(\dfrac{x}{2}\right)}{\dfrac{x}{2}} = \lim_{u\to0}\frac{\sin u}{u} = 1.$$

Therefore, using the limit laws for products and powers:

$$\lim_{x\to0}\frac{1-\cos x}{x^2} = \frac{1}{2}\cdot 1^2 = \frac{1}{2}.$$

## 4. Why the denominator had to be $x^2$ (and not $x$)

Geometrically, on the unit circle at angle $x$, $\sin x$ is the vertical leg (which grows linearly with $x$), whereas $1-\cos x$ is the tiny horizontal gap between $(1,0)$ and $(\cos x, 0)$, which grows quadratically like $\dfrac{1}{2}x^2$. That is why $\lim_{x\to0}\dfrac{1-\cos x}{x^2}=\dfrac{1}{2}$ is finite and nonzero, whereas $\lim_{x\to0}\dfrac{1-\cos x}{x} = \lim_{x\to0}x\cdot\dfrac{1-\cos x}{x^2} = 0\cdot\dfrac{1}{2}=0$.

## Quick verification

Let us check the result using the **conjugate method** by multiplying top and bottom by $1+\cos x$:

$$\frac{1-\cos x}{x^2} = \frac{(1-\cos x)(1+\cos x)}{x^2(1+\cos x)} = \frac{1-\cos^2 x}{x^2(1+\cos x)} = \left(\frac{\sin x}{x}\right)^2\cdot\frac{1}{1+\cos x}.$$

Taking the limit as $x\to0$ gives $1^2\cdot\dfrac{1}{1+\cos 0} = 1\cdot\dfrac{1}{1+1} = \dfrac{1}{2}$. ✓

## A concrete example

Evaluate $\dfrac{1-\cos x}{x^2}$ for $x=0.1$ and $x=0.01$ radians:

- For $x=0.1$: $\cos(0.1)\approx 0.99500417$, so $\dfrac{1-0.99500417}{0.01} = \dfrac{0.00499583}{0.01} \approx 0.49958$.
- For $x=0.01$: $\cos(0.01)\approx 0.9999500004$, so $\dfrac{1-0.9999500004}{0.0001} \approx 0.499996$.

Both values are just below $\dfrac{1}{2}=0.5$.

## How I would explain this in class

> Plugging in $x=0$ gives $0/0$. There are two great ways to turn $1-\cos x$ into $\sin^2$ so we can use $\dfrac{\sin u}{u}\to 1$. Either use the half-angle identity $1-\cos x = 2\sin^2(x/2)$ to get $\dfrac{2\sin^2(x/2)}{4(x/2)^2}\to\dfrac{2}{4}=\dfrac{1}{2}$, or multiply top and bottom by $1+\cos x$ to get $\left(\dfrac{\sin x}{x}\right)^2\dfrac{1}{1+\cos x}\to 1^2\cdot\dfrac{1}{1+1}=\dfrac{1}{2}$.

## Related workbook topics

- [Exercise 8: A square root in a function limit](problem_08_solution.md)
- [Exercise 13: Fundamental trigonometric limit](problem_13_solution.md)
