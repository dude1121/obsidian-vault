---
tags:
  - physics
  - oscillatory-motion
---
In physics a **forced oscillator** is an [[Simple harmonic motion|oscillator]] that experiences both a [[Retarding Force|retarding force]] (thus [[Damped oscillations|damping]] the oscillations) as well as some external [[Force|force]] that transfers [[Energy|energy]] into the system. 

Consider an example of a damped oscillator driven by a force that varies periodically, such as $F(t)=F_{0}\sin \omega t$ where $F_{0}$ is constant and $\omega$ is the [[Angular Frequency|angular frequency]] of the driving force. In general, the frequency of the driving force is variable but the natural frequency $\omega_{0}$ is fixed by $k$ and $m$. Our differential equation for this situation is
$$
F_{0}\sin \omega t - b\ \frac{dx}{dt} -kx=m\ \frac{d^2x}{dt^2}
$$
This is a [[Ordinary Differential Equation#Nonhemogenous|linear nonhomegenous second order differential equation]]. The solution is
$$
x(t)=A\cos(\omega t+\varphi)
$$
where the [[Amplitude|amplitude]] $A$ is
$$
A=\frac{F_{0}/m}{\sqrt{ (\omega ^2-\omega_{0}^2)^2+\left(\displaystyle \frac{b\omega}{m}\right)^2 }}
$$
where $\omega_{0}=\sqrt{ k/m }$ is the natural frequency of the undamped system. For small damping, the amplitude is large when the frequency of the driving force is near the natural frequency of oscillation, that is $\omega \approx \omega_{0}$. This phenomenon is called [[Resonance|resonance]] and the natural frequency is also known as the *resonant frequency* of a system.
