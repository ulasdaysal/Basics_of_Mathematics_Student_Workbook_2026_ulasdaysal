# Exercise 8. Number of Requests Handled by a Server

## The question

The rate at which requests arrive at a server during the first $5$ minutes is described by the function

$$r(t)=100+20t\quad [\text{requests/min}],\qquad 0\le t\le 5.$$

1. Compute the total number of requests that arrived during this time.
2. Compute the average rate of incoming requests over this interval.
3. Compare the average rate with the values $r(0)$ and $r(5)$.

## Before calculating: what idea do we need?

When we are given a time-varying **rate of flow** $r(t)$ (in requests per minute), multiplying rate by a tiny time increment $dt$ gives the number of requests $dQ=r(t)\,dt$ arriving during that instant. Integrating $r(t)$ over $[0,5]$ accumulates all incoming requests, and dividing that total by the $5$-minute duration yields the average arrival rate.

## 1. Total number of requests in the first 5 minutes

The total number of requests $Q$ arriving on $[0,5]$ is the definite integral of the arrival rate $r(t)$:

$$Q = \int_0^5 r(t)\,dt = \int_0^5 (100+20t)\,dt.$$

Computing the antiderivative and evaluating at the limits:

$$Q = \left[100t+10t^2\right]_0^5 = \bigl(100(5)+10(5)^2\bigr) - 0 = 500 + 250 = 750\text{ requests}.$$

## 2. Average rate of incoming requests over $[0,5]$

By the integral average value formula on $[0,5]$, the average arrival rate $r_{\text{avg}}$ is the total number of requests divided by the elapsed time:

$$r_{\text{avg}} = \frac{1}{5-0}\int_0^5 r(t)\,dt = \frac{750}{5} = 150\text{ requests/min}.$$

## 3. Comparing $r_{\text{avg}}$ with $r(0)$ and $r(5)$

Let us evaluate the arrival rate at the endpoints of the interval:

$$r(0) = 100+20(0) = 100\text{ requests/min},$$

$$r(5) = 100+20(5) = 200\text{ requests/min}.$$

Comparing the three quantities:

$$r_{\text{avg}} = 150 = \frac{100+200}{2} = \frac{r(0)+r(5)}{2},$$

and $r_{\text{avg}}$ is attained exactly at the midpoint $t=2.5\text{ min}$: $r(2.5)=100+20(2.5)=150\text{ requests/min}$.

## 4. Why the average equals the arithmetic mean of the endpoints here

Because $r(t)=100+20t$ is a **linear function**, the rate increases at a constant pace ($20\text{ requests/min}^2$). Every time interval $[0, 2.5]$ with rate below $150$ is symmetrically balanced by a corresponding time interval $[2.5, 5]$ with rate above $150$. For any linear function on $[a,b]$, the integral average always coincides with the midpoint value $r\bigl(\frac{a+b}{2}\bigr)$ and the endpoint average $\frac{r(a)+r(b)}{2}$.

## Quick verification

We can verify the integral geometrically using the area of a trapezoid under $r(t)$ on $[0,5]$:

- Base width: $\Delta t = 5\text{ min}$.
- Parallel heights: $r(0)=100$ and $r(5)=200$.
- Area: $\frac{100+200}{2}\cdot 5 = 150\cdot 5 = 750\text{ requests}$. ✓

If a second server received a constant stream of $150\text{ requests/min}$ for $5$ minutes, it would handle $150\times 5 = 750\text{ requests}$—the exact same total load. ✓

## A concrete example

In capacity planning for a web service, engineers need both numbers:
- The **average rate** $r_{\text{avg}}=150\text{ req/min}$ tells us the total logging storage or billing volume over the $5$-minute window ($750$ requests).
- The **peak rate** $r(5)=200\text{ req/min}$ tells us the minimum throughput capacity the server CPU must have at $t=5$ so that requests do not queue up or time out.

## How I would explain this in class

> Integrating the arrival rate $r(t)=100+20t$ from $t=0$ to $t=5$ sums up the requests over time: $\int_0^5 (100+20t)\,dt = [100t+10t^2]_0^5 = 750$ requests. Dividing $750$ requests by $5$ minutes gives an average rate of $150\text{ requests/min}$. Since $r(0)=100$ and $r(5)=200$, the average rate $150$ is the exact halfway point $\frac{r(0)+r(5)}{2}$ because $r(t)$ is linear.

## Related workbook topics

- [Exercise 5: Distance from Velocity](problem_05_solution.md)
- [Exercise 6: Average Value of a Function](problem_06_solution.md)
