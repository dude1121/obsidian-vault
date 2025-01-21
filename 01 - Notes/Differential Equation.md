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
2. *Substitute* each of these equations into the given differential equation.
3. *Simplify*.
# Separation of variables
A differential equation of the first order and the first degree contains the first derivative to the first power. I.e., we could re-write it as $\frac{dy}{dx}=f(x,y)$. This is more commonly written in differential form:
$$
M(x,y)dx+N(x,y)dy=0
$$
where $M(x,y)$ and $N(x,y)$ may represent constants, functions of either $x$ or $y$, or functions of $x$ *and* $y$.  To solve,
1. Write the equation in the form above. Verify that $M(x,y)$ and $N(x,y)$ are both products of a function involving only $x$ and a function involving only $y$. If this is not the case, separation of variables cannot be used.
2. Separate the $x$ and $y$ terms by multiplying or dividing the equation by an appropriate expression.
3. Integrate each term and add the constant of integration, which becomes the arbitrary constant of the solution.

>[!question] Example
>Solve $dx-4xy^3dy=0$.
>$$
>\begin{aligned}
>dx-4xy^3dy&=0\\
>(1)dx+(-4xy^3)dy&=0\\
>\frac{dx}{x}-4y^3dy&=0\\
>\int\frac{dx}{x}-\int 4y^3dy&=0\\
>\boxed{\ln x-y^4=c}
>\end{aligned}
>$$
# Linear differential equations of the first order
This form of a differential equation is,
$$
dy+Py\ dx=Q\ dx
$$
where $P$ and $Q$ are functions of $x$. To evaluate this form, we multiply both sides by,
$$
e^{\int P\ dx}
$$
That is,
$$
e^{\int P\ dx}(dy + Py\ dx)=e^{\int P\ dx}Q\ dx
$$
This term is sometimes called $I$.
$$
I=e^{\int P\ dx}
$$
Therefore we can say that,
$$
y=\frac{1}{I}\int QI\ dx + C
$$
