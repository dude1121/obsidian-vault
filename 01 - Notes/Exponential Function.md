---
tags:
  - mathematics
  - functions
---
An **exponential function** is a [[Function|function]] that involves some input $x$ being raised to a constant base $b$. This is known as [[Exponentiation|exponentiation]]. The exponential function is generally taken to be a [[Real Numbers|real]] function although it can be extended to the [[Complex Numbers|complex numbers]]. 

The function $f(x)=b^x$ is defined for any $b > 0, b\neq 1$. If the base of the function is $e$, the function can be written as $\exp(x)$, where $\exp(1)=e$ (see [[Euler's Number|Euler's number]]). Since all bases greater than 0 can be expressed as
$$
b^x=e^{x\ln b}
$$
this means that all exponential functions can be written in terms of the natural exponential function.
# Formal Definition

The natural exponential function can be defined in terms of both its [[Power Series|power series]] and its [[Limit|limit]] definition. With either definition, if $x=1$ is substituted in, the value of the base $e$ must then be equivalent to the modified series or limit.

## Power Series
$$
\exp(x):=\sum_{k=0}^{\infty}\frac{x^k}{k!}=1+x+\frac{x^2}{2!}+\frac{x^3}{3!}+\dots
$$
## Limit Definition
$$
\exp(x)=\lim_{ n \to \infty }\left(1+\frac{x}{n}\right)^n 
$$
