---
tags:
  - electromagnetism
  - circuit-analysis
  - physics
  - charging-state
  - steady-state
---
An **inductor** is a two-terminal component that has the ability to use electrical [[Energy|energy]] to generate a [[Magnetic Field|magnetic field]]. The strength of that magnetic field is given by the inductor's [[Inductance|inductance]]. Like the [[Capacitor|capacitor]], it exhibits its true characteristics only when there is a change in voltage or current. 

# Construction

Simply put, an inductor is not much more than a coil of wire, usually fitted with a core of some magnetic material, usually iron. The inductance of any inductor can be found by,
$$
L=\frac{\mu N^2 A}{\ell}
$$
where $\mu$ is the [[Permeability|permeability]] of the core material in [[Webers|webers]] per [[Amperes|ampere]]-[[Metre|metre]]  $[\text{Wb/Am}]$, $N$ is the number of turns of wire in the coil (typically unitless but sometimes marked with a $t$ for *turns*), $A$ is the cross-sectional area of the space within the coil $[\text{m}^2]$, and $\ell$ is the length of the coil $[\text{m}]$.

# Behaviour

## Practical Response

An ideal inductor has no other [[Resistance|resistive]] or [[Capacitance|capacitive]] characteristics.

```tikz 
\usepackage{circuitikz} 
\begin{document} 
\begin{circuitikz}[american voltages]
\draw 
(0,0) to[L, o-o] (2,0);
\end{circuitikz} 
\end{document} 
```

In practice this is not the case. In the *complete model* of an inductor, there is both a resistance associated with the winding of the coil and a stray capacitance in the inductor. 

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american voltages]
\draw
	(0,0) node[ocirc]{}
	(0,0) -- (0.5,0) node[circ]{}
	(0.5,0) to[R, l=$R_s$] (2.5,0)
		to[L, l=$L$] (4.5,0) node[circ]{}
	(4.5,0) -- (5,0) node[ocirc]{}
	(0.5,0) -- (0.5,-1)
	(0.5, -1) to[cC, l=$C$] (4.5,-1)
	(4.5, -1) -- (4.5, 0)
;
\end{circuitikz}
\end{document}
```

The stray capacitance is so small that it can mostly be ignored, but since resistance is given by,
$$
R=\frac{\rho \ell}{A}
$$
and the coil is a long piece of material, the resistance can often play a large role in the way an inductor behaves within a circuit. Therefore, we often use the *practical model*,
```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american voltages]
\draw
	(0,0) to[R, l=$R_s$, o-] (2,0)
		to[L, l=$L$, -o] (4,0)
;
\end{circuitikz}
\end{document}
```
to model an inductor.

## DC Circuits

In a dc circuit, an inductor, like a capacitor, has two states: the transient charging / discharging state, and *steady state*.

### Transient Charging State

Consider the following circuit:
```tikz
\usepackage{circuitikz}

\begin{document}
	\begin{circuitikz}[european voltages]
		\draw
		(0,0) to[battery, l=$E_{S1}$, a=$50$V, f_<=$i_T$] (0, -4)
			node[ground]{}
		(0,0) to[ospst, l=$SW_1$] (3,0)
		(3,0) to[R, l=$R_1$, a=$2$k$\Omega$, v<=$v_{R1}$, voltage shift=4] (7,0)
		to[L, l=$L_1$, a=$4$H, f=$i_{L1}$, v<=$v_{L1}$, voltage shift=4] (7,-4)
		(3,0) to[R, l_=$R_2$, a^=$3$k$\Omega$, v<=$v_{R2}$, voltage shift=4, *-*] (3,-4)
		(0, -4) -- (7,-4)
		;
	\end{circuitikz}
