---
tags:
  - mathematics
---
The **Heaviside function** (or sometimes, the *Heaviside step function*) is a function usually denoted by $H$ or $\theta$ (although sometimes also $u$, $\mathbf{1}$, or $\mathbb{1}$) that is named after [[Oliver Heaviside]]. It is defined as,
$$
H(t)=\begin{cases}
1 & t\geq 0 \\
0 & t< 0
\end{cases}
$$
The Heaviside function is a [[Step Function|step function]], and in some ways is *the* step function, as all other step functions can be defined in terms of this function. It was originally developed to solve [[Differential Equation|differential equations]] where it represented a signal (like a [[Current|current]] or [[Voltage|voltage]]) that switched on at $t=0$ and stayed turned on.
# Value at $t=0$
Although the above definition defines the function to be $1$ at $t=0$, there is some debate as to whether the function is actually $1$, $0$, $\frac{1}{2}$, or if it is even defined at all. Often times, the value of $H(0)$ is whichever one is convenient for the task being performed.