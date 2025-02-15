---
tags:
  - electrical-engineering
  - electronics
---
A **dc-dc convertor** is a circuit that can step up or step down [[DC Electricity|dc]] [[Voltage|voltage]]. Technically speaking, the convertor is the dc equivalent of a [[Transformer|transformer]]. Dc-dc convertors are typically used in [[Switch-mode Power Supply|switch-mode power supplies]] since they have fewer losses than [[Voltage Regulator|voltage regulator]] ICs. 

Like their ac counterpart, dc-dc convertors have (ideally) the same input power as the output power. That is,
$$
P_{\ \text{in}}=P_{\ \text{out}}
$$
In reality of course there will be losses in the conversion process. The average efficiency is around $90\%$, meaning $10\%$ of the input power is lost. The type of dc-dc convertor varies depending on the output voltage value compared to the input.

| Voltage Status                                                           | Designation          |
| ------------------------------------------------------------------------ | -------------------- |
| $V_{\ \text{in}}>V_{\ \text{out}}$                                       | Buck Convertor       |
| $V_{\ \text{in}}<V_{\ \text{out}}$                                       | Boost Convertor      |
| $V_{\ \text{in}}>V_{\ \text{out}}$ or $V_{\ \text{in}}<V_{\ \text{out}}$ | Buck-Boost Convertor |

# Overview of design
![[dc-dc-overview.png]]
Any dc-dc convertor can be broken down into three main components: the *power section*, consisting of the convertor itself; the *gate driver*, a supplementary circuit that will energize the gate of the switching components; and the *PWM control*, a circuit that times the gate circuit using [[Pulse Width Modulation|pulse width modulation]]. This final part is typically done via software. 
# Buck convertor
A buck convertor, also known as a *step-down* convertor, is a dc-dc convertor that provides an output voltage that is lower than the input voltage.
## Sample circuit
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{diodes/scale=0.6}
\draw
(0,0) node[ocirc](in){} node[above]{$+V_\mathrm{in}$}
(0,-3) node[ocirc](out){} node[below]{$-V_\mathrm{in}$}

(in) to[short] ++(1,0) node[circ](A){} to[C, l=$C_1$] ++(0,-3) node[circ]{} to[short] (out)

(A) to[short] ++(0.5,0) node[nigfete, bodydiode, anchor=D, rotate=90](Q){}
(Q) node[above=4mm]{$Q_1$}
(Q.G) node[ocirc]{} node[below]{G}

(Q.S) to[short] ++(0.5,0) node[circ](B){} to[diode, invert, l=$D_1$] ++(0,-3) node[circ](C){} to[short] (C -| A)

(B) to[L, l=$L_1$] ++(2,0) node[circ](D){} to[short] ++(1,0) node[ocirc]{} node[above]{$+V_\mathrm{out}$}

(D) to[C, l=$C_2$] ++(0,-3) node[circ](E){} to[short] (C)

(E) to[short] ++(1,0) node[ocirc]{} node[below]{$-V_\mathrm{out}$}

;
\end{circuitikz}
\end{document}
```
The above circuit is a simple buck convertor circuit. The [[Inductor|inductor]] plays a major role in this circuit. When the [[Metal Oxide-Semiconductor Field Effect Transistor|MOSFET]] is triggered on, the inductor is charged by the source voltage $V_{\ \text{in}}$. When the FET's gate signal is pulled low, the circuit simplifies to just $L_{1}$, $C_{2}$, and $D_{1}$. The inductor will discharge through the [[Capacitor|capacitor]] and the [[Diode|diode]], slightly reducing the current until the FET is triggered on again. This creates a ripple in the output current, this ripple $\Delta I$ is determined by the [[Inductance|inductance]] of the inductor. It can be determined by,
$$
\Delta I=\frac{t_{\ \text{on}}}{L}(V_{\ \text{in}}-V_{\ \text{o}})
$$
which is itself a re-arrangement of,
$$
V_{\ \text{L}}=L \frac{di}{dt}
$$
We can use the off time to find a similar expression for the ripple current:
$$
\Delta I=\frac{t_{\ \text{off}}V_{\ \text{o}}}{L}
$$
We can combine these relationships to find the given expression:
$$
V_{\ \text{o}}=\frac{t_{\ \text{on}}}{T}V_{\ \text{in}}=DV_{\ \text{in}}
$$
where $D$ is the [[Duty Cycle|duty cycle]] of the gate driver circuit. This means that the output voltage is determined solely by the duty cycle.  