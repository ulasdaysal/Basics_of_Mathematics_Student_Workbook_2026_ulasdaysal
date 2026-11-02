# Exercise 11. Decomposition into Parallel and Perpendicular Components

## The question

Decompose $u=(3,4)$ into components parallel and perpendicular to $v=(1,2)$. Check

$$u=u_{\parallel}+u_{\perp},\qquad u_{\perp}\cdot v=0.$$

Explain why these are two independent checks of correctness.

## Before calculating: what idea do we need?

Every vector $u$ can be uniquely decomposed with respect to a nonzero reference direction $v$ as

$$u = u_{\parallel} + u_{\perp},$$

where:

- $u_{\parallel} = \operatorname{proj}_v u = \dfrac{u\cdot v}{v\cdot v}\,v$ is a scalar multiple of $v$ (**parallel component**),
- $u_{\perp} = u - u_{\parallel}$ is orthogonal to $v$, meaning $u_{\perp}\cdot v = 0$ (**perpendicular component**).

Geometrically, we are setting up a local right-angled coordinate system aligned with $v$ and splitting $u$ into a leg along $v$ and a leg perpendicular to $v$.

## 1. Finding the parallel component $u_{\parallel}$

For $u=(3,4)$ and $v=(1,2)$, we compute the dot products:

$$u\cdot v = 3\cdot 1 + 4\cdot 2 = 3 + 8 = 11,$$

$$v\cdot v = 1^2 + 2^2 = 1 + 4 = 5.$$

Therefore, the parallel component is

$$u_{\parallel} = \operatorname{proj}_v u = \frac{u\cdot v}{v\cdot v}\,v = \frac{11}{5}(1,2) = \left(\frac{11}{5},\, \frac{22}{5}\right).$$

## 2. Finding the perpendicular component $u_{\perp}$

We subtract $u_{\parallel}$ from $u=(3,4)=\left(\frac{15}{5},\frac{20}{5}\right)$:

$$u_{\perp} = u - u_{\parallel} = \left(\frac{15}{5},\, \frac{20}{5}\right) - \left(\frac{11}{5},\, \frac{22}{5}\right) = \left(\frac{4}{5},\, -\frac{2}{5}\right).$$

## 3. Checking the two required conditions

1. **Sum check ($u = u_{\parallel} + u_{\perp}$):**
   $$u_{\parallel} + u_{\perp} = \left(\frac{11}{5},\, \frac{22}{5}\right) + \left(\frac{4}{5},\, -\frac{2}{5}\right) = \left(\frac{11+4}{5},\, \frac{22-2}{5}\right) = \left(\frac{15}{5},\, \frac{20}{5}\right) = (3,4) = u.$$
2. **Orthogonality check ($u_{\perp}\cdot v = 0$):**
   $$u_{\perp}\cdot v = \left(\frac{4}{5},\, -\frac{2}{5}\right)\cdot(1,2) = \frac{4}{5}\cdot 1 + \left(-\frac{2}{5}\right)\cdot 2 = \frac{4 - 4}{5} = 0.$$

## 4. Why these are two independent checks of correctness

Neither condition alone guarantees that $(u_{\parallel}, u_{\perp})$ is the true orthogonal decomposition of $u$ along $v$:

- **Why $u = u_{\parallel} + u_{\perp}$ alone is not enough:** If we picked *any* wrong scalar multiple of $v$—say $\tilde{u}_{\parallel} = 2v = (2,4)$—and defined $\tilde{u}_{\perp} = u - \tilde{u}_{\parallel} = (1,0)$, their sum $\tilde{u}_{\parallel} + \tilde{u}_{\perp}$ would still equal $(3,4)=u$ automatically! However, $\tilde{u}_{\perp}\cdot v = (1,0)\cdot(1,2) = 1 \neq 0$, so the second check catches the wrong projection factor.
- **Why $u_{\perp}\cdot v = 0$ alone is not enough:** Any multiple of $(2,-1)$, such as $(2,-1)$ or $(0,0)$, satisfies $w\cdot v = 0$, even if it has nothing to do with $u=(3,4)$. The sum check $u_{\parallel}+u_{\perp}=u$ ensures that our two components actually reconstruct the given vector $u$ without arithmetic mistakes during subtraction.

Together, (1) $u_{\parallel}$ being a multiple of $v$, (2) $u_{\perp}\cdot v = 0$, and (3) $u_{\parallel}+u_{\perp}=u$ uniquely lock in the decomposition.

## Quick verification

Let us also check the **Pythagorean theorem** $\|u_{\parallel}\|^2 + \|u_{\perp}\|^2 = \|u\|^2$:

$$\|u_{\parallel}\|^2 = \left(\frac{11}{5}\right)^2 + \left(\frac{22}{5}\right)^2 = \frac{121 + 484}{25} = \frac{605}{25} = \frac{121}{5},$$

$$\|u_{\perp}\|^2 = \left(\frac{4}{5}\right)^2 + \left(-\frac{2}{5}\right)^2 = \frac{16 + 4}{25} = \frac{20}{25} = \frac{4}{5}.$$

Adding them:

$$\|u_{\parallel}\|^2 + \|u_{\perp}\|^2 = \frac{121}{5} + \frac{4}{5} = \frac{125}{5} = 25 = 3^2 + 4^2 = \|u\|^2.\quad \checkmark$$

## A concrete example

Notice that $v=(1,2)$ has perpendicular direction $v_{\perp}=(2,-1)$ (obtained by swapping the two coordinates and negating one, since $(1,2)\cdot(2,-1)=0$). Writing $u=(3,4)$ in the orthogonal basis $\{v, v_{\perp}\}$ gives

$$(3,4) = \frac{11}{5}(1,2) + \frac{2}{5}(2,-1) = \left(\frac{11}{5},\, \frac{22}{5}\right) + \left(\frac{4}{5},\, -\frac{2}{5}\right),$$

which immediately produces $u_{\parallel}$ and $u_{\perp}$ at the same time!

## How I would explain this in class

> First, we project $u=(3,4)$ onto $v=(1,2)$: $u_{\parallel} = \frac{u\cdot v}{v\cdot v}v = \frac{11}{5}(1,2) = (\frac{11}{5},\frac{22}{5})$. Subtracting this from $u$ gives $u_{\perp} = (3,4)-(\frac{11}{5},\frac{22}{5}) = (\frac45,-\frac25)$. The two checks test two completely different things: $u_{\parallel}+u_{\perp}=u$ verifies that the pieces add back up to $u$, while $u_{\perp}\cdot v=0$ verifies that we chose the exact multiple of $v$ that makes the remainder perpendicular to $v$.

## Related workbook topics

- [Exercise 6: Projection and perpendicular component](problem_06_solution.md)
- [Exercise 14: Closest point on a line](problem_14_solution.md)
