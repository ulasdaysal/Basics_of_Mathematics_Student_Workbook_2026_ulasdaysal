# Exercise 8. Two Exponential Functions

## The question

For

$$f(x)=e^{2x-3}+5^x$$

compute the derivative. Explain why the factor $2$ appears in the first term and why $\ln 5$ appears in the second.

## Before calculating: what idea do we need?

Both terms in $f(x)=e^{2x-3}+5^x$ are exponential functions, because the variable $x$ is in the **exponent** rather than the base. However, they differ from the standard exponential $e^x$ in two distinct ways:

1. **First term ($e^{2x-3}$)**: the base is the natural base $e$, where $\dfrac{d}{du}(e^u)=e^u$, but the exponent is a composite linear function $u(x)=2x-3$.
2. **Second term ($5^x$)**: the exponent is simply $x$, but the base is $a=5\neq e$, for which

$$\frac{d}{dx}(a^x)=a^x\ln a.$$

Interestingly, both extra factors can be understood through the **chain rule** once we rewrite $5^x=e^{x\ln 5}$.

## 1. Differentiate the first term $e^{2x-3}$

View $e^{2x-3}$ as a composition $e^{u(x)}$ with inner function $u(x)=2x-3$:

- Derivative of outer function $e^u$: $e^u=e^{2x-3}$,
- Derivative of inner function $u(x)=2x-3$: $u'(x)=2$.

By the chain rule:

$$\frac{d}{dx}\left(e^{2x-3}\right)=e^{2x-3}\cdot 2=2e^{2x-3}.$$

## 2. Differentiate the second term $5^x$

Apply the general exponential derivative rule $\dfrac{d}{dx}(a^x)=a^x\ln a$ with $a=5$:

$$\frac{d}{dx}\left(5^x\right)=5^x\ln 5.$$

## 3. Combine to get $f'(x)$

Adding the derivatives of the two terms gives:

$$f'(x)=2e^{2x-3}+5^x\ln 5.$$

## 4. Why $2$ appears in the first term and $\ln 5$ in the second

Both factors measure the **rate of change of the natural-base exponent**:

- **Why $2$ appears in $2e^{2x-3}$**: The base is already $e$ (for which $\ln e=1$), so differentiating the outer exponential produces no logarithm factor. Instead, the exponent $u=2x-3$ changes twice as fast as $x$ ($\frac{du}{dx}=2$), so the chain rule multiplies by $2$.
- **Why $\ln 5$ appears in $5^x\ln 5$**: Since $5=e^{\ln 5}$, we can rewrite $5^x$ in base $e$ as

$$5^x=\left(e^{\ln 5}\right)^x=e^{(\ln 5)x}.$$

Now apply the exact same chain rule as in the first term! The inner linear exponent is $v(x)=(\ln 5)x$, whose derivative with respect to $x$ is $v'(x)=\ln 5$. Thus:

$$\frac{d}{dx}\left(5^x\right)=\frac{d}{dx}\left(e^{(\ln 5)x}\right)=e^{(\ln 5)x}\cdot\ln 5=5^x\ln 5.$$

So $\ln 5\approx 1.6094$ is the conversion factor that rescales base-$5$ growth into natural (base-$e$) instantaneous growth.

## Quick verification

We can also rewrite the first term using exponent laws before differentiating:

$$e^{2x-3}=e^{-3}\cdot e^{2x}=e^{-3}\cdot\left(e^2\right)^x.$$

Viewing this as a constant $e^{-3}$ times an exponential with base $a=e^2$:

$$\frac{d}{dx}\left(e^{-3}(e^2)^x\right)=e^{-3}(e^2)^x\ln(e^2)=e^{-3}e^{2x}\cdot 2=2e^{2x-3}.\quad\checkmark$$

Both perspectives — chain rule on $e^{u(x)}$ and base-change rule $a^x\ln a$ — agree completely!

## A concrete example

At $x=1.5$:

- The first term has exponent $2(1.5)-3=0$, so $e^{2(1.5)-3}=e^0=1$, and its instantaneous rate of change is $2e^0=2$.
- The second term has value $5^{1.5}=5\sqrt{5}\approx 11.1803$, and its instantaneous rate of change is $5^{1.5}\ln 5\approx 11.1803\times 1.6094\approx 17.994$.
- In total, $f'(1.5)=2+5\sqrt{5}\ln 5\approx 19.994$.

## How I would explain this in class

> The derivative of $f(x)=e^{2x-3}+5^x$ is $f'(x)=2e^{2x-3}+5^x\ln 5$. In the first term, the base is $e$, so the exponential keeps its form and the chain rule multiplies by $(2x-3)'=2$. In the second term, the base is $5$ instead of $e$; since $5^x=e^{x\ln 5}$, differentiating brings down the constant factor $\ln 5$ from the exponent.

## Related workbook topics

- [Exercise 5: The Chain Rule as Working Through Layers](problem_05_solution.md)
- [Exercise 13: A Multi-Layer Composition](problem_13_solution.md)
