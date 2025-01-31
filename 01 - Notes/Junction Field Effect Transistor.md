---
tags:
  - physics
  - semiconductors
  - electrical-engineering
  - electronics
---
A **junction field effect transistor** or **JFET** is a type of [[Field Effect Transistor|field effect transistor]]. It differs from the [[Metal Oxide-Semiconductor Field Effect Transistor|MOSFET]] in that as a gate voltage is applied to the FET the conduction channel *narrows* whereas in a MOSFET this channel *widens* as a gate voltage is applied. This functionally means that MOSFETs and JFETs operate opposite to one another; JFETs conduct when there is no gate voltage and get less [[Conductivity|conductive]] as more voltage is applied whereas MOSFETs do not conduct until the gate voltage reaches some threshold voltage after which the conductivity *increases* with gate voltage.

Like most transistors, there are two types of JFETs: *n*-channel or *p*-channel. This distinction refers to which type of [[Semiconductor Doping|doped semiconductor]] forms the conduction channel.
![[jfet-types.png]]
The JFET always operates with the gate-source [[PN Junction|pn junction]] reverse biased. This means that a JFET is a normally on device, and an applied gate voltage will cause the JFET to become less conductive until it turns off entirely.
# Drain characteristic curve
Consider a JFET that has its gate and source shorted as in the circuit below.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
	(0,0) node[njfet, anchor=G](Q){}
	(Q.G) to[short] ++(-1,0) to[short] ++(0,-1) node[ground](G){}
	(Q.D) to[short] ++(0,0.5) to[R, l=$R_\mathrm{D}$] ++(3,0)
		node[](A){}
		to[battery, l=$V_\mathrm{DD}$] (A |- G) node[ground]{}

	(Q.S) to[short] (Q.S |- G) node[ground]{}
;
\end{circuitikz}
\end{document}
```
As $V_{\text{DD}}$ is increased (and thus $V_{\text{DS}}$), $I_{\ \text{D}}$ increases proportionally, as shown in the plot below between points A and B.
![[drain-characteristic-curve.png]]
This region is known as the *ohmic region* because throughout this region the JFET has an essentially constant [[Resistance|resistance]]. 