\end{document}
```

Assuming $v_{{L_1}}=0\text{V}$ when the switch $SW_{1}$ is closed, the inductor will begin to charge or *store* the energy provided to it in the form of a magnetic field. There is no current through the inductor the moment the switch is closed, meaning there is by extension no current through the entire circuit (i.e. $i_{T}=0\text{A}$). This is due to the fact that an inductor always *resists* a change in its current by means of a magnetic field.

>[!info] Inductor "Choking"
>An inductor will always try to resist a change in its current. It accomplishes this by creating an opposing magnetic field to the flow of charge. It will try to maintain the same current that was present prior to the change. This reluctance to change is sometimes referred to as *choking*.

Since the current prior to $t=0\text{s}$ was $0\text{A}$, the inductor will first attempt to maintain this state. Since the current in the entire circuit is also $0\text{A}$, the voltage across each of the resistors is $0\text{V}$ (since $V=IR$). By [[Kirchhoff’s Voltage Law|KVL]], then, we can conclude that at  $t=0\text{s}$, the voltage across the coil must equal the source voltage, $E_{S1}=v_{L1}$. As the current through the inductor begins to increase, the current in the circuit begins to increase, meaning the resistors develop a voltage drop across them, decreasing the voltage across the inductor. This will continue until the voltage across the inductor is $0\text{V}$ and the current through the inductor is its maximum value.

The rate at which the voltage decreases (or, *decays*) and the current increases (or, *grows*) can be modeled the same way a capacitor's transient state is modeled, as an *[[Exponential|exponential]]* function.
$$
i_{L}=I_{Max}\left(e^{-t/\tau}\right)
$$
$$
v_{L}=E\left(1-e^{-t/\tau}\right)
$$
It follows that we can express the current as an [[integral]] of the inductor's voltage over time, and the voltage can be expressed a the [[derivative]] of the current with respect to time.
$$
i_{L}=\frac{1}{L}\int v_{L}\ dt
$$
$$
v_{L}=L\frac{di_{L}}{dt}
$$
Our time constant, $\tau$, must be defined different than with a capacitor, however. 
$$
\tau=\frac{L}{R}
$$

After $5\tau$, we can assume that the voltage is $0\text{V}$ and the current is its maximum value. In the above circuit, our time constant would be
$$
\tau=\frac{L_{1}}{R_{1}}=\frac{4\text{H}}{2\text{k}\Omega}=2\text{ms}
$$
meaning that after $10\text{ms}$, we could assume the inductor to be in *steady state*. Note the relationship between resistance and the time constant of an inductor. In a capacitor, as $R\rightarrow \infty$, $\tau\rightarrow \infty$. This means that we can increase the charge time of a capacitor by increasing its series resistance. This relationship is also linear. With an inductor, however, this is not the case, and as $R\rightarrow \infty$, $\tau \rightarrow 0$. Unlike with a capacitor, if we want to increase the charge time of an inductor we actually need to *reduce* the inductor's series resistance.

The current at $5\tau$ in the circuit above is therefore,
$$
i_{Max}=\frac{50\text{V}}{2\text{k}\Omega}=25\text{mA}
$$
When the switch is opened, the magnetic field the inductor generated collapses and it begins its release stage. Redrawing the above circuit with the switch opened...
```tikz
\usepackage{circuitikz}

\begin{document}
	\begin{circuitikz}[european voltages]
		\draw
		(0,0) to[ospst, l=$SW_1$, o-] (3,0)
		(3,0) to[R, l=$R_1$, a=$2$k$\Omega$, v<=$v_{R1}$, voltage shift=4] (7,0)
		to[L, l=$L_1$, a=$4$H, f=$i_{L1}$, v=$v_{L1}$, voltage shift=4] (7,-4)
		(3,0) to[R, l_=$R_2$, a^=$3$k$\Omega$, v=$v_{R2}$, voltage shift=4, *-*] (3,-4) node[ground]{}
		(3, -4) -- (7,-4)
		;
	\end{circuitikz}
