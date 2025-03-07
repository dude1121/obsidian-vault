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

All types of convertors contain a MOSFET which is switched rapidly by a PWM signal on its gate (controlled by a [[Convertor Driver Circuit|driver circuit]]), an inductor that stores and releases energy, a flyback diode to guide the current and allow the inductor to release energy safely, and capacitors to smooth the voltage ripples. The amount of current ripple caused by the inductor, denoted below as $\Delta I$, varies inversely with the inductance of the inductor. That is, $\uparrow L, \downarrow \Delta I$.
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
where $D$ is the duty cycle. This means that, like the buck convertor, the output voltage is entirely dependent on the duty cycle of the FET gate driver. However, unlike the buck convertor, the output voltage is going to be greater than the input voltage, increasing with the duty cycle. However, this relationship practically only holds so long as $D<75\%$. If the duty cycle is greater than this value, the circuit does not have sufficient time to deliver the energy stored by the inductor, and the actual $V_{o}$ not longer matches the expected theoretical value.

At a duty cycle of around $80\%$, the output voltage is approximately $4$ times the input voltage. If we need the voltage to be more than $4$ times the input voltage, it would be better to use an [[Invertor|invertor]] circuit followed by a high-frequency [[Transformer|transformer]] to step up the voltage rather than a series of boost convertors, as these convertors will be more expensive and have more losses than a transformer.
# Buck-Boost
A buck-boost convertor, otherwise known as a *step-up / step-down* convertor, is a dc-dc convertor that can either step up or step down dc voltage.
## Sample circuit
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{diodes/scale=0.6}
\draw
(0,0) node[ocirc](in){} node[above]{$+V_\mathrm{in}$} to[short] ++(1,0) node[circ](B){}
(0,-3) node[ocirc](out){} node[below]{$-V_\mathrm{in}$} to[short] ++(1,0) node[circ](C){}

(B) to[cC, l=$C_1$] (C)

node[nigfete, bodydiode, anchor=D, rotate=90](Q){} node[xshift=14mm, yshift=-5mm]{$Q$}
(Q.G) node[ocirc]{} node[below]{G}
(Q.S) node[circ](G){} to[L, l_=$L_1$, mirror] (Q.S |- B) node[circ](D){}
(Q.S) to[diode, l=$D_1$] ++(2,0) node[circ](E){}
(B) to[short] (D)
(D) to[short] (D -| E) node[circ](F){}

(F) to[cC, l=$C_2$] (E) 

(F) to[short] ++(1,0) node[ocirc]{} node[above]{$-V_\mathrm{out}$}
(E) to[short] ++(1,0) node[ocirc]{} node[below]{$+V_\mathrm{out}$}

;
\end{circuitikz}
\end{document}
```
A sample buck-boost convertor circuit is shown above. Unlike the individual boost and buck convertors, buck-boost convertors **do not share a common ground**. The polarity of the output voltage is inverted from the input voltage. We can analyze this circuit in a similar way to the above convertors, by analyzing it when the MOSFET is on and when it is off.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{diodes/scale=0.6}
\draw
(0,0) node[ocirc](in){} node[above]{$+V_\mathrm{in}$} to[short] ++(1,0) node[circ](B){}
(0,-3) node[ocirc](out){} node[below]{$-V_\mathrm{in}$} to[short] ++(1,0) node[circ](C){}

(B) to[cC, l=$C_1$] (C)
to[short] ++(2,0) node[circ](G){}
(G) to[L, l_=$L_1$, mirror] (G |- B) node[circ](D){}
(G) to[open] ++(2,0) node[circ](E){}
(B) to[short] (D)
(D) to[short] (D -| E) node[circ](F){}

(F) to[cC, l=$C_2$] (E) 

(F) to[short] ++(1,0) node[ocirc]{} node[above]{$-V_\mathrm{out}$}
(E) to[short] ++(1,0) node[ocirc]{} node[below]{$+V_\mathrm{out}$}

;
\end{circuitikz}
\end{document}
```
When the MOSFET is triggered on, we can model it as a short. This shorts out the diode which we model as an open. This means that when the MOSFET is on, the inductor is storing energy. The on-time ripple current caused by the inductor is the same as the boost convertor,
$$
\Delta I = \frac{t_{on}}{L}V_{in}
$$

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{diodes/scale=0.6}
\draw
(0,0) node[ocirc](in){} node[above]{$+V_\mathrm{in}$} to[short] ++(1,0) node[circ](B){}
(0,-3) node[ocirc](out){} node[below]{$-V_\mathrm{in}$} to[short] ++(1,0) node[circ](C){}

