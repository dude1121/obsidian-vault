---
tags:
  - mathematics
  - physics
---
The **Dirac delta function**, sometimes called the **delta distribution** or **unit impulse**, is a function that has the properties of having a value of zero everywhere except at zero where it has a value of [[Infinity|infinity]]. It is defined as,
$$
\delta(x)=\begin{cases}
0 & \text{if }x\neq 0 \\
\infty&\text{if }x=0
\end{cases}
$$
It also has the property that the total area under the function is 1. That is,
$$
\int_{-\infty}^\infty \delta(x)\ dx=1
$$
Technically speaking, the delta function is not a *function* at all, since its value is not finite at $x=0$ which is why it is sometimes called a [[Distribution|distribution]] instead.

Since $\delta(x)$ is $0$ everywhere except at $x=0$, then multiplying another function $f(x)$ by $\delta(x)$ results in,
$$
f(x)\delta(x)=f(0)\delta(x)
$$
This leads to the more interesting result that integrating any function $f(x)$ and $\delta(x)$ results in the value of that function at $x=0$.
$$
\int_{-\infty}^\infty f(x)\delta(x)\ dx=f(0)\int_{-\infty}^\infty \delta(x)\ dx=f(0)
$$
In this case, the integral need not run from negative to positive infinity, the [[Domain|domain]] must simply extend symmetrically across the delta function, i.e. evaluating the integral from $-\varepsilon$ to $\varepsilon$ would suffice.

If we shift the spike of the delta function by horizontally translating it by some value $a$ then we get,
$$
\delta(x-a)=\begin{cases}
0&\text{if }x\neq a \\
\infty&\text{if }x=a
\end{cases}
$$
and
$$
\int_{-\infty}^\infty \delta(x-a)\ dx=1
$$
Therefore if we combine this with some arbitrary function $f(x)$ we get the results,
$$
\begin{align}
f(x)\delta(x-a)=f(a)\delta(x-a)&&\int_{-\infty}^\infty f(x)\delta(x-a)\ dx=f(a)
\end{align}
$$
Although $\delta$ itself is not a legitimate function, [[Integral|integrals]] over $\delta$ are perfectly valid. It can be useful to think of this function as something that is always intended for use under an integral sign. 