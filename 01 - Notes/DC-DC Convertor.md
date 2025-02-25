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
# Boost convertor
A boost convertor, also known as a *step-up* convertor, is a dc-dc convertor that provides an output voltage that is higher than the input voltage.
## Sample circuit
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{diodes/scale=0.6}
\draw
(0,0) node[ocirc](in){} node[above]{$+V_\mathrm{in}$}
(0,-3) node[ocirc](out){} node[below]{$-V_\mathrm{in}$}

(in) to[short] ++(1,0) node[circ](A){} to[C, l=$C_1$] ++(0,-3) node[circ](C){} to[short] (out)

(A) to[L, l=$L_1$] ++(2.5,0) node[circ](B){}

(B) to[short] ++(0,-0.5) node[nigfete, bodydiode, anchor=D](Q){}
(Q) node[right=4mm]{$Q_1$}
(Q.G) node[ocirc]{} node[below]{G}

(Q.S) to[short] (Q.S |- C)

(B) to[diode, l=$D_1$] ++(2,0) node[circ](D){} to[short] ++(1,0) node[ocirc]{} node[above]{$+V_\mathrm{out}$}

(D) to[C, l=$C_2$] ++(0,-3) node[circ](E){} to[short] (C)

(E) to[short] ++(1,0) node[ocirc]{} node[below]{$-V_\mathrm{out}$}

;
\end{circuitikz}
\end{document}
```
This above sample boost convertor circuit is very similar to the sample buck convertor circuit above. The difference here is that the MOSFET is now where the diode was, the inductor is where the MOSFET was, and the diode is where the inductor was. It can be useful to try and analyze this circuit under two conditions: when the FET is energized and when the FET is de-energized.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{diodes/scale=0.6}
\draw
(0,0) node[ocirc](in){} node[above]{$+V_\mathrm{in}$}
(0,-3) node[ocirc](out){} node[below]{$-V_\mathrm{in}$}

(in) to[short] ++(1,0) node[circ](A){} to[C, l=$C_1$] ++(0,-3) node[circ](C){} to[short] (out)

(A) to[L, l=$L_1$] ++(2.5,0) node[circ](B){}

(B) to[short] (B |- C) node[circ]{}

(B) to[short] ++(0.25,0) node[ocirc]{} ++(1.5,0) node[ocirc]{} to[short] ++(0.25,0) node[circ](D){} to[short] ++(1,0) node[ocirc]{} node[above]{$+V_\mathrm{out}$}

(D) to[C, l=$C_2$] ++(0,-3) node[circ](E){} to[short] (C)

(E) to[short] ++(1,0) node[ocirc]{} node[below]{$-V_\mathrm{out}$}

;
\end{circuitikz}
\end{document}
```
When the FET is energized it behaves as a short. This shunts current away from the diode, essentially breaking the output from the input. During this phase, the inductor $L$ will store the energy from the source voltage. 
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{diodes/scale=0.6}
\draw
(0,0) node[ocirc](in){} node[above]{$+V_\mathrm{in}$}
(0,-3) node[ocirc](out){} node[below]{$-V_\mathrm{in}$}

(in) to[short] ++(1,0) node[circ](A){} to[C, l=$C_1$] ++(0,-3) node[circ](C){} to[short] (out)

(A) to[L, l=$L_1$] ++(2.5,0) node[](B){}

(B) to[short] ++(2,0) node[circ](D){} to[short] ++(1,0) node[ocirc]{} node[above]{$+V_\mathrm{out}$}

(D) to[C, l=$C_2$] ++(0,-3) node[circ](E){} to[short] (C)

(E) to[short] ++(1,0) node[ocirc]{} node[below]{$-V_\mathrm{out}$}

;
\end{circuitikz}
\end{document}
```
When the FET is de-energized, the branch with the FET is essentially removed from the circuit, and the diode is replaced with a short. This means that the output voltage is the input voltage *plus* the stored voltage from the inductor. 

In both phases the inductor is present and is cycling between storing and releasing [[Energy|energy]]. In the on-state, the current in this circuit will increase as the inductor stores energy. When the FET is de-energized, the inductor will try to maintain the same current by increasing its voltage, thus providing a higher output voltage. In this off-state, the current will decrease.

This switching current will, like the buck convertor, cause a ripple in the output current. Note that the *average* output current is determined by the load, but the ripple is determined by the components. The output voltage can be determined by analyzing this ripple. Recall that,
$$
V_{\text{L}}=L\ \frac{di}{dt}
$$
In the on-state, $V_{\text{L}}$ is effectively the same as the input voltage, $V_{\text{in}}$. The $di$ can be replaced by a $\Delta I$ representing the ripple current, and the $dt$ corresponds to the on-time of the gate driver circuit.
$$
V_{in}=L\ \frac{\Delta I}{t_{\ \text{on}}}
$$
Re-arranging for current,
$$
\Delta I = \frac{t_{\ \text{on}}}{L}V_{in}
$$
During the off-state, the voltage across the inductor will be the input voltage minus the output voltage, according to [[Kirchhoff’s Voltage Law|KVL]]. Our $\Delta I$ will be the negative of the on-state $\Delta I$ since in the off state we are now going from high-to-low current, whereas in the on-state we were going from low-to-high. Our $dt$ is now the off time of the gate driver circuit.
$$
V_{in}-V_{o}=L\ \frac{-\Delta I}{t_{\ \text{off}}}
$$
Rearranging for current,
$$
\Delta I=\frac{t_{\ \text{off}}}{L}(V_{o}-V_{in})
$$
Substituting our two equations for $\Delta I$ into one another we get,
$$
\begin{align}
\frac{t_{\ \text{on}}}{L}V_{in}&=\frac{t_{\ \text{off}}}{L}(V_{o}-V_{in}) \\
V_{in}\left( \frac{t_{on}+t_{off}}{L} \right)&=\frac{t_{off}}{L}V_{o} \\
V_{in}\left( \frac{T}{t_{off}} \right)&=V_{o} \\
V_{o}&=V_{in}\left(\frac{T}{T-t_{on}}\right) \\
&\boxed{=V_{in}\left(\frac{1}{1-D}\right)}
\end{align}
$$
where $D$ is the duty cycle. This means that, like the buck convertor, the output voltage is entirely dependent on the duty cycle of the FET gate driver. However, unlike the buck convertor, the output voltage is going to be greater than the input voltage, increasing with the duty cycle. However, this relationship practically only holds so long as $D<0.80$. If the duty cycle is greater than this value, the circuit does not have sufficient time to deliver the energy stored by the inductor, and the actual $V_{o}$ not longer matches the expected theoretical value.

At a duty cycle of around $75\%$, the output voltage is approximately $4$ times the input voltage. If we need the voltage to be more than $4$ times the input voltage, it would be better to use an [[Invertor|invertor]] circuit followed by a high-frequency [[Transformer|transformer]] to step up the voltage rather than a series of boost convertors, as these convertors will be more expensive and have more losses than a transformer.