(B) to[cC, l=$C_1$] (C)
to[open] ++(2,0) node[circ](G){}
(G) to[L, l_=$L_1$, mirror] (G |- B) node[circ](D){}
(G) to[short] ++(2,0) node[circ](E){}
(B) to[short] (D)
(D) to[short] (D -| E) node[circ](F){}

(F) to[cC, l=$C_2$] (E) 

(F) to[short] ++(1,0) node[ocirc]{} node[above]{$-V_\mathrm{out}$}
(E) to[short] ++(1,0) node[ocirc]{} node[below]{$+V_\mathrm{out}$}

;
\end{circuitikz}
\end{document}
```
In the off case, the inductor is able to discharge. This will cause an opposite polarity voltage to be induced across the output terminals. The voltage across the inductor therefore $-V_{o}$. For reasons stated above, our $\Delta I$ is now $I_{min}-I_{max}$. Therefore,
$$
\Delta I=\frac{t_{off}}{L}V_{o}
$$
We can combine these two states to get,
$$
\begin{align}
\frac{t_{on}}{L}V_{in}&=\frac{t_{off}}{L}V_{o} \\
t_{on}V_{in}&=t_{off}V_{o} \\
V_{o}&=\frac{t_{on}}{t_{off}}V_{in} \\
&=\frac{t_{on}}{T-t_{on}}V_{in} \\
&\boxed{=\frac{D}{1-D}V_{in}}
\end{align}
$$
Therefore we can determine our output voltage solely by the duty cycle of the MOSFET gate driver, as seen above. If the duty cycle $D>50\%$, this operates as a boost convertor. That is, when $D>50\%$, $V_{o}>V_{in}$. If $D<50\%$, then $V_{o}<V_{in}$. This corresponds to whether or not the inductor is primarily storing or delivering energy.

Just like the boost convertor, the duty cycle should in principle be restricted to $D<80\%$. Any higher than this limit can cause damage to the circuit.
# Convertors with no diode
In each of these convertors, we can replace the diode with a second MOSFET. Since each MOSFET has a body diode, this component will behave exactly the same as the diode. The FET also has less losses than a normal diode.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[vsource, l=$V_s$] ++(0,-3)
(0,0) to[short] ++(2,0) node[circ](A){}
(0,-3) to[short] ++(2,0) node[circ](B){}

(A) to[cC, l=$C_1$] (B) node[below=5mm, xshift=15mm]{Buck Convertor Equivalent}

(A) to[short] ++(3,0) node[nigfete, anchor=D, bodydiode](Q1){} node[right=3mm, yshift=-5mm]{$Q_1$}

(Q1.G) node[ocirc]{} node[left]{$G_1$}
(Q1.S) node[circ](C){} node[nigfete, bodydiode, anchor=D](Q2){} node[right=3mm, yshift=-5mm]{$Q_2$}

(Q2.G) node[ocirc]{} node[left]{$G_2$}
(Q2.S) to[short] (Q2.S |- B) node[circ](D){}

(C) to[L, l=$L_1$] ++(2,0) node[circ](E){} to[cC, l=$C_2$] (E |- B) node[circ](F){}  to[short] (B)

(E) to[short] ++(1,0) node[ocirc]{} node[above]{$+V_{\mathrm{out}}$}
(F) to[short] ++(1,0) node[ocirc]{} node[below]{$-V_{\mathrm{out}}$}
;
\end{circuitikz}
\end{document}
```
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[vsource, l=$V_s$] ++(0,-2)
(0,0) to[short] ++(2,0) node[circ](A){}
(0,-2) to[short] ++(2,0) node[circ](B){}

(A) to[cC, l=$C_1$] (B) node[below=5mm, xshift=15mm]{Boost Convertor Equivalent}

(A) to[L, l_=$L_1$] ++(3,0) node[circ](C){} to[short] ++(0,0.5) node[nigfete, anchor=S, bodydiode](Q1){} node[right=3mm, yshift=5mm]{$Q_1$}

