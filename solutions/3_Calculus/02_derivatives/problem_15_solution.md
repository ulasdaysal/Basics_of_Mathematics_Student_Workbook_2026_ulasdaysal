# Exercise 15. The Difference Quotient as a Check of the Derivative

## The question

Choose one function from the problem set and a point $x_0$ at which the derivative exists. Compute $f'(x_0)$ exactly, and then calculate

$$\frac{f(x_0+h)-f(x_0)}{h}$$

for $h=1$, $0.1$, and $0.01$. Compare the values with $f'(x_0)$ and explain why the difference quotient approaching a single number is consistent with the definition of the derivative, while a few computations do not replace a limit argument.

## Before calculating: what idea do we need?

By definition, the derivative at $x_0$ is the limit of the difference quotient:

$$f'(x_0)=\lim_{h\to0}\frac{f(x_0+h)-f(x_0)}{h}.$$

For any specific nonzero number $h$, the difference quotient $\dfrac{f(x_0+h)-f(x_0)}{h}$ is the **secant slope** between $x_0$ and $x_0+h$. Evaluating this ratio for smaller and smaller steps ($h=1, 0.1, 0.01$) lets us **numerically observe** the secant slopes converging toward the tangent slope $f'(x_0)$ — a powerful sanity check on our derivative formula, though not a mathematical proof.

## 1. Choose a function and a point, and compute $f'(x_0)$ exactly

Let us choose the polynomial from Exercise 10 (and Exercise 11):

$$f(x)=x^2-3x+1 \qquad\text{at}\qquad x_0=2.$$

First compute the exact value and exact derivative at $x_0=2$:

- Function value: $f(2)=2^2-3(2)+1=4-6+1=-1$.
- Derivative formula: $f'(x)=2x-3$.
- Exact derivative at $x_0=2$:

$$f'(2)=2(2)-3=1.$$

## 2. Compute the difference quotient for $h=1$, $0.1$, and $0.01$

First let us simplify $f(2+h)$ for a general step $h$:

$$f(2+h)=(2+h)^2-3(2+h)+1=(4+4h+h^2)-(6+3h)+1=-1+h+h^2.$$

Therefore, for any $h\neq0$:

$$\frac{f(2+h)-f(2)}{h}=\frac{(-1+h+h^2)-(-1)}{h}=\frac{h+h^2}{h}=1+h.$$

Now evaluate for the three requested values of $h$:

1. **For $h=1$** ($x_0+h=3$, where $f(3)=3^2-3(3)+1=1$):

$$\frac{f(3)-f(2)}{1}=\frac{1-(-1)}{1}=2=1+1.$$

2. **For $h=0.1$** ($x_0+h=2.1$, where $f(2.1)=2.1^2-3(2.1)+1=-0.89$):

$$\frac{f(2.1)-f(2)}{0.1}=\frac{-0.89-(-1)}{0.1}=\frac{0.11}{0.1}=1.1=1+0.1.$$

3. **For $h=0.01$** ($x_0+h=2.01$, where $f(2.01)=2.01^2-3(2.01)+1=-0.9899$):

$$\frac{f(2.01)-f(2)}{0.01}=\frac{-0.9899-(-1)}{0.01}=\frac{0.0101}{0.01}=1.01=1+0.01.$$

## 3. Compare the values with $f'(2)=1$

| Step size $h$ | Point $x_0+h$ | Difference quotient $\dfrac{f(2+h)-f(2)}{h}$ | Exact derivative $f'(2)$ | Error $\vert\text{DQ}-f'(2)\vert$ |
| :---: | :---: | :---: | :---: | :---: |
| $1$ | $3$ | $2.00$ | $1$ | $1.00$ |
| $0.1$ | $2.1$ | $1.10$ | $1$ | $0.10$ |
| $0.01$ | $2.01$ | $1.01$ | $1$ | $0.01$ |

As $h$ shrinks by a factor of $10$ each time ($1\to 0.1\to 0.01$), the difference quotient $2.00\to 1.10\to 1.01$ gets steadily closer to $f'(2)=1$, and the discrepancy equals $h$.

## 4. Consistency vs. proof: why a few values do not replace a limit argument

- **Why it is consistent with the definition**: If $f'(x_0)=\lim_{h\to0}\frac{f(x_0+h)-f(x_0)}{h}$ exists, then for small values of $h$ the difference quotient must lie close to $f'(x_0)$. Seeing $2\to 1.1\to 1.01$ approach $1$ confirms that we did not make a sign or arithmetic error when computing $f'(2)=1$.
- **Why three values do not prove the limit exists**:
  1. Checking only $h=1, 0.1, 0.01$ tests only **three positive numbers** ($h>0$). It never checks negative steps $h<0$ (such as $h=-0.01$, which could approach a completely different left-hand slope if the function had a corner like in Exercise 14).
  2. Even for $h>0$, a function could behave nicely at $h=1, 0.1, 0.01$ and then oscillate wildly or jump at $h=0.0001$.
  3. Only the **algebraic limit argument** $\lim_{h\to0}(1+h)=1$ proves that the difference quotient converges to $1$ for **every** way $h$ can approach $0$ ($h\to0^+$ and $h\to0^-$).

## Quick verification

Let us also check negative steps $h=-0.1$ and $h=-0.01$ at $x_0=2$:

- For $h=-0.1$: $\dfrac{f(1.9)-f(2)}{-0.1}=\dfrac{-1.09-(-1)}{-0.1}=\dfrac{-0.09}{-0.1}=0.90=1-0.1$.
- For $h=-0.01$: $\dfrac{f(1.99)-f(2)}{-0.01}=\dfrac{-1.0099-(-1)}{-0.01}=\dfrac{-0.0099}{-0.01}=0.99=1-0.01$.

From the left ($0.90\to 0.99$) and from the right ($1.10\to 1.01$), the secant slopes sandwich the exact derivative $f'(2)=1$. ✓

## A concrete example

Why can testing only $h=1, 0.1, 0.01$ be fooled? Consider two examples:

1. **One-sided trap**: For $g(x)=|x-2|+(x-2)$ at $x_0=2$, testing $h=1, 0.1, 0.01$ gives difference quotients $2, 2, 2$, suggesting $g'(2)=2$. Yet for $h=-0.01$, the difference quotient is $0$, so $g'(2)$ does not exist at all!
2. **Tiny-scale trap**: For $k(x)=x^2-3x+1+\sin(100\pi x)$ at $x_0=2$, plugging in $h=1, 0.1, 0.01$ makes $\sin(100\pi(2+h))=\sin(200\pi+100\pi h)=0$ at all three points, giving the exact same table $2.00, 1.10, 1.01$, even though the actual derivative at $x=2$ is $1+100\pi\approx 315.16$!

## How I would explain this in class

> Choosing $f(x)=x^2-3x+1$ at $x_0=2$, the power rule gives the exact derivative $f'(2)=2(2)-3=1$. Computing the difference quotient $\frac{f(2+h)-f(2)}{h}=1+h$ for $h=1, 0.1, 0.01$ gives $2, 1.1, 1.01$, which clearly approaches $f'(2)=1$. This is a great numerical check that our derivative formula is right, but three sample points cannot replace a limit proof because they only test three positive values of $h$ and cannot rule out corners for $h<0$ or hidden oscillations at smaller scales.

## Related workbook topics

- [Exercise 10: The Tangent Line as an Application of the Derivative](problem_10_solution.md)
- [Exercise 11: Derivative from the Definition](problem_11_solution.md)
