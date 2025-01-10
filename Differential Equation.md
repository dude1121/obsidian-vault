---
tags:
  - mathematics
  - calculus
---
A **differential equation** is an [[Equation|equation]] that contains [[Derivative|derivatives]] or [[Differential|differentials]]. Differential equations can either be *ordinary*, meaning it makes use of only ordinary or "true" derivatives, or they can be *partial*, meaning it makes use of [[Partial Derivative|partial derivatives]]. 
# Order and degree
The *order* of a differential equation refers to the highest derivative in the equation. For example,
$$
\frac{dy}{dx}+x=y
$$
is a *first-order* differential equation, whereas,
$$
1+\frac{d^2y}{dx^2}y=x
$$
is a *second-order* differential equation. The *degree* of a differential equation is given by the highest power of that derivative. E.g.,
$$
\left[\frac{dy}{dx}\right]^3+y=x
$$
is a first-order, third-degree differential equation.
# Solutions
A *solution* to a differential equation is a relation between the variables that satisfies the differential equation. When this relation is substituted into the differential equation, an *algebraic identity* results.

To find the solution of an $n$-th order differential equation, we would expect to [[Integral|integrate]] $n$ times. With each integration step, an arbitrary integration constant would be produced. These are known as *general solutions*. If a specific value is given to at least one of the arbitrary constants, this is known as a *particular solution*.
## Proving a function is a solution to a differential equation
If given a function to "show" that it is a solution to a differential equation, follow the following steps:
1. *Identify all the derivatives* of the given function to the order of the differential equation.
2. 