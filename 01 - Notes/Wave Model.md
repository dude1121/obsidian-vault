---
tags:
  - physics
---
The **wave model** is a physics model for solving problems involving waves, both [[Mechanical Wave|mechanical]] and [[Electromagnetic Radiation|electromagnetic]]. 
# Travelling wave
The travelling wave analysis model is used in situations in which a wave moves through space without interacting with other waves or particles.
![[wave-wavelength-period-amplitude.png]]
In the figure above we can describe the wave using different terms.

The **crest** refers to the highest point in the wave. The **trough** is the lowest point in the wave.

The **[[Wavelength|wavelength]]** $\lambda$ is the [[Distance|distance]] between two identical points, in the case above it is the distance between two crests or troughs.

The **[[Period|period]]** $T$ is the time interval required for two identical points of adjacent waves to pass by a point. Inversely, the **[[Frequency|frequency]]** is the number of crests (or troughs, or *any* unique point on the wave) that pass a given point in a unit time interval. Frequency and period are related by
$$
f=\frac{1}{T}
$$
The **[[Amplitude|amplitude]]** $A$ is the maximum distance the wave travels from its equilibrium point. 

Mechanical waves travel at a specific speed and this speed is determined by the properties of the medium being disturbed.

We can create a relationship for this wave, namely that at $t=0$,
$$
y(x,0)=A\sin\left( \frac{2\pi}{\lambda}x \right)
$$
If the wave moves to the right with some speed $v$, the wave function at some later time $t$ is,
$$
y(x,t)=A\sin\left[\frac{2\pi}{\lambda}(x-vt) \right]
$$
Since the speed is distance over time, we can re-write our expression for speed as,
$$
v=\frac{\Delta x}{\Delta t}=\frac{\lambda}{T}
$$
Substituting that into our equation we get,
$$
y(x,t)=A\sin\left[2\pi\left( \frac{x}{\lambda}-\frac{t}{T} \right) \right]
$$
We can express this wave function in an even more convenient form by defining two other quantities: the [[Wave Number|angular wave number]] $k$ and the [[Angular Frequency|angular frequency]] $\omega$.
$$
k=\frac{2\pi}{\lambda}
$$
$$
\omega=\frac{2\pi}{T}
$$
Using these definitions we can express the wave function in the much simpler,
$$
y(x,t)=A\sin(kx-\omega t)
$$
The wave speed can therefore be defined as,
$$
v=\frac{\omega}{k}=\lambda f
$$
One final addition to our wave equation is the [[Phase Constant|phase constant]] $\varphi$. This represents a horizontal shift to our wave equation such that it no longer has the value of $0$ when $x=0$ and $t=0$.
$$
\boxed{y(x,t)=A\sin(kx-\omega t+\varphi)}
$$
