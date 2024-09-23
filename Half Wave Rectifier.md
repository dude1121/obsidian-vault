---
tags:
  - electromagnetism
  - physics
  - circuit-analysis
---
A **Half wave rectifier** is a type of [[Rectifier|rectifier]] circuit that converts half of an [[AC Electricity|ac signal]] into a [[DC Electricity|dc signal]]. It can be constructed with a single diode.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,-3) to[sinusoidal voltage source] (0,0)
to[short] (2,0)
to[L] (2,-3)
to[short] (0,-3)

(2.75,-3) to[L] (2.75,0)
to[diode, bipoles/length=1cm] (3.9,0) to[short, -o] (4,0)
(2.75,-3) to[short, -o] (4,-3)
;
\end{circuitikz}
\end{document}
```

In this circuit above, since the diode will only allow current flow in one direction, the output voltage will only be half of the ac signal. The peak voltage of the output signal will also be approximately $0.7\pu{ V}$ less than the input peak voltage, since there will be a voltage drop across the diode of $V_{F}$.
![[half-wave-waveform.png]]
