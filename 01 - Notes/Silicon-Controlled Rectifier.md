---
tags:
  - physics
  - electrical-engineering
  - electronics
---
A **silicon-controlled rectifier** or **SCR** is a [[Thyristor|thyristor]] that behaves as a [[Diode|diode]] (complete with an anode and cathode) with a gate terminal to control conduction.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[left] {A} to[full thyristor, n=TRI] (3,0) node[right] {K}
(TRI.G) node[above] {G}
;
\end{circuitikz}
\end{document}
```
SCRs are used in high [[Voltage|voltage]] and high [[Current|current]] switching applications, but crucially these applications must be *low [[Frequency|frequency]]*. An SCR can be represented as a *pnpn* junction, with the gate connected to a *p-type* section.
![[scr.png]]
The current through the SCR $I_{\text{AK}}$ can be controlled by a relatively low-current "control" signal current $I_{\text{G}}$. To "turn on" the SCR, it must be *forward biased*, i.e., $V_{\text{A}}>V_{\text{K}}$ and $V_{\text{G}}>V_{\text{K}}$. This is a very important concept, as the cathode voltage may not necessarily be at ground potential. The designer must take into consideration what potential $V_{\text{K}}$ will be at and design a [[Driver Circuit|driver circuit]] to achieve a proper gate voltage. 

The current at the gate will lower the barrier voltage required to allow the SCR to conduct. Conversely, if the gate voltage is negative with respect to the cathode, the barrier voltage *increases*. When this barrier voltage is reached, the voltage $V_{\text{AK}}$ will dramatically drop as it enters conduction. Once it enters conduction, the only way to "turn off" the SCR, the polarity across the device must be reversed and the current $I_{\text{AK}}$ must drop below the *holding current* $I_{\text{H}}$, which is the minimum current the device can operate in when first entering conduction. It is not sufficient to remove the gate voltage to turn off the device.
![[scr-performance-plot.png]]
# Parameters
Common datasheet values for SCRs are defined as,
- *Forward-breakover voltage* $V_{\text{BR(F)}}$. This is the voltage at which the SCR enters conduction. This value is maximum when $I_{\text{G}}=0\pu{ A}$ and it is designated as $V_{\text{BR(F0)}}$. 
- *Holding current* $I_{\text{H}}$. This is the value of anode current $I_{\text{AK}}$ below which the SCR switches from forward-conduction to the forward-blocking region. This value increases with decreasing values of $I_{\text{G}}$ and is maximum for $I_{\text{G}}=0\pu{ A}$.
- *Gate trigger current* $I_{\text{GT}}$. This is the value of gate current necessary to switch the SCR from the forward-blocking region to the forward-conduction region under specified conditions.
- *Average forward current* $I_{\text{F(avg)}}$ or $I_{\text{T}}$. This is the maximum continuous anode current that the device can withstand in the conduction state under specified conditions.
- *Forward-conduction region*. This region corresponds to the *on* condition of the SCR where there is forward current from anode to cathode through the very low [[Resistance|resistance]] of the SCR.
- *Reverse-breakdown voltage* $V_{\text{BR(R)}}$ or $V_{\text{DRM}}$. This is the value of reverse voltage from cathode to anode at which the device breaks into the avalanche region and begins to conduct heavily. 
- *On-state voltage* $V_{\text{T}}$. This is voltage across the SCR from anode to cathode when it is conducting. Ideally this parameter should be as low as feasibly and financially possible.
Note when making design choices for any component including SCRs, a safety margin of $2-3$ times the design value should be used.
# SCR Gate Driver
In order to properly use an SCR, we need an additional [[Driver Circuit|driver circuit]] for the gate terminal to control timings for applications like a thyristor controlled [[Rectifier#Controlling the output voltage|rectifier]]. Consider the following circuit:
```tikz
\usepackage{circuitikz}
\tikzset{tbulb/.style={cute inductor,n=aux,append after command={(aux)
       node[draw,circle,inner  sep=.35cm]{}}}}