\end{document}
```
Note that because the inductor "wants" to maintain the same current direction prior to the change, the current does not swap direction as with a capacitor. Instead, an [[Electromotive Force|emf]] develops across the inductor, and it begins to behave like a source. The current in the release stage can be given by,
$$
i_{L}=i_{0}\left(e^{-t/\tau}\right)
$$
where $i_{0}$ is the current at the moment the switch was opened. The voltage is therefore,
$$
\begin{aligned}
v_{L}&=L\frac{d_{i_{L}}}{dt}\\
&=L\frac{d}{dt}\left[i_{0}\left(e^{-t/\tau}\right)\right]\\
&=L\cdot i_{0}\cdot e^{-t/\tau} \frac{d}{dt}\left(-\frac{t}{\tau}\right)\\
&=-\frac{L\cdot i_{0}\cdot e^{-t/\tau}}{\tau}\\
&=-\frac{L\cdot i_{0}\cdot e^{-t/\tau}}{\frac{L}{R}}\\
&=-i_{0} \cdot R \cdot e^{-t/\tau}\\
\end{aligned}
$$
From this and our diagram, we see that while the current does not change, the voltage across the inductor *does* change polarity. Its also evident that the initial voltage at $t=0\text{s}$ is,
$$
v_{0}=-i_{0}\cdot R
$$
Assuming this switch is opened after the inductor had entered steady state, 
$$
\begin{aligned}
v_0&=-(25\text{mA})(2\text{k}\Omega+3\text{k}\Omega)\\
&=-125\text{V}
\end{aligned}
$$
This is far greater than the original source voltage of $50\text{V}$. Crucially, however, this large jump in voltage does not last long. It is only for an instant that it is this high, as the voltage begins to decay very quickly. Our new $\tau$ for the discharge stage is,
$$
\tau=\frac{4\text{H}}{2\text{k}\Omega+3\text{k}\Omega}=800\mu\text{s}
$$
Meaning that after just $4\text{ms}$, the voltage and current will both be *near* $0$. 

### Steady State

In steady state conditions, the voltage across the inductor is effectively $0\text{V}$ and the current through it is maximum. This is very much like a *short*. Recall that when the circuit is first energized, however, the opposite is true: the current is $0\text{A}$ and the voltage is maximum. This is very much like an *open*.

> [!info] Steady State Inductor
> When an inductor is first connected, it behaves like an *open*, since the voltage is maximum and the current through it is $0\text{A}$. However, after $5\tau$, it acts like a *short*, since the voltage is $0\text{V}$ and the current through it is maximum.

## AC Circuits

Recall that the voltage across an inductor is given by,
$$
v_{L}=L\frac{di_{L}}{dt}
$$
It follows then that an increase in frequency would result in an increase in voltage across the inductor, since the current is more rapidly changing with time. For any given sinusoidal current,
$$
i_{L}=I_M\sin(\omega t)
$$
its voltage is therefore,
$$
\begin{aligned}
v_{L}&=L\frac{d}{dt}\left[I_{M}\sin(\omega t)\right]\\
&=\omega \cdot L\cdot I_{M}\cos(\omega t)\\
&=\omega \cdot L\cdot I_{M}\sin(\omega t+90\degree)
\end{aligned}
$$
Its evident then that the voltage has a [[phase shift]] of $90\degree$ relative to the current.
![[inductor-lagging.png]]
If this graph represents both voltage (red) and current (blue) vs time, we see that the voltage reaches its peak value $90\degree$ prior to the current. We could say that the voltage is *leading* the current, but typically we always refer to the current's position relative to the voltage, meaning for an inductor we say that the current is *lagging*.

>[!info] Lagging Current
>In an ideal inductor, the current will always lag the voltage by $90\degree$.

The opposition to the applied voltage can be found by,
$$
\text{Opp.}=\frac{\text{Cause}}{\text{Effect}}=\frac{V_{M}}{I_{M}}=\frac{\omega \cdot L\cdot I_{M}}{I_{M}}=\omega L
$$
The opposition is therefore the product of the angular velocity ($\omega$) and the inductance. We call this opposition [[Reactance|reactance]].
$$
X_{L}=\omega L
$$
As an example, suppose a given inductor has a voltage across it of $\mathbf{V_{L}}=15\text{V}\angle 90\degree$ and a current through it of $\mathbf{I_{L}}=250\text{mA}\angle 0\degree$. The reactance is therefore,
$$
\begin{aligned}
\mathbf{X_{L}}&=\frac{\mathbf{V_{L}}}{\mathbf{I_{L}}}\\
&=\frac{15\text{V}\angle 90\degree}{250\text{mA}\angle 0\degree}\\
&=60\Omega\angle 90\degree
\end{aligned}
$$
We can see therefore that in an ideal inductor, its reactance will have an angle of $90\degree$.

### Frequency Response

As given above the reactance of an inductor is,
$$
X_{L}=\omega L
$$
where $\omega$ is the angular velocity given by $\omega=2\pi f$. The reactance of an inductor has a linear relationship with the frequency.
![[inductor-frequency.png]]
Here is a plot of three different inductors and their reactance vs frequency response. The orange line is an inductor with $L=1\text{H}$, red is $L=100\text{mH}$, and blue is $L=20\text{mH}$. The inductance alters only the slope of this plot, with inductors with very high inductances being very sensitive to changes in frequency, whereas smaller inductors can be relatively stable over larger frequency changes.

Because this relationship is linear, we can state that as $f\rightarrow \infty$, $X_{L}\rightarrow \infty$, meaning that at very high frequencies an inductor will begin to behave as an open, having a very high reactance.

### Practical Considerations

Recall the complete model of an inductor:
```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american voltages]
\draw
	(0,0) node[ocirc]{}
	(0,0) -- (0.5,0) node[circ]{}
	(0.5,0) to[R, l=$R_s$] (2.5,0)
		to[L, l=$L$] (4.5,0) node[circ]{}
	(4.5,0) -- (5,0) node[ocirc]{}
	(0.5,0) -- (0.5,-1)
	(0.5, -1) to[cC, l=$C_p$] (4.5,-1)
	(4.5, -1) -- (4.5, 0)
;
\end{circuitikz}
\end{document}
```
$R_{s}$ represents the copper losses due to [[Eddy Current|eddy currents]] forming in the core as well as [[Hysteresis|hysteresis]] losses due to core losses created by the rapidly reversing magnetic field. $C_{p}$ is the stray capacitance between the windings of the inductor.

In general, the larger the inductance $L$, the lower the frequency in which $R_{s}$ and $C_{p}$ become important. For example, for an inductor on the order of $\text{mH}$, it will stop being "ideal" at around $100\text{kHz}$, whereas an inductor on the order of $\mu\text{H}$ will stop behaving ideally around $1\text{Mhz}$. At this point, increases in frequency result in the inductive effects actually being over taken by the capacitive effects (because as $f\rightarrow \infty$, $X_{C}\rightarrow 0$. Since $C_{p}$ is in *parallel* with $L$, this effectively "shorts out" the inductance).
