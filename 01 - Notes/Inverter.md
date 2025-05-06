---
tags:
  - electrical-engineering
  - electronics
  - physics
---
An **inverter** is an electrical circuit that converts a [[DC Electricity|dc voltage]] into an [[AC Electricity|ac voltage]]. Inverters are used in applications like [[Variable Frequency Drive|VFDs]], [[Wind Turbine#|VVVF wind turbines]], or [[Power Factor|power factor]] correction. This design can be modified to create a [[Three Phase Inverter|three phase variation]].
# Overview of design
![[inverter-design.png]]
Any inverter can be broken down into three distinct parts: the power section, where the signal inversion actually occurs, the gate driver circuit, which controls which parts of the power section are conducting, and the [[Pulse Width Modulation|PWM]] control which essentially sets the timing for the gate driver. This PWM control can either be hardware or controlled by [[Microprocessor|microprocessors]].

At its core, an inverter circuit is two [[Half-Bridge Circuit|half-bridges]], otherwise known as an [[H-Bridge]].
# Sample circuit
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[](B){} to[vsource, l=$V_s$] ++(0,6) node[](A){}

(A) to[short] ++(1.5,0) node[circ](C){} to[cC, l=$C$] ++(0,-6) node[circ]{}

(C) to[short] ++(2,0) node[circ](F){} to[short] ++(0,-0.5) node[nigfete, anchor=D, bodydiode](Q1){} node[right]{$Q_1$}
(Q1.G) node[ocirc]{} node[left]{$G_1$}
(Q1.S) node[circ](D){} node[left]{$A$} to[short] ++(0,-2.25) node[nigfete, anchor=D, bodydiode](Q2){} node[right]{$Q_2$}
(Q2.G) node[ocirc]{} node[left]{$G_2$}
(Q2.S) to[short] (Q1.S |- B) node[circ](E){} to[short] (B)

(F) to[short] ++(2.5,0) node[circ](G){}  to[short] ++(0,-0.5) node[nigfete, anchor=D, bodydiode](Q3){} node[right]{$Q_3$}
(Q3.G) node[ocirc]{} node[left]{$G_3$}
(Q3.S) to[short] ++(0,-2.25) node[circ](H){} node[left]{$B$} node[nigfete, anchor=D, bodydiode](Q4){} node[right, yshift=-5mm, xshift=3mm]{$Q_4$}
(Q4.G) node[ocirc]{} node[left]{$G_4$}
(Q4.S) to[short] (Q4.S |- E) node[circ](I){} to[short] (E)

(D) to[short] ++(4,0) node[](J){} to[R, l=$R$] (J |- H) to[short] (H)

;
\end{circuitikz}
\end{document}
```
The above sample inverter circuit makes use of a [[Voltage Sources|dc voltage source]] which provides the initial dc voltage. It is in parallel with a capacitor $C$ referred to as the *dc-link capacitor*. This circuit has the following characteristics:
$$
\begin{align}
V_{A}=D_{1}V_{s}&&V_{B}=D_{2}V_{s}&&V_{o}=V_{A}-V_{B}
\end{align}
$$
Each half bridge ($Q_{1}$ and $Q_{2}$ vs. $Q_{3}$ and $Q_{4}$) is referred to having its own duty cycle, $D_{1}$ and $D_{2}$, respectively. The duty cycles are controlled by an [[Inverter Gate Driver|gate driver circuit]].

>[!note] Important!
>This duty cycle is the 'high-side' duty cycle, meaning that $D_{1}=60\%$ refers to $Q_{1}$ being on $60\%$ of the time, not $Q_{2}$. 

In the positive half cycle of the output ac signal, $D_{1}=D$ and $D_{2}=0$. This means that $V_{B}$ is effectively $0\ \pu{ V}$, meaning $V_{o}=V_{A}$. In the negative half cycle, $D_{1}=0$ and $D_{2}=D$. Therefore $V_{A}=0\ \pu{ V}$, and $V_{o}=V_{B}$.
# Adjusting output frequency
We can control the output frequency of an inverter by changing the values of $D_{1}$ and $D_{2}$. If $D_{1} > D_{2}$, the output polarity is positive, and if $D_{1}<D_{2}$, then the output polarity is negative. The duration of the output half cycle is determined by the PWM control.

Unless otherwise stated, we assume that the duration of each half cycle is identical, that is, that the inverter is *balanced*.
# Adjusting output voltage
The output voltage, as noted before, is equal to,
$$
V_{o}=V_{A}-V_{B}
$$
Since $V_{A}=D_{1}V_{s}$ and $V_{B}=D_{2}V_{s}$, the output voltage can be expressed as,
$$
V_{o}=V_{s}(D_{1}-D_{2})
$$
In the positive half cycle, $D_{2}=0$, meaning this simplifies to,
$$
V_{o}=DVs
$$
In the negative half cycle, $D_{1}=0$, meaning this simplifies to,
$$
V_{o}=-DV_{s}
$$
Therefore the average magnitude of the output voltage is,
$$
\boxed{V_{o}=DV_{s}}
$$
# Sine wave output
Up until now we've discussed an inverter for an ac square wave. Still an ac signal, but not necessarily the most useful signal. We recall that,
$$
V_{o}=V_{A}-V_{B}=DV_{s}
$$
If the duty cycle $D$ is constant, the output voltage is also constant. However, if we vary the duty cycle, we can also vary the output voltage. There are two main methods of accomplishing this.
## $100\%$ low-side
For the output to be positive, $V_{A}>V_{B}$. If we want a sinusoidal output, the amount by which $V_{A}$ is greater than $V_{B}$ must also vary according to a sinusoidal function. To make this easier, we can tie $V_{B}$ to $0\ \mathrm{V}$. For the negative cycle, we do the same thing for $V_{A}$. This means that only one half of the bridge is contributing to the sine wave. The advantage here is that we only need to program one duty cycle and just alternate which half bridge is applying it.

During the positive half cycle, $V_{A}=V_{pk}\sin(\omega t)$ and $V_{B}=0\ \mathrm{V}$. During the negative half cycle, $V_{A}=0\ \mathrm{V}$ and $V_{B}=-V_{pk}\sin(\omega t)$.
![[100-low-side-inverter.png]]
The duty cycle for each leg is determined by
$$
\begin{align}
D_{A}=\frac{V_{A}}{V_{s}}&&D_{B}=\frac{V_{B}}{V_{s}}
\end{align}
$$
For this method, the duty cycle is given by,
$$
\begin{align}
\text{From }0\degree\text{ to }180\degree&:D_{A}=\frac{V_{A}}{V_{s}}=\frac{V_{pk}}{V_{s}}\sin(\omega t)\ ; D_{B}=0\\
\text{From }180\degree\text{ to }360\degree&:D_{B}=\frac{V_{B}}{V_{s}}=-\frac{V_{pk}}{V_{s}}\sin(\omega t)\ ; D_{A}=0
\end{align}
$$
## $50\%$ offset
Instead of making the reference point $0\ \mathrm{V}$, we can instead vary both $V_{A}$ and $V_{B}$ to create our sinusoidal output. The advantage here is that the same duty cycle program works for both the positive and negative half cycles. 

This time, neither 'leg' is held at $0\ \mathrm{V}$. $V_{A}=\frac{1}{2}V_{s}+\frac{1}{2}V_{pk}\sin(\omega t)$ and $V_{B}=\frac{1}{2}V_{s}-\frac{1}{2}V_{pk}\sin(\omega t)$. This means that both legs have a dc offset of half the source voltage, but they are inverse waveforms of one another.
![[50-offset-inverter.png]]
As mentioned above, the duty cycle for each leg is determined by
$$
\begin{align}
D_{A}=\frac{V_{A}}{V_{s}}&&D_{B}=\frac{V_{B}}{V_{s}}
\end{align}
$$
For this method, the duty cycle is given by,
$$
\begin{align}
D_{A}&=\frac{V_{A}}{V_{s}}=0.5+\frac{V_{pk}}{2V_{s}}\sin(\omega t) \\
D_{B}&=\frac{V_{B}}{V_{s}}=0.5-\frac{V_{pk}}{2V_{s}}\sin(\omega t)
\end{align}
$$
$$
\begin{align}
\frac{d^2y}{dt^2}&=-6 \frac{dy}{dt}-9y \\
\frac{d}{dt}\left( \frac{dy}{dt} \right)&=-6 \frac{dy}{dt}-9y \\
\mathrm{Let\ }z=\frac{dy}{dt} \\
\frac{dz}{dt}&=-6z-9y \\
\frac{d^2z}{dt^2}&=-6 \frac{dz}{dt}-9 \frac{dy}{dt} \\
&=-6(-6z-9y)-9z \\
&=36z+54y-9z \\
\boxed{\frac{dz}{dt}=-6z-9y}
&&\boxed{\frac{d^2z}{dt^2}=27z+54y}
\end{align}
$$

$$
\begin{align}
\frac{d^2y}{dt^2}+6\frac{dy}{dt}+9y&=0 \\
\mathcal{L}\left\{y''\right\}+6\mathcal{L}\left\{y'\right\}+9\mathcal{L}\left\{y\right\}&=0 \\
s^2\mathcal{L}\left\{y\right\}-5s+2+6s\mathcal{L}\left\{y\right\}-30+9\mathcal{L}\left\{y\right\}&=0 \\
\mathcal{L}\left\{y\right\}(s^2+6s+9)&=28+5s \\
\mathcal{L}\left\{y\right\}&=\frac{28+5s}{s^2+6s+9} \\
&=28\cdot\frac{1}{(s+3)^2}+5\cdot\frac{s}{(s+3)^2} \\
y(t)&=28te^{-3t}+5e^{-3t}(1-3t) \\
&=28te^{-3t}+5e^{-3t}-15te^{-3t} \\
&=5e^{-3t}+13te^{-3t} \\
&=e^{-3t}(5+13t)
\end{align}
$$
$$
\boxed{y(t)=e^{-3t}(5+13t)}
$$
