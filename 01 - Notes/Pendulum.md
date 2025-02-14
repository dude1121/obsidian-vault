---
tags:
  - physics
  - oscillatory-motion
---
A **pendulum** is a mechanical system that exhibits [[Periodic Motion|periodic motion]]. It consists of a bob of mass $m$ suspended by a light string of length $L$ that is fixed at the upper end. The motion occurs in the vertical plane and is driven by the gravitational force. 
# Simple pendulum
When the angle $\theta$ the bob makes with the vertical is small enough ($<10\degree$) the pendulum can be approximated as a [[Simple harmonic motion|simple harmonic oscillator]].
![[pendulum.png]]
The bob has two main forces acting on it (ignoring [[Air Resistance|air resistance]]): the [[Tension|tension]] force in the string $\mathbf{\vec{T}}$, and the [[Gravitational Force|force of gravity]] $m \vec{g}$. The tangential component of gravity $mg\ \sin \theta$ always acts towards $\theta=0$, opposite the [[Displacement|displacement]] of the bob. Therefore, the tangential component is a *restoring force*.
$$
F_{t}=-mg\ \sin \theta=m \frac{d^2s}{dt^2}
$$
where $s$ is the bob's position measured along the arc it sweeps out. The negative sign indicates that this force always points in the opposite direction of displacement. $s$ is defined as,
$$
s=L\ \theta
$$
which means we can re-write the equation for $F_{t}$ as,
$$
\begin{align}
-mg\ \sin \theta&=m \frac{d^2(L\ \theta)}{dt^2} \\
-g\ \sin \theta&=L \frac{d^2\theta}{dt^2} \\
\frac{d^2\theta}{dt^2}&=-\frac{g}{L}\sin \theta
\end{align}
$$
 This is similar but not quite the same as our model for simple harmonic motion. $\theta$ is our [[Angular Position|angular position]], but instead of the [[Angular Acceleration|acceleration]] being proportional to the position it is proportional to the [[Sine|sine]] of the position. If we assume $\theta<10\degree$ we can use the [[Small Angle Approximation|small angle approximation]] in which $\sin \theta \approx \theta$ (provided $\theta$ is in [[Radian|radians]]). So long as $\theta$ remains less than $10\degree$ ($\approx 0.2\pu{ \! rad}$), $\sin \theta$ is approximately equal to $\theta$ within an accuracy of less than $1.0\%$. Therefore,
 $$
\frac{d^2\theta}{dt^2}=-\frac{g}{L}\theta\ \ \ (\text{for small values of }\theta)
$$
This time the solution for this [[Differential Equation|differential equation]] is,
$$
\theta\ (t)=\theta_{\text{max}}\cos(\omega t+\varphi)
$$
where
$$\omega=\sqrt{ \frac{g}{L} }$$
We can therefore define the period of oscillation as
$$
T=\frac{2\pi}{\omega}=2\pi \sqrt{ \frac{L}{g} }
$$
Since $2\pi$ and $g$ are constant, the period of oscillation is dependant solely on the length of the pendulum string. This is also interesting because it means a simple pendulum will oscillate at the same frequency regardless of [[Mass|mass]].
# Physical pendulum
If the pendulum is instead oscillating about a fixed axis that does not pass through the object's [[Centre of Mass|centre of mass]] we can not treat the system as a simple pendulum. Instead, this system is called a *physical pendulum*. 
![[physical-pendulum.png]]
The gravitational force in this case provides a [[Torque|torque]] about the axis through the pivot point $O$. The magnitude of this torque is $\tau=mgL\sin \theta$. This object can be modelled as a [[Rigid Object under constant angular acceleration|rigid object under a net torque]] and use the rotational form of [[Newton's Laws#Second Law|Newton's second law]], $\sum \tau=I\alpha$ where $I$ is the [[Moment of Inertia|moment of inertia]] of the object about the axis $O$. This results in the following expression:
$$
\begin{align}
I \frac{d^2\theta}{dt^2}&=-mgL\ \sin \theta \\
\ddot{\theta}&=-\left(\frac{mgL}{I}\right)\sin \theta
\end{align}
$$
If we make use of the same small angle approximation,
$$
\ddot{\theta}=-\left(\frac{mgL}{I}\right)\ \theta
$$
We can once again define an [[Angular Frequency|angular frequency]] $\omega$ as,
$$
\omega=\sqrt{ \frac{mgL}{I} }
$$
meaning the expression simplifies to,
$$
\ddot{\theta}=-\omega^2\theta
$$
Which gives us the same solution to the ODE as the simple pendulum:
$$
\theta\ (t)=\theta_{\text{max}}\cos(\omega t + \varphi)
$$
The period is,
$$
T=\frac{2\pi}{\omega}=2\pi \sqrt{ \frac{I}{mgL} }
$$
