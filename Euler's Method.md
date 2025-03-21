---
tags:
  - mathematics
  - calculus
---
In calculus, **Euler's method** (named after [[Leonhard Euler]]) is a method of solving [[Ordinary Differential Equation|ODEs]] that have a given initial value. It is the simplest [[Runge-Kutta Method|Runge-Kutta method]].
# Example
Say we have an initial value problem
$$
\begin{align}
y'=y&&y(0)=1
\end{align}
$$
We want to use Euler's method to approximate $y(4)$.

The Euler method is,
$$
y_{n+1}=y_{n}+hf(x_{n},y_{n})
$$
where $h$ is the *step size* we are using. 