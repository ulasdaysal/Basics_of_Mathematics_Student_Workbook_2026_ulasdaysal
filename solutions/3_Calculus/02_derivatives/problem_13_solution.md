# Exercise 13. A Multi-Layer Composition

## The question

For

$$f(x)=e^{\sin(x^2)}$$

compute the derivative. First write the layers

$$x\longrightarrow x^2\longrightarrow \sin(x^2)\longrightarrow e^{\sin(x^2)}$$

and explain why differentiation moves through them in the reverse order.

## Before calculating: what idea do we need?

A three-layer composition $f(x)=F(G(H(x)))$ works like a three-stage pipeline:
- **Evaluation** starts at the innermost input $x$ and applies $H$, then $G$, then $F$ moving **inside-out**.
- **Differentiation** by the chain rule unwraps the layers moving **outside-in** (in the reverse order of evaluation), multiplying the derivative of each layer evaluated at everything inside it:

$$f'(x)=F'\big(G(H(x))\big)\cdot G'\big(H(x)\big)\cdot H'(x).$$

In Leibniz notation, if $u=x^2$, $v=\sin u$, and $y=e^v$, then

$$\frac{dy}{dx}=\frac{dy}{dv}\cdot\frac{dv}{du}\cdot\frac{du}{dx}.$$

## 1. Write the layers of evaluation

When we plug a number $x$ into $f(x)=e^{\sin(x^2)}$, we compute three intermediate steps in order from inside to outside:

$$x \xrightarrow{\text{square}} u=x^2 \xrightarrow{\text{sine}} v=\sin(x^2) \xrightarrow{\text{exponential}} y=e^{\sin(x^2)}.$$

- **Layer 1 (innermost)**: $u=H(x)=x^2$,
- **Layer 2 (middle)**: $v=G(u)=\sin u=\sin(x^2)$,
- **Layer 3 (outermost)**: $y=F(v)=e^v=e^{\sin(x^2)}$.

## 2. Differentiate layer by layer in reverse order

Unwrap the composition from the **outermost** layer to the **innermost** layer:

1. **Outermost layer ($e^v$)**: differentiate $e^v$ with respect to its argument $v=\sin(x^2)$:

$$\frac{dy}{dv}=e^v=e^{\sin(x^2)}.$$

2. **Middle layer ($\sin u$)**: differentiate $\sin u$ with respect to its argument $u=x^2$:

$$\frac{dv}{du}=\cos u=\cos(x^2).$$

3. **Innermost layer ($x^2$)**: differentiate $x^2$ with respect to $x$:

$$\frac{du}{dx}=2x.$$

## 3. Multiply the factors to obtain $f'(x)$

Multiply the three derivatives together:

$$f'(x)=e^{\sin(x^2)}\cdot\cos(x^2)\cdot 2x=2x\cos(x^2)e^{\sin(x^2)}.$$

## 4. Why differentiation moves in the reverse order of evaluation

Think of wrapping and unwrapping a gift box:
- When **evaluating** $f(x)$, $x$ is placed inside the squaring box $x^2$, which is placed inside the $\sin(\cdot)$ box, which is finally placed inside the $e^{(\cdot)}$ box.
- When **differentiating** $f(x)$, we ask how the final output $y=e^{\sin(x^2)}$ responds to a change in $x$. At the top level, $f(x)$ is an exponential function $e^{(\text{something})}$, so we must first open the outermost $e^{(\cdot)}$ box while keeping its contents $\sin(x^2)$ intact; only then does the chain rule ask us to differentiate what was inside ($\sin(x^2)$), which in turn requires opening the middle $\sin(\cdot)$ box before finally reaching the innermost $x^2$ box.

*(Note: because multiplication of real numbers is commutative, the final product $e^{\sin(x^2)}\cdot\cos(x^2)\cdot 2x=2x\cos(x^2)e^{\sin(x^2)}$ can be written in any order, even though the logical process of peeling off layers proceeds from outside to inside.)*

## Quick verification

Let us approximate $f(x)=e^{\sin(x^2)}$ near $x=0$ using $\sin u\approx u$ and $e^v\approx 1+v$:

$$f(x)=e^{\sin(x^2)}\approx e^{x^2}\approx 1+x^2\quad\text{for }x\text{ near }0.$$

Differentiating $1+x^2$ gives $2x$. Now check our exact formula as $x\to0$:

$$f'(x)=2x\cos(x^2)e^{\sin(x^2)}\approx 2x\cdot\cos(0)\cdot e^0=2x\cdot1\cdot1=2x.\quad\checkmark$$

Both the small-$x$ behavior and the exact derivative formula match.

## A concrete example

Evaluate $f(x)$ and $f'(x)$ at $x=\sqrt{\pi}\approx 1.7725$:

- Innermost layer: $u=(\sqrt{\pi})^2=\pi$,
- Middle layer: $v=\sin(\pi)=0$,
- Outermost layer: $f(\sqrt{\pi})=e^0=1$.
- Derivative at $x=\sqrt{\pi}$:

$$f'(\sqrt{\pi})=2\sqrt{\pi}\cos(\pi)e^{\sin(\pi)}=2\sqrt{\pi}(-1)(1)=-2\sqrt{\pi}\approx -3.5449.$$

Because $\cos(\pi)=-1<0$, the function is decreasing steeply as $x$ passes through $\sqrt{\pi}$.

## How I would explain this in class

> Evaluating $f(x)=e^{\sin(x^2)}$ goes from inside to outside: $x\to x^2\to\sin(x^2)\to e^{\sin(x^2)}$. Differentiating works in reverse, like peeling layers off from the outside in: first differentiate the outer exponential to get $e^{\sin(x^2)}$, then multiply by the derivative of the middle sine layer, $\cos(x^2)$, and finally multiply by the derivative of the inner square, $2x$, giving $f'(x)=2x\cos(x^2)e^{\sin(x^2)}$.

## Related workbook topics

- [Exercise 5: The Chain Rule as Working Through Layers](problem_05_solution.md)
- [Exercise 7: A Trigonometric Composition](problem_07_solution.md)
