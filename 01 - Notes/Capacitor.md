---
tags:
  - electromagnetism
  - circuit-analysis
  - physics
  - fringing
  - charging-state
  - steady-state
---

A **capacitor** is a two-terminal component that has the ability to temporarily store [[Charge|charge]] when a voltage is applied across its terminals. The amount of charge that a capacitor can store is determined by its [[Capacitance|capacitance]]. 

# Construction

A capacitor's construction can vary but they all operate based on the same principle. At their core, a capacitor is made up of two plates separated by a [[Dielectric|dielectric]]. 

![[Dielectric]]

When a [[Voltage|voltage]] is applied across these plates, opposite charges gather on each plate, such that one plate becomes *positively charged* and the other is *negatively charged*. The dielectric, combined with the *[[Distance|distance]]* between the two plates, prevent these charges from "jumping" across and shorting out the capacitor. The charges on each plate create an [[Electric Field|electric field]].
![[capacitor-fringing.png]]
This field extends to the opposite plate. The field mainly extends directly across to the other plate, but some flux lines extend beyond the capacitor in a behaviour called "fringing". This fringing reduces the net capacitance of the capacitor somewhat. For most purposes, we can ignore fringing and assume that 100% of the field strength reaches the other plate through the dielectric.

The strength of the electric field, denoted with the scripted $\mathcal{E}$, can be found by,
$$
	\mathcal{E}=\frac{V}{d}
$$
where $V$ is the voltage $[\text{V}]$ across the two plates and $d$ is the distance between them in [[Metre|metres]] $[\text{m}]$. 
![[capacitor-dielectric.png]]
As the charges gather on each plate, the oppositely charged particles within the atoms of the dielectric become [[Polarization|polarized]], turning them into *[[Dipole|dipoles]]*. This polarization induces a tiny voltage across the atom, and the sum of all these tiny voltages is defined as the dielectric voltage.
![[capacitor-dielectrics.png]]
If we separate the plates with only air, we generate a given electric field strength, $\mathscr{E}_1$. However, if we add in a dielectric in between the plates, the dielectric voltage will itself generate an opposing electric field. This reduces the net electric field strength between the plates. But our formula above states that $\mathcal{E}\propto V\cdot d^{-1}$. Since the distance is not changing, the voltage across the plates must change to keep the electric field strength constant. This is accomplished by more charges gathering on each plate. This has the added effect of increasing the capacitance since
$$
	C=\frac{Q}{V}
$$
We can also define the capacitance in terms of the construction of the capacitor given by,
$$
	C=\epsilon\frac{A}{d}
$$
Since a dielectric like *mica* has a higher [[Permittivity|permittivity]] than air, this also results in an increase in capacitance, despite the fact that the area and distance remain unchanged.

# Behaviour

## DC Circuits

In a [[DC Electricity|dc]] circuit, the capacitor has two states: the transient charging / discharging stage, and *steady state*.

### Transient Charging State

In this phase, the charges are deposited onto the plates of the capacitor. This continues until the voltage across the capacitor approaches (but will never truly equal) the [[Voltage Sources|source]] voltage. This relationship is [[Exponential|exponential]] which is why the capacitor will never truly equal the source voltage, but it will come very close to it, so close that we can assume they are in fact equal.

The time it takes to charge the capacitor depends on two factors: the capacitance of the capacitor, and the resistance in the circuit. We can model voltage across the capacitor as a [[Function|function]] of time by,
$$
	v_C=E\left(1-e^{-t/\tau}\right)
