---
tags:
  - electronics
  - electromagnetism
  - physics
  - circuit-analysis
  - components
  - semiconductors
---
A **BJT** (**B**ipolar **J**unction **T**ransistor) is a type of [[Transistor|transistor]] used for signal amplification and switching. It comes in two types: *npn* and *pnp*, referring to the arrangement of the doped regions within the device.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[npn](Q){}
(Q.C) -- ++(0,1) node[ocirc, label=\Large C]{}
(Q.B) -- ++(-1,0) node[ocirc, label=left:\Large B]{}
(Q.E) -- ++(0,-1) node[ocirc, label=below:\Large E]{}
;
\end{circuitikz}
\end{document}
```
This is called a *bipolar* transistor because it makes use of both [[Electron|electrons]] and [[Hole Current|holes]] as current carriers.

# Construction

A BJT consists of three [[Semiconductor|semiconductor]] regions, each doped in an alternating pattern. In an *npn* BJT, there are two *n*-type regions and one *p*-type regions, and the opposite is true in a *pnp* BJT.
![[bjt construction.png]]
The [[PN Junction|pn junction]] joining the base and the emitter is fittingly called the *base-emitter junction*, and the junction between the base and the collector is known as the *base-collector junction*. The base is very lightly doped compared to the emitter and collectors. The emitter is heavily doped, whereas the collector is only moderately doped. Because of this, the emitter and collector are *not* interchangeable. 

# Biasing

```tikz
\usepackage{circuitikz}
\begin{document}
	\ctikzset{resistors/scale=0.75, batteries/scale=0.8}
	\begin{circuitikz}
	\draw
	(0,0) node[npn](Q){}
	(Q.B) to[R, f<_=$I_B$] ++(-2,0) to[battery] ++(0,-2) node[ground]{}
	(Q.C) to[R, f<_=$I_C$] ++(0,2) -- ++(2,0) to[battery] ++(0,-5) node[ground]{}
	(Q.E) to[short, f=$I_E$] ++(0,-1.4) node[ground]{}
	;
	\draw
	(7,0) node[pnp, yscale=-1](Q){}
	(Q.B) to[R, f_=$I_B$] ++(-2,0) to[battery, invert] ++(0,-2) node[ground]{}
	(Q.C) to[R, f>_=$I_C$] ++(0,2) -- ++(2,0) to[battery, invert] ++(0,-5) node[ground]{}
	(Q.E) to[short, f<=$I_E$] ++(0,-1.4) node[ground]{}
	;
	\end{circuitikz}

\end{document}
```
Above are biasing arrangements for both an npn and pnp transistor. In both cases, the base-emitter junction is forward-biased (i.e., in the npn $V_{B}>V_{E}$ and in the pnp $V_{E}>V_{B}$) and the base-collector junction is reverse-biased. This is called *forward-reverse bias*.

Note the direction of the [[Current|currents]] in each circuit. In the npn circuit, the current flows into the transistor from the collector and base and out of the transistor via the emitter. In the pnp, the opposite occurs. In both cases though,
$$
I_{E}=I_{C}+I_{B}
$$
This follows from [[Kirchhoff's Current Law]]. 

# Characteristics 

The dc [[Current Gain|current gain]] of a transistor is the ratio of the dc collector current $I_{C}$ to the dc base current $I_{B}$. It is typically denoted as $\beta_{DC}$, but may be seen on datasheets as $h_{FE}$ (see datasheet values for hybrid parameters). 
$$
\beta_{DC}=\frac{I_{C}}{I_{B}}
$$
Typical values of $\beta_{DC}$ range from $20 - 200$. A related parameter is the dc alpha $\alpha_{DC}$, which is the ratio of the collector current $I_{C}$ to the emitter current $I_{E}$.
$$
\alpha_{DC}=\frac{I_{C}}{I_{E}}
$$
$\alpha_{DC}$ ranges typically from $0.95 - 0.99$ but is always less than $1$ because $I_{C}$ will always be at least slightly less than $I_{E}$. 

## Collector Characteristic Curves

Consider the following circuit:

```tikz
\usepackage{circuitikz}
\begin{document}

