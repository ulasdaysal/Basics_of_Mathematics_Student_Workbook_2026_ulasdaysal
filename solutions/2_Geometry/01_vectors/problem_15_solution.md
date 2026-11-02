# Exercise 15. Comparing Directions Using the Cosine of the Angle

## The question

Given

$$a=(1,2,1),\qquad b=(2,4,2),\qquad c=(2,0,3).$$

For each pair, compute

$$\frac{u\cdot v}{\|u\|\,\|v\|}.$$

Order the pairs by increasing angle between the vectors. Explain why for $a$ and $b$ the value is $1$ even though the vectors have different lengths.

## Before calculating: what idea do we need?

For any two nonzero vectors $u$ and $v$, the quantity

$$\cos\theta = \frac{u\cdot v}{\|u\|\,\|v\|}$$

is the **cosine of the angle** $\theta \in [0,\pi]$ between them. Notice that we can also write it as the dot product of their **unit normalizations**:

$$\frac{u\cdot v}{\|u\|\,\|v\|} = \left(\frac{u}{\|u\|}\right)\cdot\left(\frac{v}{\|v\|}\right).$$

Because the function $\cos\theta$ is **strictly decreasing** on the interval $[0,\pi]$ (from $\cos 0 = 1$ down to $\cos\pi = -1$), a **larger cosine means a smaller angle**, and a **smaller cosine means a larger angle**.

## 1. Computing the lengths of $a,b,c$

First, we compute the norm of each vector:

$$\|a\| = \sqrt{1^2+2^2+1^2} = \sqrt{1+4+1} = \sqrt{6},$$

$$\|b\| = \sqrt{2^2+4^2+2^2} = \sqrt{4+16+4} = \sqrt{24} = 2\sqrt{6},$$

$$\|c\| = \sqrt{2^2+0^2+3^2} = \sqrt{4+0+9} = \sqrt{13}.$$

## 2. Computing $\dfrac{u\cdot v}{\|u\|\,\|v\|}$ for each pair

1. **Pair $(a,b)$:**
   $$a\cdot b = 1(2) + 2(4) + 1(2) = 2 + 8 + 2 = 12,$$
   $$\cos\angle(a,b) = \frac{a\cdot b}{\|a\|\,\|b\|} = \frac{12}{\sqrt{6}\cdot 2\sqrt{6}} = \frac{12}{12} = 1.$$
2. **Pair $(a,c)$:**
   $$a\cdot c = 1(2) + 2(0) + 1(3) = 2 + 0 + 3 = 5,$$
   $$\cos\angle(a,c) = \frac{a\cdot c}{\|a\|\,\|c\|} = \frac{5}{\sqrt{6}\,\sqrt{13}} = \frac{5}{\sqrt{78}} \approx 0.566.$$
3. **Pair $(b,c)$:**
   $$b\cdot c = 2(2) + 4(0) + 2(3) = 4 + 0 + 6 = 10,$$
   $$\cos\angle(b,c) = \frac{b\cdot c}{\|b\|\,\|c\|} = \frac{10}{2\sqrt{6}\,\sqrt{13}} = \frac{5}{\sqrt{78}} \approx 0.566.$$

## 3. Ordering the pairs by increasing angle

Comparing the cosines:

$$\cos\angle(a,b) = 1 > \cos\angle(a,c) = \cos\angle(b,c) = \frac{5}{\sqrt{78}}.$$

Since $\cos\theta$ decreases as $\theta$ increases on $[0,\pi]$:

- $\angle(a,b) = \arccos(1) = 0^\circ$ ($0\text{ rad}$) is the **smallest angle**,
- $\angle(a,c) = \angle(b,c) = \arccos\!\left(\frac{5}{\sqrt{78}}\right) \approx 55.5^\circ$ ($0.969\text{ rad}$) are **equal and larger**.

So in order of increasing angle:

