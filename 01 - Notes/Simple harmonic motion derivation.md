---
tags:
  - physics
  - oscillatory-motion
  - calculus
  - mathematics
---
We are given the following relation.
$$
\frac{d^2x}{dt^2}=-\frac{k}{m}x
$$
Let $\omega^2=\frac{k}{m}$. Rewriting the initial equation,
$$
\frac{d^x}{dt^2}=-\omega^2x
$$
Move the term on the right side to the left side of the equation.
$$
\frac{d^2x}{dt^2}+\omega^2x=0
$$
This is in the form of a [[Differential Equation#Second-Order linear differential equations|second-order linear differential equation]]. As such, we can write this as,
$$
r^2+\omega^2=0
$$
Solving for $r$ we first evaluate the discriminant.
$$
\begin{align}
&b^2-4ac \\
=\ &(0)^2-4(1)(\omega^2) \\
=\ &-4\omega^2 \\
<\ &0\\
\end{align}
$$
Since the discriminant is $<0$, the roots are complex.
$$
\begin{align}
\alpha&=\frac{b}{2a}&\beta&=\frac{\sqrt{ 4ac-b^2 }}{2a} \\
&=\frac{0}{2(1)}&&=\frac{\sqrt{ 4(1)(\omega^2)-(0)^2 }}{2(1)} \\
&=0&&=\frac{\sqrt{ 4\omega^2 }}{2} \\
&&&=\omega \\
\therefore\  r&=\pm\ i\omega
\end{align}
$$
Using these roots to solve for $x$,
$$
\begin{align}
x(t)&=c_{1}e^{i\omega t}+c_{2}e^{-i\omega t} \\
\end{align}
$$
Using [[Euler's Formula|Euler's formula]] $e^{ix}=\cos x+i\sin x$,
$$
x(t)=c_{1}(\cos \omega t+i\sin \omega t)+c_{2}(\cos(-\omega t)+i \sin(-\omega t))
$$
Since $\cos x$ is an even function and $\sin x$ is an odd function,
$$
x(t)=c_{1}\cos \omega t+c_{1}i\sin \omega t+c_{2}\cos \omega t-c_{2}i\sin \omega t
$$
Factoring,
$$
x(t)=(c_{1}+c_{2})\cos \omega t + i(c_{1}-c_{2})\sin \omega t
$$
Let $C=c_{1}+c_{2}$ and $D=c_{1}-c_{2}$, where $c_{1}$ and $c_{2}$ are [[Complex Numbers#Conjugate|complex conjugates]] of one another (since in a real oscillatory situation the constants must necessarily be real).
$$
x(t)=C\cos \omega t+D\sin \omega t
$$
This is the general [[Real Numbers|real]] solution for this problem, however oscillatory motion is often written in [[Amplitude|amplitude]]-[[Phase|phase]] form. Let's set our general solution equal to some arbitrary function with an amplitude and phase constant.
$$
x(t)=C\cos \omega t+D\sin \omega t=A\cos(\omega t+\varphi)
$$
This takes advantage of the geometric properties of cosine and sine, so we can define the resultant magnitude of our new function $A$ as,
$$
A=\sqrt{ C^2+D^2 }
$$
and the phase constant is simply the angle between our resultant magnitude and the horizontal, given by
$$
\varphi=-\arctan\left( \frac{D}{C} \right)
$$
Thus we obtain our final solution,
$$
\boxed{x(t)=A\cos(\omega t+\varphi)}
$$
where $A$ and $\varphi$ are defined in terms of our constants found previously.





