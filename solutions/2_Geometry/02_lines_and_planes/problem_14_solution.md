# Exercise 14. Contrast: Intersection and Parallelism

## The question

From the point $P=(0,0,1)$, two lines are drawn with direction vectors

$$v_1=(2,1,-1),\qquad v_2=(2,1,0).$$

For each line, analyze its position relative to the plane $z=0$.

For the line that intersects the plane, find the intersection point. For the other line, explain how you can recognize parallelism without solving an equation.

## Before calculating: what idea do we need?

The plane $z=0$ is the horizontal $xy$-plane, whose normal vector points straight up along the $z$-axis:

$$n=(0,0,1).$$

For any line starting at $P=(0,0,1)$ with direction vector $v=(v_x,v_y,v_z)$, the dot product $v\cdot n=v_z$ is simply the **vertical ($z$) component** of the direction vector:
- If $v_z\neq 0$, the line changes height as $t$ varies, so it must cross the floor $z=0$ at a unique point.
- If $v_z=0$, the line has zero vertical velocity—it moves purely horizontally at constant height $z=1$ and never touches $z=0$.

## 1. First line $L_1$: intersecting the plane $z=0$

The first line has parametric equation

$$L_1:(x,y,z)=(0,0,1)+t(2,1,-1)=(2t,\,t,\,1-t),\qquad t\in\mathbb{R}.$$

Here $v_1\cdot n=(2,1,-1)\cdot(0,0,1)=-1\neq 0$, so $L_1$ intersects the plane $z=0$ at one point.

Setting $z=0$ gives

$$1-t=0\implies t=1.$$

Substituting $t=1$ into $L_1$ gives the intersection point:

$$Q=(2(1),\,1,\,1-1)=(2,1,0).$$

## 2. Second line $L_2$: recognizing parallelism without solving an equation

The second line has direction vector $v_2=(2,1,0)$ and starts at $P=(0,0,1)$:

$$L_2:(x,y,z)=(0,0,1)+t(2,1,0)=(2t,\,t,\,1),\qquad t\in\mathbb{R}.$$

How can we recognize immediately—without solving an equation—that $L_2$ is parallel to $z=0$ and has no common points with it?
1. **Orthogonality with the normal (zero $z$-component):** The third coordinate of $v_2=(2,1,0)$ is $0$, so $v_2\cdot n=(2,1,0)\cdot(0,0,1)=0$. Moving along $v_2$ never changes the $z$-coordinate.
2. **Constant non-zero height:** Because $L_2$ starts at $P=(0,0,1)$ with $z=1$ and its direction vector adds $0$ to $z$, every point on $L_2$ has $z=1\neq 0$. Thus $L_2$ stays in the horizontal plane $z=1$, strictly parallel to $z=0$ at a constant distance of $1$ unit above it.

## Quick verification

- **For $L_1$ and $Q=(2,1,0)$:**
  - Does $Q$ lie in the plane $z=0$? Its third coordinate is $z=0$. ✓
  - Does $Q$ lie on $L_1$? At $t=1$, $(0,0,1)+1(2,1,-1)=(2,1,0)=Q$. ✓
- **For $L_2$:** For any $t\in\mathbb{R}$, the third coordinate of $(2t,t,1)$ is $z=1\neq 0$, confirming $L_2\cap\{z=0\}=\varnothing$. ✓

## A concrete example

Notice the geometric relationship between the two lines:
- $L_2:(2t,t,1)$ is a horizontal ray of light shining at height $z=1$ in the direction $(2,1,0)$.
- $L_1:(2t,t,1-t)$ has the exact same horizontal motion $(2t,t)$ in the $xy$-coordinates, but tilts downward with vertical rate $-1$, hitting the floor $z=0$ at $(2,1,0)$ right underneath the point $(2,1,1)$ on $L_2$.

## How I would explain this in class

> The plane $z=0$ is the horizontal $xy$-floor, with normal vector $n=(0,0,1)$, and both lines start at $P=(0,0,1)$, one unit above the floor. For the second line, the direction vector $v_2=(2,1,0)$ has a $z$-component of $0$, so you can see at a glance without solving anything that the line moves purely horizontally at height $z=1$ and is parallel to $z=0$. For the first line, $v_1=(2,1,-1)$ drops by $1$ unit in $z$ for each unit of $t$, so starting from $z=1$ it hits the floor $z=0$ at $t=1$, landing at $(2,1,0)$.

## Related workbook topics

- [Exercise 7: A Line Relative to a Plane](problem_07_solution.md)
- [Exercise 15: Complete Classification of a Line Relative to a Plane](problem_15_solution.md)