\begin{circuitikz}[american voltages]
\ctikzset{resistors/scale=0.75, batteries/scale=0.8}
\draw
(0,0) node[npn, scale=1.5](Q){}
(Q.E) to[short] (0,-2) node[ground](G){}
(Q.C) to[open, v^=$V_{CE}$] (Q.E)
(Q.B) to[R, f<_=$I_B$, l=$R_B$] ++(-2,0)
to[battery1, name=VBB, l=$V_{BB}$] ++(0,-2) to[short, -*] (G)
(Q.C) to[short, f<=$I_C$] ++(0,1) to[R, l=$R_C$] ++(2,0) node[](B){}
to[battery, l=$V_{CC}$] (G -| B) -- (G)
;
\end{circuitikz}
\end{document}
```
Assume $V_{BB}$ and $V_{CC}$ are variable [[Voltage Sources|voltage sources]], and $V_{BB}$ is set to produce a certain value of $I_{B}$ whereas $V_{CC}=0\pu{ V}$. In this state, both the base-emitter junction *and* the base-collector junction are forward biased, since $V_{B}=0.7\pu{ V}$ and $V_{C}\approx V_{E}=0\pu{ V}$. The base current $I_{B}$ is primarily flowing through the base-emitter junction since that is the path of lowest [[Impedance|impedance]], so $I_{C}$ will be near $0\pu{ A}$. When both junctions are forward biased like this, the transistor is said to be in *saturation*. In this state, the collector current $I_{C}$ will be its maximum value and it is not dependant on the base current. 

If we increase $V_{CC}$, $V_{CE}$ will increase with it. This therefore increases the collector current until the the base-collector junction is no longer reverse biased, i.e. when $V_{C}\approx 0.7\pu{ V}$. When this occurs, the transistor exits saturation and enters the *active* or *linear* region.
![[saturation-active-plot.png]]
In this region, the collector current remains nearly constant as $V_{CE}$ increases. In this mode, the following relationship holds:
$$
I_{C}=\beta_{DC}I_{B}
$$
When $V_{CE}$ gets too high, the base-collector junction goes into reverse breakdown and the collector current skyrockets. This can cause damage to the device, and as such no BJT transistor is operated in this region.

This relationship between saturation, linear, and breakdown is shown in the above plots for various values of $I_{B}$. When $I_{B}=0\pu{ A}$, the transistor is in cutoff, and it ideally has zero [[Conductance|conductance]]. This allows the transistor to be operated as a current controlled switch.

# Amplifier

A bipolar junction transistor can also act as a [[Voltage|voltage]] [[Amplifier|amplifier]] for ac signals. If an ac signal is superimposed on the dc bias voltage, the resulting output ac voltage will be amplified. Consider the following circuit:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
	(0,0) to[sV, l=$V_s$] ++(0,-3) node[ground](G){}
	(0,0) to[cC, invert, -*] ++(2,0) node[](A){}
	to[battery1, l=$V_{BB}$] ++(0,-3) node[ground]{}
	(A) to[R, l=$R_B$] ++(2,0) node[anchor=B, npn, scale=1.5](Q){$r_e'$}
	(Q.E) to[short] (G -| Q.E) node[ground]{}
	(Q.C) to[short] ++(0,1)
	to[R,l=$R_C$] ++(2,0) node[circ, label=above:$A$](D){}
	to[battery, l=$V_{CC}$] (G -| D) node[ground]{}
	;
\end{circuitikz}
\end{document}
```
The applied ac input voltage $V_{s}$ is coupled to the circuit by a capacitor. The ac [[Voltage Gain|voltage gain]] can be found by first finding the ac voltage at the base of the transistor (denoted with a lowercase $_b$). It is given by,
$$
V_{b}=I_{e}r_{e}'
$$
where $r_{e}'$ is the dynamic (meaning varying with time) ac [[Resistance|resistance]] of the transistor. The ac collector voltage is given by,
$$
V_{c}=I_{c}R_{C}
$$
However, since the ac currents $I_{c}$ and $I_{e}$ are approximately equal, we can substitute in $I_{e}$.
$$
V_{c}\approx I_{e}R_{C}
$$
Since voltage gain is the ratio of the output voltage to the input voltage,
$$
A_{v}=\frac{V_{c}}{V_{b}}
$$
we can substitute our expressions for voltage in.
$$
A_{v}\approx\frac{I_{e}R_{C}}{I_{e}r_{e}'}
$$
The $I_{e}$ terms cancel, leaving
$$
A_{v}\approx\frac{R_{C}}{r_{e}'}
$$
## Q-Point

The *q-point* (quiescent point) of a BJT amplifier circuit (also known as the dc operating point) is the [[Steady State|steady state]] dc voltage or current that allows the transistor to amplify a signal without hitting cutoff or saturation.

Suppose a $4\pu{ V}_{\pu{pp}}$ is sent through a BJT amplifier circuit with a gain of $A_{v}=3$. The output voltage can not be greater than the dc bias voltage, so if the transistor is only biased with $5\pu{ V}_{\pu{ DC}}$ then the signal will experience clipping as it hits the "rails" of the amplifier circuit.

The location of this q-point can be described graphically by the *dc load line*. This line is superimposed on the characteristic curves of $I_{C}$ vs $V_{CE}$ and it ranges from the saturation value where $I_{C}=I_{C(sat)}$ to the cutoff value where $V_{CE}=V_{CC}$. This load line is determined by the external circuit and not the transistor itself.
![[dc-load-line.png]]

The region along the load line from saturation to cutoff is generally known as the *linear region*. So long as the transistor is operated with values along this line, the output voltage is ideally a linear reproduction of the input. 

>[!QUESTION] Example
>```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{resistors/scale=0.75, batteries/scale=0.8}
\draw
(0,0) node[npn, anchor=B, scale=1](Q){}
to[R, l2_=$R_B$ and $10$k$\Omega$, l2 valign=b] ++(-2.5,0)
to[sV, l=$V_{in}$] ++(0,-2)
to[battery1, l2=$V_{BB}$ and $13$V] ++(0,-1.5)
node[ground](G){}
(Q.C) to[R, l2=$R_C$ and $220\Omega$, l2 halign=l] ++(0, 1.5)
-- ++(1,0) node[](A){}
to[battery, l2=$V_{CC}$ and $10$V] (G -| A) node[ground]{}
(Q.E) -- ++(0,-0.25) node[anchor=east]{$\beta_{DC}=100$} 
to[short] (G -| Q.E) node[ground]{}
;
\end{circuitikz}
\end{document}
>```
>Find the Q-point of the above circuit.
>$$
>\begin{aligned}
>I_{BQ}&=\frac{V_{BB}-0.7\pu{ V}}{R_{B}} &I_{CQ}&=\beta_{DC}I_{BQ}&V_{CE}&=V_{CC}-I_{CQ}R_{C}\\&=\frac{3.7\pu{ V}-0.7\pu{ V}}{10\pu{ k}\Omega}&&=(100)(300\mu\pu{ A})&&=10\pu{ V}-(30\pu{ mA})(220\Omega)\\&=300\mu\pu{ A}&&\boxed{=30\pu{ mA}}&&\boxed{=3.4\pu{ V}}\\
>\end{aligned}
>$$
>$\therefore \text{The circuit's Q-point is at }I_{CQ}=30\pu{ mA}\text{ and }V_{CE}=3.4\pu{ V}\text{.}$
>





 