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

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[battery, invert] (0,4)
to[zzD*, invert,  l=\Large$D$, bipoles/length=1cm, -o] (3,4)
(0,0) to[R, -o] (3,0)

(4,2) node[]{\Large$=$}

(5,0) to[battery, invert] (5,4)
to[battery1, l=\Large$D$, -o] (8,4)
(5,0) to [R, -o] (8,0)
;
\end{circuitikz}
\end{document}
```

## Practical Model

In practice, however, there is some resistance in the zener diode.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[battery, invert] (0,4)
to[zzD*, invert, bipoles/length=1cm, -o] (3,4)
(0,0) to[R, -o] (3,0)

(1.75, 5) node[]{\Large$D$}

(4,2) node[]{\Large$=$}

(5,0) to[battery, invert] (5,4)
to[R, l=$Z_Z$] (7,4)
to[battery1, -o] (8,4)
(5,0) to [R, -o] (8,0)

(6.75, 5) node[]{\Large$D$}
;
\end{circuitikz}
\end{document}
```