\begin{document}
\begin{circuitikz}
\draw
(0,2) node[ocirc](AC1){} node[left]{$AC1$}
(0,0) node[ocirc](AC2){} node[left]{$AC2$}

(AC1) to[short] ++(2,0) node[circ](T1A){}
(T1A) to[thyristor, l=$T_1$, mirror, n=T1] ++(0,2.5) node[](T1K){}
(T1.G) node[ocirc]{} node[right]{$G_1$}

(AC2) to[short] ++(5,0) node[circ](T2A){} to[short] ++(0,2)
to[thyristor, l=$T_2$, mirror, n=T2] ++(0,2.5) node[circ](T2K){}
(T2.G) node[ocirc]{} node[right]{$G_2$}

(T1K) to[short] (T2K)

(T1A) to[short] ++(0,-2) to[thyristor,l_=$T_3$, invert, n=T3] ++(0,-3) node[](T3K){}
(T3.G) node[ocirc]{} node[right]{$G_3$}

(T2A) to[thyristor,l_=$T_4$, invert, n=T4] ++(0,-3) node[circ](T4K){} node[ground]{}
(T4.G) node[ocirc]{} node[right]{$G_4$}

(T3K) to[short] (T4K)

(T2K) to[short] ++(2,0) node[ocirc](O1){} node[right]{$R_\mathrm{PP}$}
(T4K) to[short] ++(2,0) node[ocirc](O2){} node[right]{$R_\mathrm{PN}$}

(O1) to[tbulb] (O2)
;
\end{circuitikz}
\end{document}
```
In order for the SCRs to conduct the following conditions must be met:
	For all:
		- $V_{\text{GK}}>$ Threshold
	For $T_{1}$ and $T_{2}$:
		- $V_{\text{G}}>V_{\text{RPP}}$
	For $T_{3}$:
		- $V_{\text{G3}}>V_{\text{AC1}}$
	For $T_{4}$:
		- $V_{\text{G4}}>V_{\text{AC2}}$
There are therefore different reference points that need to be kept in mind, and SCRs $T_{1}$ & $T_{4}$ must have a different timing than $T_{2}$ & $T_{3}$. The solution to this is a [[Pulse Transformer|pulse transformer]].
## Sample driver circuit
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[
	longL/.style = {cute inductor, inductors/scale=0.75, inductors/width=4, inductors/coils=25}]
\draw
(0,0) node[ocirc]{} node[left]{$R_\mathrm{PP}$} to[short] ++(1,0)
node[circ](A){} to[R, a=$5\mathrm{k}\Omega$] ++(0,-2)
node[circ](B){}
to[short] ++(-1,0) node[ocirc]{} node[left]{$G_1$}
(B) to[R, a=$510\Omega$] ++(2,0) to[cute inductor, l=$S_2$, mirror] ++(0,2) to[short] (A)

(0,-3) node[ocirc]{} node[left]{$AC2$} to[short] ++(1,0)
node[circ](C){} to[R, a=$5\mathrm{k}\Omega$] ++(0,-2)
node[circ](D){}
to[short] ++(-1,0) node[ocirc]{} node[left]{$G_4$}
(D) to[R, a=$510\Omega$] ++(2,0) node[](TS){} to[cute inductor, l=$S_1$, mirror] ++(0,2) to[short] (C)

(TS) to[open] ++(1,0) node[](TP2){} to[longL, l=$P$] ++(0,5) node[](TP1){}

(TP1) to[short] ++(2,0) to[short] ++(0,-2) node[npn, anchor=C, xscale=-1](Q1){\ctikzflipx{$Q_1$}}
(Q1.E) to[short] (Q1.E |- TP2) node[ground](G){}
(TP2) to[short] (G)

(Q1.B) to[short] ++(0.5,0) node[circ](E){} to[R, a=$1\mathrm{k}\Omega$] ++(2,0) to[short] ++(1,0) node[ocirc]{} node[right]{$GP$}
(E) to[R, a=$5\mathrm{k}\Omega$] ++(0,-2) node[](F){} to[short] (F -| G) node[circ]{}
;
\end{circuitikz}
\end{document}
```
