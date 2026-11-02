# Exercise 15. Observation Versus Proof

## The question

Choose one sequence and one function from this set. For the sequence, compute several values for increasingly large $n$. For the function, prepare a table of values with arguments approaching the limit point from the left and right. Sketch the behavior of both objects.

Compare the observation with the analytical result and explain why a finite number of calculations or a sketch does not constitute a proof that the limit exists.

## Before calculating: what idea do we need?

Numerical tables and graphs are indispensable **discovery tools**: they give us a conjecture for what a limit might be and help us catch algebra mistakes.

However, a limit is a statement about **infinitely many arguments**—either all $n$ beyond any threshold $N$ (for $n\to\infty$), or all $x$ in an arbitrarily small punctured neighborhood $(x_0-\delta, x_0+\delta)\setminus\{x_0\}$ (for $x\to x_0$). No finite table of numbers or finite-resolution drawing can check infinitely many inputs.

## 1. Chosen sequence: numerical table and sketch

We choose the sequence from Exercise 1:

$$a_n = \frac{4n^2-3n+1}{2n^2+5n-7},\qquad \text{with analytical limit } \lim_{n\to\infty}a_n = 2.$$

| $n$ | Numerator $4n^2-3n+1$ | Denominator $2n^2+5n-7$ | Value $a_n$ (rounded) | Distance $2-a_n$ |
|---|---|---|---|---|
| $2$ | $11$ | $11$ | $1.00000$ | $1.00000$ |
| $5$ | $86$ | $68$ | $1.26471$ | $0.73529$ |
| $10$ | $371$ | $243$ | $1.52675$ | $0.47325$ |
| $50$ | $9\,851$ | $5\,243$ | $1.87889$ | $0.12111$ |
| $100$ | $39\,701$ | $20\,493$ | $1.93729$ | $0.06271$ |
| $1000$ | $3\,997\,001$ | $2\,004\,993$ | $1.99352$ | $0.00648$ |

Sketch of the discrete points $(n, a_n)$ approaching the horizontal level $y=2$:

```
  a_n ^
  2.0 + - - - - - - - - - - - - - - - - - - - - - (limit L = 2)
      |                             *     *     *
  1.5 +                 *     *
      |           *
  1.0 +     *
      +-----+-----+-----+-----+-----+-----+-----> n
            2     5    10    50   100  1000
```

## 2. Chosen function: two-sided table and sketch

We choose the function from Exercise 8 as $x\to4$:

$$f(x) = \frac{\sqrt{x}-2}{x-4},\qquad \text{with analytical limit } \lim_{x\to4}f(x) = \frac{1}{4} = 0.25.$$

| Left approach ($x\to4^-$) | $f(x)$ (rounded) | Right approach ($x\to4^+$) | $f(x)$ (rounded) |
|---|---|---|---|
| $x=3.5$ | $0.25834$ | $x=4.5$ | $0.24264$ |
| $x=3.9$ | $0.25158$ | $x=4.1$ | $0.24846$ |
| $x=3.99$ | $0.25016$ | $x=4.01$ | $0.24984$ |
| $x=3.999$ | $0.25002$ | $x=4.001$ | $0.24998$ |

Sketch of the continuous curve $y=f(x)$ with a puncture (hole) at $(4, 0.25)$:

```
  y ^
0.5 + *
    |   \
0.25+ - - \ - - o - - - - - - - (limit L = 0.25 at hole x = 4)
    |             \       *
    +-----------+---+-----------+---> x
                0   4
```

## 3. Comparing observations with the analytical results

- For the sequence $a_n$, the table shows $a_n$ increasing toward $2$, with the gap $2-a_n\approx \dfrac{6.5}{n}$ shrinking by a factor of $10$ each time $n$ is multiplied by $10$. This matches our analytical result $\lim_{n\to\infty}a_n=2$ from factoring out $n^2$.
- For the function $f(x)$, the left-hand values decrease toward $0.25$ and the right-hand values increase toward $0.25$, pinching together at height $0.25$. This matches our analytical result $\lim_{x\to4}\dfrac{1}{\sqrt{x}+2}=\dfrac{1}{4}$.

## 4. Why finite calculations or a sketch never constitute a proof

1. **Delayed behavior beyond the table:** A sequence can match $2$ for the first $1000$ terms and still diverge—for instance, $b_n = 2 + 10^{-100}n$ is indistinguishable from $2$ at $n=1000$, yet $\lim_{n\to\infty}b_n=+\infty$.
2. **Hidden behavior closer to the limit point:** A function like $g(x)=\cos\left(\dfrac{2\pi}{x-4}\right)$ equals $1$ at every sample point $x = 4 \pm 10^{-k}$ ($k=1,2,3,\dots$), so a standard table of decimal steps would show $1.00000$ everywhere, even though $\lim_{x\to4}g(x)$ does not exist!
3. **Catastrophic cancellation and finite precision:** On a calculator or computer, evaluating $\dfrac{\sqrt{x}-2}{x-4}$ at $x=4+10^{-16}$ actually outputs $0$ instead of $0.25$ because floating-point arithmetic rounds $\sqrt{4+10^{-16}}$ to $2$.
4. **Finite resolution of a sketch:** A drawn line has positive thickness and is plotted through finitely many sample points, so it cannot reveal tiny jumps, rapid oscillations (like $\sin(1/x)$ near $0$), or distinguish $0.25$ from $0.2500001$.

## Quick verification

Let us verify the exact error formulas analytically:

- For $a_n$: $2 - a_n = \dfrac{13n-15}{2n^2+5n-7}$. At $n=1000$, this is $\dfrac{12\,985}{2\,004\,993}\approx 0.006476$, matching the table's $2-1.99352=0.00648$. ✓
- For $f(x)$: $f(x)-\dfrac{1}{4} = \dfrac{1}{\sqrt{x}+2}-\dfrac{1}{4} = \dfrac{2-\sqrt{x}}{4(\sqrt{x}+2)}$. At $x=3.99$, this is $\approx \dfrac{0.0025016}{15.99}\approx 0.000156$, matching $0.25016-0.25=0.00016$. ✓

## A concrete example

Consider the "deceptive" sequence

$$c_n = \frac{4n^2-3n+1}{2n^2+5n-7} + \left(\frac{n}{10\,000}\right)^{10}.$$

For $n=2, 5, 10, 50, 100, 1000$, the extra term $(n/10\,000)^{10}$ is at most $10^{-10}$, so $c_n$ produces the **exact same 5-decimal-place table** as $a_n$ above! Yet $\lim_{n\to\infty}c_n = +\infty$, proving that our finite table alone could never distinguish convergence to $2$ from divergence to $+\infty$.

## How I would explain this in class

> Tables and sketches are awesome for building intuition and double-checking our work—we can literally watch $a_n$ climb toward $2$ and $f(x)$ pinch toward $0.25$ from both sides of $x=4$. But a table only tests a handful of numbers. A sequence could blow up after $n=10^9$, a function could oscillate wildly between our chosen sample points, and calculators even lose accuracy when you divide two tiny numbers. Only an algebraic proof covers all infinitely many values.

## Related workbook topics

- [Exercise 1: Dominant terms in a sequence](problem_01_solution.md)
- [Exercise 8: A square root in a function limit](problem_08_solution.md)
