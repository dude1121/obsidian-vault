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
# Second-Order linear differential equations
A second-order linear differential equation has the form:
$$
P(x)\ \frac{d^2y}{dx^2}+Q(x)\ \frac{dy}{dx} + R(x)y=G(x)
$$
where $P$, $Q$, $R$, and $G$ are continuous functions. If $G(x)=0$, then we say the equation is *homogenous*. Else, it is *non-homogenous*.
## Homogenous
> [!quote] Theorem
> If $y_{1}(x)$ and $y_{2}(x)$ are both solutions of the homogenous equation and $c_{1}$ and $c_{2}$ are any constants, then the function
> $$
> y(x)=c_{1}y_{1}(x)+c_{2}y_{2}(x)
> $$
> is also a solution of the same equation.

>[!quote] Theorem
>If $y_{1}$ and $y_{2}$ are linearly independent solutions of the equation, and $P(x)$ is never $0$, then the general solution is given by,
>$$
>y(x)=c_{1}y_{1}(x)+c_{2}y_{2}(x)
>$$
>where $c_{1}$ and $c_{2}$ are arbitrary constants.

The above theorems allow us to solve homogenous differential equations because we can make some assumptions. The second theorem is especially useful because it says that if we know *two* particular linearly independent solutions, then we know *every* solution. This is not always easy but it is always possible to do if the functions $P$, $Q$, and $R$ are constants. That is, if the equation is of the form,
$$
ay\ ''+by\ '+cy=0
$$
where $a$, $b$, and $c$ are constants and $a\neq 0$. From this we know we are looking for a function $y$ such that a constant times its second derivative $y\ ''$ plus another constant times $y\ '$ plus a third constant times $y$ is equal to $0$. We know that the [[Exponential Function|exponential function]] $y=e^{rx}$ (where $r$ is some constant) has the property that its derivative is a multiple of itself, $y\ '=re^{rx}$. Its second derivative follows the pattern, $y\ ''=r^2e^{rx}$. We can substitute this in to the above equation,
$$
ar^2e^{rx}+bre^{rx}+ce^{rx}=0
$$
or
$$
(ar^2+br+c)e^{rx}=0
$$
But $e^{rx}$ is never $0$, meaning that $y=e^{rx}$ is a solution of the equation if $r$ is a root of the equation,
$$
ar^2+br+c=0
$$
This equation is called the *auxiliary equation* or *characteristic equation* of the differential equation $ay\ ''+by\ '+cy=0$. This can be solved using the quadratic formula or factoring to find our $r$ values. 
$$
\begin{align}
r_{1}=\frac{-b+\sqrt{ b^2-4ac }}{2a}&&r_{2}=\frac{-b-\sqrt{ b^2-4ac }}{2a}
\end{align}
$$
Evaluating the discriminant leads us to three distinct cases:
### $b^2-4ac>0$
In this case, there are two [[Real Numbers|real]] [[Root (Mathematics)|roots]], meaning the solution to the differential equation is
$$
y=c_{1}e^{r_{1}x}+c_{2}e^{r_{2}x}
$$
### $b^2-4ac=0$
If there is only one root, the solution to the differential equation is of the form,
$$
y=c_{1}e^{rx}+c_{2}xe^{rx}
$$
In this case, the root $r$ is equal to
$$
r=-\frac{b}{2a}
$$
### $b^2-4ac<0$
In this case the roots $r_{1}$ and $r_{2}$ are not real but instead [[Complex Numbers|complex]]. We could write the roots as,
$$
\begin{align}
r_{1}=\alpha+i\beta&&r_{2}=\alpha-i\beta
\end{align}
$$
where $\alpha$ and $\beta$ are real numbers. They can be defined as
$$
\begin{align}
\alpha=-\frac{b}{2a}&&\beta=\frac{\sqrt{ 4ac-b^2 }}{2a}
\end{align}
$$
Using [[Euler's Formula|Euler's formula]],
$$
e^{i\theta}=\cos \theta+i\ \sin \theta
$$
We can therefore write the solution of the differential equation as,
$$
\begin{align}
y&=c_{1}e^{(\alpha+i\beta)x}+c_{2}e^{(\alpha-i\beta)x}\\ \\
&=c_{1}e^{\alpha x}(\cos \beta x+i\sin \beta x)+c_{2}e^{\alpha x}(\cos \beta x-\sin \beta x)\\ \\
&=e^{\alpha x}\left[(c_{1}+c_{2})\cos \beta x+i(c_{1}-c_{2})\sin \beta x\right] \\
&\boxed{=e^{\alpha x}(c_{1}\cos \beta x+c_{2}\sin \beta x)}
\end{align}
$$
## Non-homogenous
A non-homogenous differential equation is of the form,
$$
a\frac{d^2y}{dx^2} + P(x)\frac{dy}{dx} + Q(x)y=f(x)
$$
where $P(x)$, $Q(x)$, and $f(x)$ are arbitrary functions of $x$.

To solve a non-homogenous differential equation, we first recognize that the general solution to a non-homogenous equation is of the form,
$$
y=y_{c}+y_{p}
$$
where $y_{c}$ is the *complementary solution* and $y_{p}$ is the *particular solution*. We find the complementary solution by solving the left-hand side as a homogenous equation. We then use the right-hand side $f(x)$ to find the particular solution.
### Particular solution
