---
tags:
  - electrical-engineering
  - circuit-analysis
---
A **first-order circuit** is an electrical circuit that can be described by a [[Ordinary Differential Equation#Linear differential equations of the first order|first order differential equation]]. These circuits can take the form of RC or RL. These circuits can also be energized by the energy stored in the [[Capacitor|capacitors]] or [[Inductor|inductors]] *or* they can be energized by an [[Voltage Sources|independent source]] (referred to as *source free* and *sourced*, respectively). Putting these combinations together there are four types of first-order circuits.
# Source free RC
A source free RC circuit occurs when a dc source is suddenly disconnected. The [[Energy|energy]] stored in the capacitor is then released to the [[Resistor|resistor]].[^1]
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[cC, l_=$C$, i=$i_C$] ++(0,-3) to[short] ++(1.5,0) node[](B){} to[short] ++(1.5,0)
(0,0) to[short] ++(1.5,0) node[ocirc](A){} node[above]{$a$} to[short] ++(1.5,0) to[R, l=$R$, i=$i_R$] ++(0,-3)
(A) to[open, v<=$v$] (B)
(B) node[circ]{} node[ground]{}
;
\end{circuitikz}
\end{document}
```
Since the capacitor is initially charged, we can assume that at $t=0$ the initial voltage is
$$
v(0)=V_{0}
$$
The initial energy in the capacitor is
$$
w(0)=\frac{1}{2}CV_{0}^2
$$
If we apply [[Kirchhoff's Current Law|KCL]] at node $a$,
$$
i_{C}+i_{R}=0\ \mathrm{A}
$$
By definition, $i_{C}=C\ dv/dt$ and $i_{R}=v/R$. Thus,
$$
C\ \frac{dv}{dt}+ \frac{v}{R}=0
$$
or,
$$
\frac{dv}{dt}+\frac{v}{RC}=0
$$
This is the first order differential equation for this circuit. Solving it for $v(t)$ yields,
$$
v(t)=V_{0}e^{-t/RC}
$$
Therefore the voltage response of the RC circuit is an [[Exponential Function|exponential]] decay of the initial voltage. Since this response is due to the initial energy stored and the physical characteristics of the circuit and not due to some external voltage or current source, this is called the circuit's *natural response*.

We can define the [[Time Constant|time constant]] $\tau$ to be
$$
\tau=RC
$$
making the expression for voltage,
$$
\boxed{v(t)=V_{0}e^{-t/\tau}}
$$
A related expression for the current can be derived via [[Ohm's Law]].
$$
i(t)=\frac{V_{0}}{R}e^{-t/\tau}
$$
As well as the power dissipated by the resistor,
$$
p_{R}(t)=\frac{V_{0}^2}{R}e^{-2t/\tau}
$$
And finally the energy absorbed by the resistor.
$$
w_{R}(t)=\frac{1}{2}CV_{0}^2(1-e^{-2t/\tau})
$$
# Source free RL
A source free RL circuit also occurs when a source is suddenly disconnected, but as its name implies it consists of an [[Inductor|inductor]] and resistor with no capacitive element.[^2]
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[L, l=$L$, v=$v_L$] ++(0,-3) to[short] ++(1.5,0) node[](B){} to[short] ++(1.5,0)
(0,0) to[short, i=$i$] ++(1.5,0) node[ocirc](A){} node[below]{$a$} to[short, i=$i$] ++(1.5,0) to[R, l=$R$, v<=$v_R$] ++(0,-3)
(B) node[circ]{} node[ground]{}
;
\end{circuitikz}
\end{document}
```
In a source free RL circuit the important response to determine is the current through the inductor, $i(t)$. At $t=0$ we assume that inductor has an initial current $I_{0}$, or in other words,
$$
i(0)=I_{0}
$$
The energy stored in the inductor is therefore,
$$
w(0)=\frac{1}{2}LI_{0}^2
$$
Applying [[Kirchhoff’s Voltage Law|KVL]] around the circuit we get that,
$$
v_{L} + v_{R}=0
$$
But $v_{L}=L di/dt$ and $v_{R}=iR$. Therefore,
$$
L \frac{di}{dt} + Ri = 0
$$
or,
$$
\frac{di}{dt}+\frac{R}{L}i=0
$$
This is the first order differential equation for this circuit. Solving it for $i(t)$ yields,
$$
i(t)=I_{0}e^{-Rt/L}
$$
But the time constant $\tau$ for a RL circuit is
$$
\tau=\frac{L}{R}
$$
therefore we can write the solution as,
$$
\boxed{i(t)=I_{0}e^{-t/\tau}}
$$
The voltage across the resistor can be found using Ohm's Law.
$$
v_{R}(t)=I_{0}Re^{-t/\tau}
$$
And the power dissipated by the resistor,
$$
p_{R}(t)=I_{0}^2Re^{-2t/\tau}
$$
Finally, the energy absorbed by the resistor.
$$
w_{R}(t)=\frac{1}{2}LI_{0}^2(1-e^{-2t/\tau})
$$
# Step response of an RC circuit
When a dc source is suddenly applied to an RC circuit

[^1]: Note that this need not be 1 discrete capacitor and 1 discrete resistor but could also be an equivalent of numerous components.

[^2]: Similar note as source free RC but for inductors and resistors.
