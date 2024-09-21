---
tags:
  - electromagnetism
  - physics
  - circuit-analysis
---
A **full wave rectifier** is a [[Rectifier|rectifier]] circuit that converts the entire [[AC Electricity|ac waveform]] into a steady   [[DC Electricity|dc signal]].
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[sinusoidal voltage source] (0, 4)
to[short] (3,4)
to[L] (3,0)
to[short] (0,0)

(4, 4) to[L, name=1] (4,0) node[circle, fill=red, inner sep=1pt] at(1.midtap){} 
;
\end{circuitikz}
\end{document}
```
