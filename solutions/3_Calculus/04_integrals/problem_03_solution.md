# Exercise 3. Recognizing Basic Antiderivatives

## The question

Compute

$$\int\left(2e^x+3\cos x-4\sin x\right)\,dx.$$

Match each term with a known derivative and verify the entire result with one differentiation.

## Before calculating: what idea do we need?

By **linearity of the integral**, we can integrate a sum or difference term by term and pull constant multipliers in front:

$$\int \bigl(a\,f(x)+b\,g(x)\bigr)\,dx = a\int f(x)\,dx + b\int g(x)\,dx.$$

For elementary transcendental functions, integration relies on recognizing basic derivative formulas in reverse:
- $\dfrac{d}{dx}(e^x)=e^x \implies \int e^x\,dx=e^x+C$,
- $\dfrac{d}{dx}(\sin x)=\cos x \implies \int \cos x\,dx=\sin x+C$,
- $\dfrac{d}{dx}(\cos x)=-\sin x \implies \int (-\sin x)\,dx=\cos x+C$ (or $\int \sin x\,dx=-\cos x+C$).

Paying close attention to the plus and minus signs on sine and cosine is the key step.

## 1. Matching each term with a known derivative

We look at each piece of the integrand $2e^x+3\cos x-4\sin x$:

1. **Exponential term $2e^x$:**
   Since $\dfrac{d}{dx}(e^x)=e^x$, multiplying by $2$ gives $\dfrac{d}{dx}(2e^x)=2e^x$.
2. **Cosine term $3\cos x$:**
   Since $\dfrac{d}{dx}(\sin x)=\cos x$, multiplying by $3$ gives $\dfrac{d}{dx}(3\sin x)=3\cos x$.
3. **Sine term $-4\sin x$:**
   Notice that $\dfrac{d}{dx}(\cos x)=-\sin x$ already contains the minus sign! Multiplying by $+4$ gives:
   $$\frac{d}{dx}(4\cos x)=4(-\sin x)=-4\sin x.$$

## 2. Combining the terms into the indefinite integral

Adding the antiderivatives of the three pieces and including the constant of integration $C$:

$$\int\left(2e^x+3\cos x-4\sin x\right)\,dx = 2e^x+3\sin x+4\cos x+C.$$

## 3. Why the sign on $4\cos x$ is positive

Students often confuse the signs when integrating $\sin x$ and $\cos x$. Here we can think of $-4\sin x$ in two equivalent ways:
- Either factor out $-4$: $-4\int\sin x\,dx = -4(-\cos x)=+4\cos x$,
- Or group the minus sign with $\sin x$: $+4\int(-\sin x)\,dx = +4\cos x$ because $-\sin x$ is directly the derivative of $\cos x$.

Both perspectives show why the result has $+4\cos x$.

## Quick verification

We differentiate the entire family $F(x)=2e^x+3\sin x+4\cos x+C$ in one step:

$$F'(x)=\frac{d}{dx}\left(2e^x+3\sin x+4\cos x+C\right)=2e^x+3\cos x+4(-\sin x)+0=2e^x+3\cos x-4\sin x.$$

This matches the original integrand, including every sign. ✓

## A concrete example

Let us check the rate of change at $x=0$:
- The integrand at $x=0$ gives the target slope:
  $$f(0)=2e^0+3\cos 0-4\sin 0=2(1)+3(1)-4(0)=5.$$
- Near $x=0$, our antiderivative (with $C=0$) behaves like:
  $$F_0(x)=2e^x+3\sin x+4\cos x,\qquad F_0(0)=2(1)+3(0)+4(1)=6,$$
  and its derivative at $x=0$ is $F_0'(0)=2e^0+3\cos 0-4\sin 0=5$. If we had mistakenly written $-4\cos x$, the derivative at $x=\pi/2$ would be $+4$ instead of $-4$.

## How I would explain this in class

> Instead of memorizing a separate list of integral sign rules, I match each term directly to a derivative I already know. The derivative of $e^x$ is $e^x$, so $2e^x$ integrates to $2e^x$. The derivative of $\sin x$ is $+\cos x$, so $3\cos x$ integrates to $3\sin x$. And since the derivative of $\cos x$ is $-\sin x$, the term $-4\sin x$ already has the minus sign built in, so it integrates to $+4\cos x$. A quick differentiation at the end guarantees I didn't flip a sign.

## Related workbook topics

- [Exercise 1: Antiderivative and Verification](problem_01_solution.md)
- [Exercise 11: Choose the Method First](problem_11_solution.md)