$$
where $E$ is the source voltage $[\text{V}]$, $e$ is [[Euler's Number]], $t$ is the time elapsed in seconds $[\text{s}]$, and $\tau$ is what we call the *time constant* and is also measured in seconds $[\text{s}]$. The time constant for a capacitor is defined as
$$
	\tau=RC
$$
where $R$ is the resistance $[\Omega]$ and $C$ is the capacitance $[\text{F}]$. The time constant is defined as the time it takes for the capacitor to charge 63.2% of the way to the source voltage. Each time constant is another 63.2% of the way. 
![[voltage vs time capacitor charge.png]]
From this plot, we see that by the time 5 time constants have elapsed, the capacitor's voltage is 99.3% of the source voltage. For most purposes, this is sufficient to assume that it is 100% of the source voltage. Therefore, in most cases, we assume that when $t=5\tau$, $v_C=E$. 

Note this relationship between resistance and the time constant. Since $\tau \propto R$, as $R\rightarrow \infty$, $\tau \rightarrow \infty$. This means we can increase the charge time by increasing the capacitor's series resistance, and this is a linear relationship. Contrast that with an inductor, where $\tau \propto R^{-1}$. This relationship is non-linear and it means that for most values of $R$, $\tau_{L}>\tau_{R}$.

> [!info] Time-Dependent Variables
> Note that we use $v_C$ for the capacitor voltage and not $V_C$. This is because the voltage across the capacitor varies with time and is therefore not constant. That is,
> $$
> 	\frac{dv}{dt}=\dot{v}\neq0
> $$
> In general, lowercase variables indicate a time-varying value, whereas uppercase variables indicate a constant value.

What about the current? In a similar manner, we apply an exponential function to the current. Consider the following simple circuit.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=$E$] (0,-2)
	node[ground]{}
	(0,0) to[cspst] (2,0)
	to[R, l=$R$, v<=$v_R$, f=$i_{C}$] (4,0)
	to[C, l=$C$, v<=$v_C$] (4,-2)
	(4, -2) -- (0, -2)
;

\end{circuitikz}
\end{document}
```

Let's do a [[Kirchhoff’s Voltage Law|KVL]] loop around the circuit.
$$
	E-v_R-v_C=0\text{V}
$$
Isolating for $V_R$,
$$
	v_R=E-v_C
$$
Since $v_C$ is going to steadily increase until it reaches $E$, this means that when $v_C=E$, $v_R=0\text{V}$. This also means that the current through the resistor, $i_R$, must equal $0\text{A}$. But when the switch is first thrown and $v_C=0\text{V}$, then $v_R=E$ and by extension $i_R=v_R/R$. Therefore, the current through the circuit is not to be modeled as exponential *growth*, but rather exponential *decay*. This relationship is given by,
$$
	i_{T}=I_{Max}\left(e^{-t/\tau}\right)
$$
Where $I_{Max}$ is the maximum current through the circuit when $t=0\text{s}$, typically given as $E/R$.

There is, however, another way to find the current through a capacitor.
$$
i_C=C\frac{dv}{dt}
$$
If we take the [[Derivative|derivative]] of our previous voltage expression, 
$$
\begin{aligned}
\frac{dv_C}{dt}&=\frac{d\left(E\left(1-e^{-t/\tau}\right)\right)}{dt}\\
&=E\cdot -e^{-t/\tau}\frac{d\left(-\frac{t}{\tau}\right)}{dt}\\
&=\frac{Ee^{-t/\tau}}{\tau}
\end{aligned}
$$
Then substitute that derivative into the expression above,
$$
i_C=C\frac{Ee^{-t/\tau}}{\tau}
$$
Since $\tau=RC$,
$$
i_C=\frac{E}{R}e^{-t/\tau}
$$
And just like that we arrive at the same equation we found earlier.

Since we define the current through the capacitor in terms of a derivative, we can likewise define the voltage across the capacitor as an [[Integral|integral]] if the current is known but the voltage is not.
$$
	v_C=\frac{1}{C}\int i_C\ dt
$$

Once $5\tau$ has elapsed, we can consider the capacitor fully charged. However, what happens when the source is disconnected? Remember that the capacitor has built up a voltage across it, but crucially this voltage is in the *opposite* polarity of the source. This means that the current through the circuit will change direction, and travel the opposite way.

---
#### Example

Consider the following circuit:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,2) to[battery, l_=$E_{S1}$, a^=$12V$] (0,-2)
(0,2) -- (2,2) node[ocirc, label=$1$]{}
(2.5,2) to[cspst] (2,2)
(2.5,1.5) node[ocirc, label=$2$]{}
(2.5,2) to[R, a=$R_1$, l=$20k\Omega$, v<=$v_{R1}$, f=$i_{C1}$, voltage shift=4] (6,2)
	to[C, l=$C_1$, a=$0.05\mu F$, v^<=$v_{C1}$, voltage shift=4] (6,-2)
	(6, -2) -* (2.5, -2)
	(0, -2) -* (2.5, -2)
	to[R, l=$R_2$, a=$10k\Omega$] (2.5, 1.5)
;

\end{circuitikz}
\end{document}
```

Let's consider the circuit in two states: the switch in position 1, and the switch in position 2 after the capacitor has been fully charged.

*In Position 1*

With the switch in position 1, this becomes a series circuit consisting of $E_{S1}$, $R_1$, and $C_1$. In this state, assuming the capacitor is completely discharged at $t=0\text{s}$ (i.e. $v_{C1}=0\text{V}$), we can create an expression for the voltage across the capacitor and find how long it will take for it to become "fully charged". 
$$
\begin{aligned}
	v_{C1}&=E_{S1}\left(1-e^{-t/\tau}\right)\\
	&=12\text{V}\left(1-e^{-t/\tau}\right)
\end{aligned}
$$
To find our time constant, $\tau$, we use the relationship $\tau=RC$. Since in the charging phase the only resistance we need to consider is $R_1$, we use that value for $R$.
$$
\begin{aligned}
	\tau&=R_1C_1\\
	&=(20\text{k}\Omega)(0.05\mu\text{F})\\
	&=1\text{ms}
\end{aligned}
$$
Since we consider the capacitor "fully charged" after $5\tau$, we can therefore say that the capacitor will be charged after $5\text{ms}$. Using our above formula we can find what the actual voltage will be after $5\tau$.
$$
\begin{aligned}
	v_{C1}&=12\text{V}\left(1-e^{-5\tau/\tau}\right)\\
	&=12\text{V}\left(1-e^{-5}\right)\\
	&=11.919\text{V}
\end{aligned}
$$
As we see, it is not that far off from the full $12\text{V}$.

The current can be found by using this same $\tau$.
$$
\begin{align*}
	i_{C1}&=\frac{E_{S1}}{R_1}\left(e^{-t/\tau}\right)\\
	&=\frac{12\text{V}}{20\text{k}\Omega}\left(e^{-5\tau/\tau}\right)\\
	&=4.043\mu\text{A}
\end{align*}
$$
As expected, this value is very close to $0\text{A}$ after $5\tau$.  

*In Position 2*

When the capacitor is fully charged (i.e. $v_{C1}=E_{S1}$) and we throw the switch to position 2, we have removed the voltage source from the circuit, as seen below

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,2) to[battery, l_=$E_{S1}$, a^=$12V$] (0,-2)
(0,2) -- (2,2) node[ocirc, label=$1$]{}
(2.5,2) to[ospst] (2,2)
(2.5,1.5) node[ocirc, label=$2$]{}
(2.5,2) to[R, a=$R_1$, l=$20k\Omega$, v=$v_{R1}$, f<=$i_{C1}$, voltage shift=4] (6,2)
	to[C, l=$C_1$, a=$0.05\mu F$, v^<=$v_{C1}$, voltage shift=4] (6,-2)
	(6, -2) -* (2.5, -2)
	(0, -2) -* (2.5, -2)
	to[R, l=$R_2$, a=$10k\Omega$] (2.5, 1.5)