$$\angle(a,b) < \angle(a,c) = \angle(b,c).$$

## 4. Why the value for $a$ and $b$ is $1$ despite different lengths

Notice that $b = (2,4,2) = 2(1,2,1) = 2a$. The vector $b$ is a **positive scalar multiple** of $a$: it points in the exact same direction and orientation as $a$, so the angle between $a$ and $b$ is $0^\circ$ and $\cos 0^\circ = 1$.

Algebraically, when we replace $a$ by $b=2a$ in the cosine formula, the scaling factor $2$ appears in both the numerator and the denominator and **cancels out completely**:

$$\frac{a\cdot(2a)}{\|a\|\,\|2a\|} = \frac{2(a\cdot a)}{2\|a\|\,\|a\|} = \frac{\|a\|^2}{\|a\|^2} = 1.$$

For the exact same reason, $\cos\angle(a,c)$ and $\cos\angle(b,c)$ are identical: dividing by $\|u\|\,\|v\|$ normalizes both vectors to unit length first, so $\frac{u\cdot v}{\|u\|\,\|v\|}$ measures **pure direction** and is completely independent of vector length.

## Quick verification

Let us normalize $a$ and $b$ first:

$$\hat{a} = \frac{a}{\|a\|} = \frac{1}{\sqrt{6}}(1,2,1),\qquad \hat{b} = \frac{b}{\|b\|} = \frac{1}{2\sqrt{6}}(2,4,2) = \frac{1}{\sqrt{6}}(1,2,1).$$

Because $\hat{a} = \hat{b}$, their unit direction vectors are identical! Therefore:

- $\hat{a}\cdot\hat{b} = \|\hat{a}\|^2 = 1$, $\checkmark$
- $\hat{a}\cdot\hat{c} = \hat{b}\cdot\hat{c} = \frac{5}{\sqrt{78}}$. $\checkmark$

Also note that $\left(\frac{5}{\sqrt{78}}\right)^2 = \frac{25}{78} < 1$, satisfying the Cauchy–Schwarz inequality $|u\cdot v| \le \|u\|\,\|v\|$. $\checkmark$

## A concrete example

In information retrieval and machine learning, $\frac{u\cdot v}{\|u\|\,\|v\|}$ is called **cosine similarity**. Suppose two readers rate three genres (Sci-Fi, Math, History):

- Reader $A$ rates them $a=(1,2,1)$ (out of $5$),
- Reader $B$ rates them $b=(2,4,2)$ (out of $10$),
- Reader $C$ rates them $c=(2,0,3)$.

Even though Reader $B$'s raw numbers are twice as large as Reader $A$'s, their relative preferences are identical ($1:2:1$). Cosine similarity divides out the overall scale and reports $\cos\angle(a,b)=1$ (a perfect match in profile direction), while giving both $A$ and $B$ the exact same similarity $\frac{5}{\sqrt{78}}\approx 0.566$ with Reader $C$.

## How I would explain this in class

> First, $\|a\|=\sqrt{6}$, $\|b\|=2\sqrt{6}$, and $\|c\|=\sqrt{13}$. Computing $\frac{u\cdot v}{\|u\|\,\|v\|}$ gives $1$ for $(a,b)$ and $\frac{5}{\sqrt{78}}$ for both $(a,c)$ and $(b,c)$. Because cosine decreases as the angle increases on $[0,\pi]$, $(a,b)$ has the smallest angle ($0^\circ$), followed by $(a,c)$ and $(b,c)$ which tie at $\arccos(5/\sqrt{78})\approx 55.5^\circ$. The value for $(a,b)$ is $1$—and $(a,c)$ matches $(b,c)$—because $b=2a$ points in the exact same direction as $a$, and dividing by the norms cancels out the factor of $2$ in length.

## Related workbook topics

- [Exercise 3: Vector normalization](problem_03_solution.md)
- [Exercise 5: Angle between vectors](problem_05_solution.md)
