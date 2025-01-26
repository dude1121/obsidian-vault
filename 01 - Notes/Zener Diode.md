---
tags:
  - electronics
  - electromagnetism
  - physics
  - semiconductors
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

In practice, however, there is some [[Impedance|impedance]] in the zener diode.

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

This impedance is dynamic and depends on the [[Derivative|rate of change]] of the zener voltage with respect to the zener current. 
$$
Z_{Z}=\frac{dV_{Z}}{dI_{Z}}
$$
# Datasheet Attributes

The *temperature coefficient* $TC$ of a zener diode is the rate of change of the zener voltage $V_{Z}$ with respect to temperature $T$.
$$
TC=\frac{dV_{Z}}{dT}
$$
# Applications

In low current circuits, a zener diode can be used as a voltage reference, where the load is put in parallel with a zener diode with a known zener voltage. 

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) node[vcc](VCC){\Large$V_{CC}$}
to[short] ++(0,-1)
to[R] ++(3,0) node[circ](A){}
to[zzD*, bipoles/length=1cm, v<=\Large$V_Z$, voltage shift=4] ++(0,-3)
node[ground]{}
(A) to[short] ++(1,0) node[ocirc]{}
to[R, v^<=\Large$V_L$, voltage shift=2] ++(0,-3) node[ground]{}
;
\end{circuitikz}
\end{document}
```

Two zener diodes can also be used as a limiter for an ac signal.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[sinusoidal voltage source] ++(0,6)
to[R] ++(3,0) node[circ](A){}
to[zzD*, bipoles/length=1cm] ++(0,-3)
to[zzD*, invert, bipoles/length=1cm] ++(0,-3) node[circ](B){}
-- (0,0)
(A) -- ++(1,0) node[ocirc]{}
to[open, v^<=\Large$V_{out}$] ++(0,-6) node[ocirc]{}
-- (B)
;
\end{circuitikz}
\end{document}
```
In the above circuit, the output voltage $V_{{out}}$ will have a maximum value of,
$$
V_{out-pk}=V_{Z}+0.7\pu{ V}
$$
