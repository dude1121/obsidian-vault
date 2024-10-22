---
tags:
  - mathematics
  - calculus
---
The **derivative** is the *instantaneous rate of change* of a given [[Function|function]]. The process of finding the derivative of a function is called *differentiation*. 

If the function is single-variable, the derivative corresponds to the [[Slope|slope]] of the [[Tangent Line|tangent line]] to the graph of the function at that point.

The derivative can be indicated in multiple ways, the most common being either [[Gottfried Wilhelm Leibniz|Leibniz]] notation or prime notation. In Leibniz notation, the derivative is indicated as a ratio of two [[Differential|differentials]], whereas in prime notation it is indicated by a prime mark.
$$
\frac{dy}{dx}=f'(x)
$$
Additional derivatives are denoted in Leibniz notation by adding superscripts to the $\frac{d}{dx}$ operator and by adding prime marks in prime notation.
$$
\frac{d^2y}{dx^2}=f''(x)
$$
In physics, [[Isaac Newton|Newton]] notation (also known as "dot notation") is used to indicate the time derivative of some variable. For example, [[Acceleration|acceleration]] $\mathbf{a}$ is the second derivative of [[Position|position]] $\mathbf{x}$. This might be noted as,
$$
\mathbf{a}=\ddot{\mathbf{x}}
$$
For a function to be differentiable at some arbitrary point $a$, the function must also be [[Continuous Function|continuous]] at $a$. Therefore, if a function is differentiable everywhere, it is also continuous everywhere, however the inverse is not necessarily true.
# Limit Definition

The [[Limit|limit]] definition of a derivative is often called the "derivative-by-definition". It states,
$$
\frac{d}{dx}f(x)= \lim_{ h \to 0 }\frac{f(x+h)-f(x)}{h} 
$$
If this limit exists, then the function is differentiable, and the value of the limit is the function's derivative.

# Rules for Differentiation

Power Rule:
$$
\frac{d}{dx}x^{n}=nx^{n-1}
$$
Constant Rule (assuming $A$ is some [[Constant|constant]] that does not vary with time):
$$
\frac{d}{dx}A=0
$$
Sum and Difference Rule:
$$
\frac{d}{dx}(af\pm bg)=af'\pm bg'
$$
Product Rule:
$$
\frac{d}{dx}(fg)=f'g+fg'
$$
Quotient Rule:
$$
\frac{d}{dx}\left(\frac{f}{g}\right)=\frac{f'g-fg'}{g^2},\ \ g\neq 0
$$
Chain Rule:
$$
\frac{d}{dx}[f(g(x))]=f'(g(x))\cdot g'(x)
$$
[[Exponential Function]]:
$$
\frac{d}{dx}e^u=e^u\cdot\frac{du}{dx}
$$
$$
\frac{d}{dx}b^u=b^u\ln b\cdot \frac{du}{dx}
$$
[[Logarithmic Functions]]:
$$
\begin{aligned}
\frac{d}{dx}\log_{b}u&=\frac{1}{u\ln b}\cdot\frac{du}{dx}\\

\end{aligned}
$$
$$
\frac{d}{dx}\ln u=\frac{1}{u}\cdot\frac{du}{dx}
$$
[[Trigonometric Functions]]:
$$
\frac{d}{dx}\sin u=\cos u\cdot\frac{du}{dx}
$$
$$
\frac{d}{dx}\cos u=-\sin u\cdot\frac{du}{dx}
$$
$$
\frac{d}{dx}\tan u=\sec^2 u\cdot\frac{du}{dx}
$$
$$
\frac{d}{dx}\cot u=-\csc^2 u\cdot\frac{du}{dx}
$$
$$
\frac{d}{dx}\sec u=\sec u \tan u\cdot\frac{du}{dx}
$$
$$
\frac{d}{dx}\csc u=-\csc u \cot u\cdot\frac{du}{dx}
$$
[[Inverse Trigonometric Functions]]:
$$
\frac{d}{dx}\arcsin u=\frac{1}{\sqrt{ 1-u^2 }}\cdot\frac{du}{dx}
$$
$$
\frac{d}{dx}\arccos u=-\frac{1}{\sqrt{ 1-u^2 }}\cdot\frac{du}{dx}
$$
$$
\frac{d}{dx}\arctan u=\frac{1}{1+u^2}\cdot\frac{du}{dx}
$$
$$
\frac{d}{dx}\mathrm{arccot}\ u=-\frac{1}{1+u^2}\cdot\frac{du}{dx}
$$
$$
\frac{d}{dx}\mathrm{arcsec}\ u=\frac{1}{u\sqrt{ u^2-1 }}\cdot\frac{du}{dx}
$$
$$
\frac{d}{dx}\mathrm{arccsc}\ u=-\frac{1}{u\sqrt{ u^2-1 }}\cdot\frac{du}{dx}
$$


