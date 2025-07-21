---
tags:
  - electrical-engineering
  - circuit-analysis
---
A **first-order circuit** is an electrical circuit that can be described by a [[Ordinary Differential Equation#Linear differential equations of the first order|first order differential equation]]. These circuits can take the form of RC or RL. These circuits can also be energized by the energy stored in the [[Capacitor|capacitors]] or [[Inductor|inductors]] *or* they can be energized by an [[Voltage Sources|independent source]] (referred to as *source free* and *sourced*, respectively). Putting these combinations together there are four types of first-order circuits.
# Source free RC
A source free RC circuit occurs when a dc source is suddenly disconnected. The [[Energy|energy]] stored in the capacitor is then released to the [[Resistor|resistor]].
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[cC, l=$C$, v<=$v_c$] ++(0,-3)
;
\end{circuitikz}
\end{document}
```