;

\end{circuitikz}
\end{document}
```

The circuit is still series, but now it consists of $R_1$, $C_1$, and $R_2$. When the capacitor begins to discharge it acts like a voltage source, flowing from positive to negative. This has the effect of *changing the current direction*. Now, instead of current flowing into the capacitor $C_1$, it flows out from $C_1$. It will continue to do so until the capacitor is discharged (i.e. $v_{C1}=0\text{V}$). How long does this take?

The expression for a capacitor discharging is one of exponential decay, as opposed to exponential growth when it is charging. Much like our expression for current, the expression for voltage in a discharging capacitor is:
$$
	v_{C1}=V_0\left(e^{-t/\tau}\right)
$$
where $V_0$ is the capacitor's voltage the moment before it began to discharge. The current therefore is given as:
$$
\begin{aligned}
	i_{C1}&=C\frac{dv_{C1}}{dt}\\
	&=C\left(-\frac{V_0e^{-t/\tau}}{\tau}\right)\\
	&=-\frac{V_0}{R}e^{-t/\tau}
\end{aligned}
$$
Note that the expression for current is negative since it is now travelling in the opposite direction. However, it is important to note that the value of $R$ has now changed since the circuit now contains $R_1$ and $R_2$. $R=R_1+R_2=30\text{k}\Omega$. $\tau$ therefore changes as well,
$$
	\tau=RC_1=30\text{k}\Omega\cdot0.05\mu\text{F}=1.5\text{ms}
$$
So while it took $5\text{ms}$ for the capacitor to fully charge, it will take $7.5\text{ms}$ for it to completely discharge, due to the added [[Resistance|resistance]].

---

### Steady State

As discovered above, after $5\tau$, the capacitor is fully charged. At this point, the current through it becomes $0\text{A}$. However, when the circuit is first energized or the switch is first thrown to connect the capacitor to a voltage source, the current is its maximum value. We can therefore characterize the capacitor in familiar terms.

> [!info] Steady State Capacitor
> When a capacitor is first connected, it behaves like a *short*, since the current is maximum and the voltage across it is $0\text{V}$. However, after $5\tau$, it acts like an *open*, since the current is $0\text{A}$ and the voltage across it is maximum.

## AC Circuits

For a given voltage across the capacitor, the greater the capacitance, the greater the current. An increase in [[Frequency|frequency]] corresponds to an increase in the rate of change of the voltage across the capacitor and therefore an increase in the current through the capacitor. Since, 
$$
	i_C=C\frac{dv_C}{dt}	
$$
and,
$$
	v_C=V_{pk}\sin(\omega t)
$$
then,
$$
\begin{aligned}
	i_C&=C\frac{d}{dt}[V_{pk}\sin(\omega t)]\\
	&=C\cdot V_{pk}\cdot\omega\cos(\omega t)\\
	&=C\cdot V_{pk}\cdot\omega\sin(\omega t + 90\degree)
\end{aligned}
$$
This introduces a [[phase shift]] between the current and the voltage of $90\degree$ (or $\frac{\pi}{2}$).
![[capacitor-leading.png]]
If we imagine this graph as an oscilloscope output with the voltage in red and current in blue, we see that the current hits its maximum point $90\degree$ before the voltage does. In this case, we say that the current is *leading* the voltage. 

> [!info] Leading Current
> In an ideal capacitor, the current will always lead the voltage by $90\degree$.

To find the opposition provided by the capacitor, we can divide the peak voltage by the peak current. In this case,
$$
	Opp.=\frac{V_{pk}}{C\cdot V_{pk}\cdot\omega}=\frac{1}{\omega C}=(\omega C)^{-1}
$$
This opposition is called [[Reactance|reactance]] and for a capacitor it is defined as
$$
	X_C=\frac{1}{\omega C}
$$
This reactance can be written as a [[Complex Numbers|complex number]] by separating it into its real and imaginary components. Since reactance has no real component, the resulting reactance is simply,
$$
	X_C=0+j\frac{V_C}{I_C}\Omega
$$
We can also write it in polar form as,
$$
	X_C=X\angle{\theta}
$$
As an example, suppose $\mathbf{V_{C}}=15\text{V}\angle 0\degree$ and $\mathbf{I_{C}}=250\text{mA}\angle 90\degree$. To find the reactance of the capacitor,
$$
\begin{aligned}
\mathbf{X_{C}}&=\frac{\mathbf{V_{C}}}{\mathbf{I_{C}}}\\
&=\frac{15\text{V}\angle 0\degree}{250\text{mA}\angle 90\degree}\\
&=60\Omega\angle {-90}\degree
\end{aligned}
$$
From this we can see that the reactance of an ideal capacitor has an angle of $-90\degree$. 

### Frequency Response

As discussed above, the reactance of a capacitor is given by,
$$
	X_C=\frac{1}{\omega C}
$$
where $\omega=2\pi f$. This means that a capacitor's reactance has an inverse relationship with the frequency.
![[Capacitor-frequency-response.png]]
Above is a plot of the reactance vs frequency for two different capacitors, the red line is a capacitor of $30\text{nF}$, the purple is a capacitor of $10\text{nF}$, and the black line is a capacitor of $100\text{nF}$. It is evident that an increase in capacitance corresponds to the graph approaching the origin, and therefore a more sensitive response to changes in its frequency.

As $f\rightarrow0$, $X_C\rightarrow\infty$, meaning that at very low frequencies a capacitor behaves as an open (as demonstrated at the lowest frequency, DC, where at steady state a capacitor behaves as an open). As $f\rightarrow\infty$, $X_C\rightarrow0$, meaning that at very high frequencies, a capacity behaves like a short. This is a much less gradual change than an [[Inductor|inductor]]. An inductor's reactance vs time plot is linear, this is not. 

### Practical Response

In theory, a capacitor is treated as *ideal*. That is, there are no [[Inductance|inductive]] or resistive features within the component.
```tikz 
\usepackage{circuitikz} 
\begin{document} 
\begin{circuitikz}[american voltages]
\draw 
(0,0) to[cC, o-o] (2,0);
\end{circuitikz} 
\end{document} 
```
However in practice there are some stray inductances and resistances that come into play. The practical model of a capacitor looks like
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages]
\draw
(0,0) to[L,o-, l=$L_s$] (2,0)
	to[R, l=$R_s$, -*] (4,0)
	to[cC, l=$C$, *-*] (8,0)
	(4,0) -- (4, -1)
	to[cC, l=$C_{AC}$, *-] (6, -1)
	to[R, l=$R_d$, -*] (8, -1)
	(4, -1) -- (4, -2)
	to[R, l=$R_p$, *-*] (8,-2)
	(8, -2) -- (8, 0)
	(8, 0) -- (9, 0) node[ocirc]{}	
;

\end{circuitikz}
\end{document}
```
Much like an inductor, there exists a frequency threshold where a capacitor will begin to behave as an inductor. This stray inductance $L_s$ comes from the capacitor leads, which may at first be very small (a capacitor with $2\text{cm}$ leads will have a stray inductance of about $200\text{nH}$) but it will have an impact at high frequencies.

$R_d$ represents the energy lost due to molecular [[Friction|friction]] within the dielectric due to the [[AC Electricity|ac]] voltage. The relative permittivity ($\epsilon_{r}$) of the dielectric decreases with increasing frequencies *until* a certain point at which it will turn around and begin to increase at very high frequencies. The capacitor $C_{AC}$ is labelled as such because it is not present in DC conditions. 

$R_p$ is the resistance of the dielectric (typically on the order of $\text{T}\Omega$)
![[Capacitor-VHF-response.png]]
For the capacitor that had its frequency response plotted above, it remained nearly ideal until about $f=3.7\text{MHz}$. After that, it begins to exhibit an inductive response. Also to note, an electrolytic capacitor typically is restricted to applications where $f\leq 10\text{kHz}$, whereas a mica or ceramic capacitor can be used up to and above $f=10\text{MHz}$.