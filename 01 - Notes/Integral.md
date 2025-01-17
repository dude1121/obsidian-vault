---
tags:
  - mathematics
  - calculus
---
An **integral** is a continuous [[Summation|sum]]. It is more broadly defined as the "area under the curve", where the curve is the graph of some [[Function|function]]. It is also the inverse operation of [[Derivative|differentiation]] and involves finding the [[Antiderivative|antiderivative]] of a function. Integrals can either be *definite* or *indefinite*. 

Functionally the integration symbol $\int$ and the summation symbol $\sum$ are the same: they both represent a sum over some set. However, integration differs in that the sum is over a set of infinitesimals, that is a set of infinitely small elements, whereas a traditional sum requires discrete elements. 
# Indefinite integration
Integrating a function indefinitely involves finding the function's antiderivative and adding some arbitrary [[Integration Constant|constant]]. This constant, typically denoted $C$, represents some added constant to the function. This is required since for the function $f(x)=x+2$, the antiderivative could be $F(x)=\frac{1}{2}x^2+2x+4$ or $F(x)=\frac{1}{2}x^2+2x+20$ or any random constant, since the derivative of a constant is always $0$.  If we know a point on the original function, we can substitute in values for our variables and the function itself to solve for the constant's value.
## Integrals of polynomial functions
Finding the integral of a polynomial (or "algebraic") function involves "undoing" the steps taken to take the derivative of a polynomial. That is, we add $1$ to the degree of each term and divide by the new power. For example,
$$
\int x^3-2x\ dx=\int x^3\ dx - \int 2x\ dx=\frac{1}{4}x^4-x^2+C
$$
Note here that an integral can also be split up if the terms being integrated are added or subtracted. This mirrors the fact that derivatives can be split up in the same sense.  This way of evaluating integrals of polynomial functions is also referred to as the *power rule of integration*. In general,
$$
\int u^n\ du=\frac{u^{n+1}}{n+1}+C\ (n\neq -1)
$$
We can also remove constants out of integrals if they do not depend on the variable being integrated.
$$
\int c\ du=c\int du= cu + C
$$
## Integrals of transcendental functions
For transcendental functions, the rules are not so simple. These functions must be integrated with respect to their derivatives. 
### Trigonometric functions
For [[Trigonometric Functions|trigonometric functions]], the following relationships hold:
$$
\begin{aligned}
&\int \sin u\ du=-\cos u+C&&\int \cos u\ du=\sin u+C\\
&\int \tan u\ du= \ln|\sec u|+C&&\int \cot u\ du=-\ln|\csc u|+C\\
&\int \sec u\ du=\ln|\sec u+\tan u|+C&&\int \csc u\ du=-\ln|\csc u+\cot u|+C\\
\end{aligned}
$$
Based on the derivatives of other functions, the following special cases also exist:
$$
\begin{aligned}
&\int \sec^2u\ du=\tan u+C&&\int \sec u \tan u\ du=\sec u+C\\
&\int \csc^2u\ du=-\cot u+C&&\int \csc u \cot u\ du=-\csc u+C
\end{aligned}
$$
### Inverse trigonometric functions
For the [[Inverse Trigonometric Functions|inverse trigonometric functions]], the following relationships hold:
$$
\begin{aligned}
&\int \frac{du}{\sqrt{ a^2-u^2 }}=\arcsin \left( \frac{u}{a} \right)+C&&\int \frac{du}{u^2+a^2}=\frac{1}{a}\arctan \left( \frac{u}{a} \right)\\
&\int \frac{du}{u\sqrt{ u^2-a^2 }}=\frac{1}{a}\mathrm{arcsec}\left( \frac{u}{a} \right)
\end{aligned}
$$
### Exponential functions
For [[Exponential Function|exponential functions]], the following relationships hold:
$$
\begin{aligned}
&\int e^u\ du=e^u+C&&\int a^u\ du=\frac{a^u}{\ln a}+C;\  a>0,\ a\neq 1
\end{aligned}
$$

### Logarithmic functions and the basic logarithmic form
For the [[Natural Log|natural logarithmic function]], the following relationship holds:
$$
\int \ln u\ du=u\ln (u)-u+C
$$
In the power rule of integration definition, we noted it does not hold if $n=-1$. This is because this unique case is the basic logarithmic form and is evaluated thusly,
$$
\int u^{-1}\ du=\int \frac{du}{u}=\ln|u|+C
$$
# Definite integration
Definite integrals have upper and lower bounds between which the function is integrated. These are called the "limits of integration". Definite integrals are defined as part of the [[Fundamental Theorem of Calculus|fundamental theorem of calculus]] which relates differentiation and integration together. A definite integral is noted with the limits on the top and bottom of the integral sign. The following integral,
$$
\int_{3}^5f(x)\ dx
$$
is read as "the integral of $f(x)$ evaluated from $3$ to $5$." This is sometimes denoted as,
$$
\int_{3}^5 f(x)\ dx= F(x)\biggr|_{3}^5
$$
and it is evaluated by substituting the higher limit of integration into the antiderivative of the integrand and subtracting from it the antiderivative evaluated at the lower limit. That is,
$$
F(x)\biggr|_{3}^5=F(5)-F(3)
$$
# Area under a curve
Integration has another property in that when evaluated as a definite integral it represents the *signed* area under the function between two points. 

# $u$-Substitution
In the examples above, we have used $u$ for the variable instead of the typical $x$. This is due to a powerful technique in evaluating integrals: $u$-substitution. This involves substituting some part of the integrand with some arbitrary variable ($u$ is often used) which turns the integral into something much easier to evaluate. 
>[!question] Example
>Evaluate the following integral.
>$$
>\int(x^3+5)^6\cdot 3x^2\ dx
>$$
>**Solution:**
>$$
>\begin{aligned}
>&\int(x^3+5)^6\cdot 3x^2\ dx
>&\text{Let }u=x^3+5\\
>&=\int u^6\ du&du=3x^2\ dx\\
>&=\frac{1}{7}u^7+C\\
>&\boxed{=\frac{1}{7}(x^3+5)^7+C}
>\end{aligned}
>$$

Using $u$-substitution allowed us to not have to expand $(x^3+5)^6$ and instead evaluate the integral rather simply. To perform $u$-substitution the term(s) to be represented by $u$ need to be determined. These terms must be selected such that there are either no "leftovers" in the differential form of $du$ or the leftovers are also present in our integrand and can therefore be eliminated (in our example the "leftovers" were $3x^2$). In the case that our leftovers are constants, these constants can be moved outside the integration.
>[!question] Example 2
>Evaluate the following definite integral.
>$$
>\int_{1}^3 \sqrt{ 1+0.5t }\ dt
>$$
>**Solution:**
>$$
>\begin{aligned}
>&\int_{1}^3\sqrt{ 1+0.5t }\ dt&\text{Let }u=1+0.5t\\
>&=\int_{1}^3(1+0.5t)^{\frac{1}{2}}\ dt&du=0.5t\\
>&=2\int_{1}^3 u^{\frac{1}{2}}\ du&2du=dt\\
>&=2\cdot \frac{2}{3}u^{\frac{3}{2}}\biggr|_{1}^3\\
>&=\frac{4}{3}(1+0.5t)^{\frac{3}{2}}\biggr|_{1}^3\\
>&=\frac{4}{3}(2.5^{\frac{3}{2}}-1.5^{\frac{3}{2}})\\
>&\boxed{\approx 2.821}
>\end{aligned}
>$$

$u$-substitution does not always work, however. For example, if the "leftovers" of the derivation of any of the terms in the integrand do not match up, $u$-substitution can not be used and other methods must be used.