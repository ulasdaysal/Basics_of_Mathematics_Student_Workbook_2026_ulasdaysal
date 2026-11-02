# Exercise 1. Line Through Two Points

## The question

Find the equation of the line through $A=(1,2)$ and $B=(4,-1)$ in parametric and general form. Identify a direction vector and an example of a normal vector. Check that both points satisfy the equation you obtain.

## Before calculating: what idea do we need?

A line in the plane can be described in two complementary ways:

- **Parametric form** starts at one known point $A$ and moves along a **direction vector** $v=\overrightarrow{AB}=B-A$:
  $$(x,y)=A+tv,\qquad t\in\mathbb{R}.$$
- **General (implicit) form** describes the line as the set of points whose displacement from $A$ is perpendicular to a **normal vector** $n=(a,b)$:
  $$ax+by+c=0.$$

If $v=(v_x,v_y)$ is a direction vector in $\mathbb{R}^2$, rotating it by $90^\circ$ gives a normal vector $n=(-v_y,v_x)$ (or any non-zero multiple of it), because their dot product is zero.

## 1. Direction vector and parametric form

The vector from $A=(1,2)$ to $B=(4,-1)$ is

$$v=\overrightarrow{AB}=B-A=(4-1,-1-2)=(3,-3).$$

Any non-zero scalar multiple of $v$ defines the same direction. Dividing by $3$ gives a simpler direction vector:

$$v_0=(1,-1).$$

Using $A=(1,2)$ as the base point and $v=(3,-3)$, the parametric form is

$$(x,y)=(1,2)+t(3,-3),\qquad t\in\mathbb{R},$$

or in coordinates:

$$\begin{cases}x=1+3t,\\y=2-3t,\end{cases}\qquad t\in\mathbb{R}.$$

(With the simplified direction vector $v_0=(1,-1)$, we can equally write $(x,y)=(1,2)+s(1,-1)$.)

## 2. Normal vector and general form

We need a vector $n=(a,b)$ perpendicular to $v_0=(1,-1)$, so $n\cdot v_0=0$. Choosing

$$n=(1,1)$$

gives $n\cdot v_0=1\cdot1+1\cdot(-1)=0$.

The general equation of a line with normal $n=(1,1)$ passing through $A=(1,2)$ is

$$1(x-1)+1(y-2)=0\implies x+y-3=0\quad(\text{or }x+y=3).$$

 We can also get this directly from the parametric equations by eliminating $t$: adding $x=1+3t$ and $y=2-3t$ cancels $3t$ and gives $x+y=3$.

## 3. Summary of vectors and equations

- **Direction vector:** $v=(3,-3)$, or simplified $v_0=(1,-1)$.
- **Normal vector:** $n=(1,1)$ (or any non-zero multiple such as $(3,3)$).
- **Parametric equation:** $(x,y)=(1,2)+t(3,-3)$ (or $(1,2)+s(1,-1)$).
- **General equation:** $x+y-3=0$.

## Quick verification

Let us check both points in both equations:

- In the general equation $x+y-3=0$:
  - For $A=(1,2)$: $1+2-3=0$. ✓
  - For $B=(4,-1)$: $4+(-1)-3=0$. ✓
- In the parametric equation $(x,y)=(1,2)+t(3,-3)$:
  - $t=0$ gives $(1,2)=A$. ✓
  - $t=1$ gives $(1+3,2-3)=(4,-1)=B$. ✓
- Orthogonality check between direction and normal:
  $$v\cdot n=(3,-3)\cdot(1,1)=3-3=0.\text{ ✓}$$

## A concrete example

What point sits halfway between $A$ and $B$? In the parametric equation $(x,y)=(1,2)+t(3,-3)$, the parameter $t$ measures progress from $A$ ($t=0$) to $B$ ($t=1$). Setting $t=\frac{1}{2}$ gives the midpoint

$$M=\left(1+\frac{3}{2},\,2-\frac{3}{2}\right)=\left(\frac{5}{2},\,\frac{1}{2}\right).$$

Checking $M$ in the general equation: $\frac{5}{2}+\frac{1}{2}-3=3-3=0$, confirming that $M$ lies on the line.

## How I would explain this in class

> To write the line through $A=(1,2)$ and $B=(4,-1)$, I first subtract the points to get the direction vector $v=B-A=(3,-3)$, which simplifies to $(1,-1)$. Starting at $A$ and stepping along $v$ gives the parametric form $(x,y)=(1,2)+t(3,-3)$. To switch to general form, I swap the components of $(1,-1)$ and change one sign to get a perpendicular normal vector $n=(1,1)$. That immediately gives the coefficients of $x$ and $y$ in $x+y+c=0$, and plugging in $(1,2)$ tells me $x+y-3=0$.

## Related workbook topics

- [Exercise 2: A Line in Space](problem_02_solution.md)
- [Exercise 3: Plane Through a Point with a Given Normal Vector](problem_03_solution.md)
