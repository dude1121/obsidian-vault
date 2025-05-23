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
where $h$ is the *step size* we are using. We first have to compute the value of $f(x_{0},y_{0})$. As stated at the beginning, $f(x,y)=y$. Therefore, $f(0,1)=1$. Meaning that we can substitute in values to find our next $y$ point.
$$
\begin{align}
y_{1}&=y_{0}+hf(x_{0},y_{0}) \\
&=1+(1)(1) \\
&=2
\end{align}
$$
We can keep going,
$$
\begin{align}
y_{2}&=y_{1}+hf(x_{1},y_{1})=2+(1)(2)=4 \\
y_{3}&=y_{2}+hf(x_{2},y_{2})=4+(1)(4)=8 \\
\vdots
\end{align}
$$
