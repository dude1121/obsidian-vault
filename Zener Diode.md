---
tags:
  - electronics
  - electromagnetism
  - physics
  - circuit-analysis
---
The **zener diode** is a special type of [[Diode|diode]] that is designed to operate in reverse breakdown. 
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[full ZZener diode, o-o] (4,0)
;
\end{circuitikz}
\end{document}
```

Zener diodes are constructed to have a certain value of reverse [[Voltage|voltage]] at which they will begin to conduct. This can make zener diodes useful in applications like voltage references. Once this value is reached, the [[current]] through the diode increases but the voltage across the diode will barely change. 

# Construction

Much like normal diodes, a zener diode consists of a [[PN Junction]]. However, a zener diode's pn junction is more carefully doped so as to set the reverse voltage level as precisely as possible.

# Models

## Ideal Model

In the ideal zener diode model, the diode is modelled simply as an opposing voltage source, with no internal [[resistance]]. 