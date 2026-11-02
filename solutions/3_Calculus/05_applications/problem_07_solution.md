# Exercise 7. Exponential Growth

## The question

Assume the population model

$$N(t)=N_0 e^{kt},\qquad k>0.$$

1. Verify by differentiation that the model satisfies the relation $N'(t)=kN(t)$.
2. Find the population doubling time.
3. Explain why the doubling time does not depend on $N_0$.

## Before calculating: what idea do we need?

Many biological, physical, and financial processes grow at a rate directly proportional to their current size: twice as many individuals produce twice as many offspring per unit time. The mathematical function whose derivative is a constant multiple of itself is the exponential function $e^{kt}$, differentiated via the chain rule: $\frac{d}{dt}(e^{kt})=k e^{kt}$.

## 1. Verifying the differential relation $N'(t)=kN(t)$

Differentiating $N(t)=N_0 e^{kt}$ with respect to $t$ (treating the initial size $N_0$ and growth constant $k>0$ as constants) and applying the chain rule to $e^{kt}$ gives:

$$N'(t) = \frac{d}{dt}\bigl(N_0 e^{kt}\bigr) = N_0 \cdot \frac{d}{dt}\bigl(e^{kt}\bigr) = N_0 \cdot k e^{kt} = k\bigl(N_0 e^{kt}\bigr) = k N(t).$$

Thus, at every instant $t$, the rate of growth $N'(t)$ equals the relative growth rate $k$ times the current population $N(t)$.

## 2. Finding the population doubling time

The doubling time $T_{\text{double}}$ is the time $t$ needed for the population to reach twice its initial value, i.e., $N(t)=2N_0$:

$$N_0 e^{k T_{\text{double}}} = 2N_0.$$

Assuming $N_0>0$, we divide both sides by $N_0$:

$$e^{k T_{\text{double}}} = 2.$$

Taking the natural logarithm of both sides and dividing by $k>0$ yields:

$$k T_{\text{double}} = \ln 2 \implies T_{\text{double}} = \frac{\ln 2}{k}.$$

## 3. Why the doubling time does not depend on $N_0$

There are two complementary ways to understand why $N_0$ cancels out:

- **Algebraic scaling:** $N_0$ is a multiplicative scale factor in $N(t)=N_0 e^{kt}$. Asking when $N(t)$ reaches $2N_0$ is asking when the growth factor $N(t)/N_0 = e^{kt}$ reaches $2$, which depends only on $k$.
- **Proportionality of growth:** Because $N'(t)=kN(t)$, each individual (or unit of population) reproduces at the same average rate $k$ independently of how many other individuals exist. A population that is $10$ times larger has $10$ times as much absolute growth $N'(t)$ to achieve before doubling, and it also has $10$ times as many individuals contributing to that growth, so the two factors of $10$ cancel completely.

## 4. Extending to any interval $[t_0, t_0 + T_{\text{double}}]$

Not only does the initial value $N_0$ not matter, the starting time $t_0$ does not matter either:

$$N(t_0 + T_{\text{double}}) = N_0 e^{k(t_0 + \frac{\ln 2}{k})} = N_0 e^{kt_0} e^{\ln 2} = 2 N(t_0).$$

In exponential growth, the population doubles over **every** time window of length $\frac{\ln 2}{k}$.

## Quick verification

Let us substitute $t=T_{\text{double}}=\frac{\ln 2}{k}$ back into $N(t)$:

$$N\left(\frac{\ln 2}{k}\right) = N_0 e^{k\cdot\frac{\ln 2}{k}} = N_0 e^{\ln 2} = 2N_0. \quad \checkmark$$

Similarly, after $m$ doubling periods ($t=m\frac{\ln 2}{k}$), $N(t)=N_0 e^{m\ln 2}=2^m N_0$. ✓

## A concrete example

Suppose a bacterial colony grows with $k=0.2\text{ h}^{-1}$ ($20\%$ continuous relative growth per hour). Its doubling time is

$$T_{\text{double}} = \frac{\ln 2}{0.2} \approx \frac{0.6931}{0.2} \approx 3.47\text{ hours}.$$

Whether a dish starts with $N_0=100$ bacteria (growing to $200$) or $N_0=1\,000\,000$ bacteria (growing to $2\,000\,000$), both dishes double in exactly $3.47\text{ hours}$.

## How I would explain this in class

> By the chain rule, differentiating $N(t)=N_0 e^{kt}$ pulls down a factor of $k$, giving $N'(t)=k N_0 e^{kt}=k N(t)$. To find when the population doubles, we solve $N_0 e^{kt}=2N_0$. Dividing both sides by $N_0$ immediately eliminates $N_0$, leaving $e^{kt}=2$, so $t=\frac{\ln 2}{k}$. Physically, a larger starting population needs a larger absolute increase to double, but its growth rate $N'(t)=kN(t)$ is proportionally larger by the exact same factor, so the time required to double is always constant.

## Related workbook topics

- [Exercise 1: Motion — from Position to Velocity](problem_01_solution.md)
- [Exercise 8: Number of Requests Handled by a Server](problem_08_solution.md)
