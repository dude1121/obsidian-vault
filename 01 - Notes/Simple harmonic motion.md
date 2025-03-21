---
tags:
  - physics
  - oscillatory-motion
---
A particle in **simple harmonic motion** is a model used to represent oscillatory situations. An example of this is [[Spring motion|spring motion]] or a [[Pendulum|pendulum]]. The following assumes there is no [[Damped oscillations|damping]]. If the pendulum is damped, the system becomes a [[Forced Oscillator|forced oscillator]].From examining a simple spring, we see that,
$$
a=-\frac{k}{m}x
$$
Since [[Acceleration|acceleration]] is the second time [[Derivative|derivative]] of the object's [[Position|position]],
$$
\frac{d^2x}{dt^2}=-\frac{k}{m}x
$$
We can define the term $k/m$ as $\omega^2$. Doing this allows us to solve the [[Ordinary Differential Equation|differential equation]] easier. The derivation for this relation can be found [[Simple harmonic motion derivation|here]], but the end result is the following equation:
$$
x(t)=A \cos(\omega t+\varphi)
$$
where $A$, $\omega$, and $\varphi$ are constants. $A$ is the [[Amplitude|amplitude]] of the function and in the case of an oscillator it represents the furthest point from equilibrium the point under observation will stray. $\omega$ as defined above is $\omega=\sqrt{ \frac{k}{m} }$ and it represents the [[Angular Frequency|angular frequency]] of the oscillator. $\varphi$ is the [[Phase Constant|phase constant]], also sometimes called the initial phase angle, and it is determined uniquely by the position and velocity of the particle at $t=0$. If the particle is at its maximum position at $t=0$ then $\varphi=0$. 

We can further define other parameters of harmonic motion. The [[Period|period]] is defined as the time duration for the particle to complete one cycle. It can be found by the relation,
$$
T=\frac{2\pi}{\omega}
$$
The inverse of the period is the [[Frequency|frequency]] which is the number of oscillations per unit time interval (typically seconds). It is defined as,
$$
f=T^{-1}=\frac{\omega}{2\pi}
$$
We could also express frequency and period in terms of the original $k$ constant and the mass of the object, namely,
$$
\begin{align}
T=2\pi \sqrt{ \frac{m}{k} }&&f=\frac{1}{2\pi}\sqrt{ \frac{k}{m} }
\end{align}
$$
This gives us an interesting relationship, that the frequency of a particle's oscillation is proportional to the square root of the spring constant $k$ and inversely proportional to the square root of the particle's [[Mass|mass]].

Just as we can express position this way we can also express [[Velocity|velocity]] and [[Acceleration|acceleration]]. 
$$
\begin{align}
v(t)=\frac{dx}{dt}=-\omega A\sin(\omega t+\varphi) \\
a(t)=\frac{d^2x}{dt^2}=-\omega^2A\cos(\omega t+\varphi)
\end{align}
$$
# Energy of the simple harmonic oscillator
Assuming the surface along which the block moves is [[Friction|frictionless]], we can expect that the total [[Mechanical Energy|mechanical energy]] is constant. The mass of the spring is also negligible, so the [[Kinetic Energy|kinetic energy]] of the system is simply,
$$
K=\frac{1}{2}mv^2
$$
We can substitute our relationship for velocity,
$$
K=\frac{1}{2}m\omega^2A^2\sin^2(\omega t+\varphi)
$$
We also know that the elastic [[Potential Energy|potential energy]] stored in the spring is equal to
$$
U=\frac{1}{2}kx^2
$$
Substituting in our equation for position,
$$
U=\frac{1}{2}kA^2\cos^2(\omega t+\varphi)
$$
Since $\omega^2=\frac{k}{m}$, we can express mechanical energy as,
$$
E_{\text{m}}=\frac{1}{2}kA^2(\sin^2(\omega t+\varphi)+\cos^2(\omega t+\varphi))
$$
Recalling the trig identity $\sin^2\theta+\cos^2\theta=1$ the term in the brackets simplifies to $1$ leaving,
$$
\boxed{E_{\text{m}}=\frac{1}{2}kA^2}
$$
This means that the total mechanical energy of a simple harmonic oscillator is a constant of the motion and is proportional to the square of the amplitude. This makes sense since at any given point the mechanical energy is the sum of the kinetic and potential, which  are constantly changing. When the particle is at its maximum displacement, it has entirely potential energy and no kinetic energy, and when it is at the equilibrium point, its energy is entirely kinetic with no potential component.
![[mech-energy-oscillator.svg]]
This can be seen graphically above, where the red and purple functions represent the kinetic and potential energy, and the blue function is the sum of the red and purple functions. The blue line remains constant despite the time-varying red and purple functions.