(Q1.G) node[ocirc]{} node[left]{$G_1$}
(Q1.D) to[short] ++(2,0) node[circ](E){} 

(C) node[nigfete, bodydiode, anchor=D](Q2){} node[right=3mm, yshift=-5mm]{$Q_2$}

(Q2.G) node[ocirc]{} node[left]{$G_2$}
(Q2.S) to[short] (Q2.S |- B) node[circ](D){}

(E) to[cC, l=$C_2$] (E |- B) node[circ](F){}  to[short] (B)

(E) to[short] ++(1,0) node[ocirc]{} node[above]{$+V_{\mathrm{out}}$}
(F) to[short] ++(1,0) node[ocirc]{} node[below]{$-V_{\mathrm{out}}$}
;
\end{circuitikz}
\end{document}
```
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[ocirc]{} node[above]{$+V_{\mathrm{out}}$} to[short] ++(3,0) node[circ](A){} to[cC, l=$C_1$] ++(0,-2) node[circ](B){} to[short] ++(-2,0) node[circ](C){} to[short] ++(-1,0) node[ocirc]{} node[below]{$-V_{\mathrm{out}}$}

(C) to[vsource, l=$V_s$] ++(0,-2) node[](E){}

(A) to[short] ++(3,0) node[nigfete, bodydiode, anchor=D](Q1){} node[right=3mm, yshift=-5mm]{$Q_1$}
(Q1.G) node[ocirc]{} node[left]{$G_1$}
(Q1.S) to[short] (Q1.S |- B) node[circ](D){} node[nigfete, bodydiode, anchor=D](Q2){} node[right=3mm, yshift=-5mm]{$Q_2$}
(Q2.G) node[ocirc]{} node[left]{$G_2$}
(Q2.S) to[short] (Q2.E |- E) node[ground]{} to[short] (E)

(B) to[L, l=$L_1$] (D)
(B) to[cC, l=$C_2$] node[circ]{} (B |- E) node[below=5mm, xshift=5mm]{Buck-Boost Equivalent}
;
\end{circuitikz}
\end{document}
```
We can create a generalized circuit that can behave as either type of convertor. This is called a *[[Half-Bridge Circuit|half-bridge]]* circuit. It looks like this:
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[circ]{} node[above]{$V_H$} to[short] ++(1,0) node[circ](A){} to[short] ++(3,0) node[nigfete, bodydiode, anchor=D](Q1){} node[right=3mm, yshift=-5mm]{$Q_1$}
(Q1.G) node[ocirc]{} node[left]{$G_1$}
(Q1.S) to[short] ++(0,-1) node[circ](B){} to[short] ++(-.5,0) node[circ]{} node[left]{M}
(B) node[nigfete, bodydiode, anchor=D](Q2){} node[right=3mm, yshift=-5mm]{$Q_2$}
(Q2.G) node[ocirc]{} node[left]{$G_2$}
(Q2.S) to[short] ++(0,-0.5) node[circ](G){} node[ground]{}
(A) to[cC, l=$C_1$] (A |- G) to[short] (G)

(B) to[L, l=$L_1$] ++(3,0) node[circ](D){} to[short] ++(1,0) node[circ]{} node[above]{$V_L$}

(D) to[cC, l=$C_2$] (D |- G) to[short] (G)

;
\end{circuitikz}
\end{document}
```
Whether this behaves as a buck or boost convertor depends on which point you consider the input or output. If $V_{H}$ is the input, then the output is $V_{L}$, making this a buck convertor. In any case the two nodes share this relationship:
$$
V_{L}=D\cdot V_{H}
$$
where $D$ is the 'high-side' duty cycle of the MOSFETs. The output voltage is determined according to the table below.

| Convertor Type | Output Voltage                            | Input   | Output        |
| -------------- | ----------------------------------------- | ------- | ------------- |
| Buck           | $V_{o}=D\cdot V_{in}$                     | $V_{H}$ | $V_{L}$       |
| Boost          | $\displaystyle V_{o}=\frac{1}{D}V_{in}$   | $V_{L}$ | $V_{H}$       |
| Buck-Boost     | $\displaystyle V_{o}=\frac{1-D}{D}V_{in}$ | $V_{L}$ | $V_{H}-V_{L}$ |
