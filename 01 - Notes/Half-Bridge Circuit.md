---
tags:
  - electrical-engineering
  - electronics
---
A **half-bridge** circuit is a gate-controlled circuit that can act as a [[DC-DC Convertor#Buck convertor|buck]], [[DC-DC Convertor#Boost convertor|boost]], or [[DC-DC Convertor#Buck-Boost|buck-boost]] convertor. It replaces the [[Diode|diode]] present in a typical convertor with a second [[Metal Oxide-Semiconductor Field Effect Transistor|MOSFET]] which allows us to control the timing on both FETs with a gate driver circuit.
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
The type of convertor this circuit behaves as depends on which terminal is designated as the input or output (see the table below).

| Convertor Type | Output Voltage                            | Input   | Output        |
| -------------- | ----------------------------------------- | ------- | ------------- |
| Buck           | $V_{o}=D\cdot V_{in}$                     | $V_{H}$ | $V_{L}$       |
| Boost          | $\displaystyle V_{o}=\frac{1}{D}V_{in}$   | $V_{L}$ | $V_{H}$       |
| Buck-Boost     | $\displaystyle V_{o}=\frac{1-D}{D}V_{in}$ | $V_{L}$ | $V_{H}-V_{L}$ |
In each case, $D$ is the [[Duty Cycle|duty cycle]] of the gate driver circuit. 
# Driver circuit
The driver circuit for the half-bridge needs to control the gates $G_{1}$ and $G_{2}$ of the MOSFETs. These gates need to be on at opposite times and never at the same time. The sample circuit below uses a IRS2004 IC to control the timing of the gates.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{diodes/scale=0.6}
\draw
(0,0) node[ocirc]{} node[above]{$V_{CC}$} to[short] ++(1,0) node[circ](A){}
to[short] ++(0,-1) node[circ](B){} to[short] ++(1.5,0)
node[dipchip, num pins=8, hide numbers, no topmark, external pins width=0.25, anchor=bpin 1](U){}

(U.bpin 1) 
node[left, yshift=2mm, font=\tiny]{1}
node[right, font=\small]{$V_{CC}$}
(U.bpin 2) 
node[left, yshift=2mm, font=\tiny]{2}
node[right, font=\small]{IN}
(U.bpin 3) 
node[left, yshift=2mm, font=\tiny]{3}
node[right, font=\small]{$\bar{\mathrm{SD}}$}
(U.bpin 4) 
node[left, yshift=2mm, font=\tiny]{4}
node[right, font=\small]{COM}
(U.bpin 5) 
node[right, yshift=2mm, font=\tiny]{5}
node[left, font=\small]{LO}
(U.bpin 6) 
node[right, yshift=2mm, font=\tiny]{6}
node[left, font=\small]{$V_s$}
(U.bpin 7) 
node[right, yshift=2mm, font=\tiny]{7}
node[left, font=\small]{HI}
(U.bpin 8) 
node[right, yshift=2mm, font=\tiny]{8}
node[left, font=\small]{$V_o$}

(B) to[cC] ++(0,-0.5) to[short] (B |- U.bpin 4) node[circ](C){}
to[short] (U.bpin 4)
(C) node[ground]{}

(A) to[diode] ++(6,0) node[circ](D){} to[short] (D |- U.bpin 8) node[circ](E){}
to[short] (U.bpin 8)

(U.bpin 7) to[short] ++(1,0) to[short] ++(0,2) to[short] ++(3,0) node[ocirc](G){} node[right]{$G_1$}
(U.bpin 5) to[short] ++(4,0) node[ocirc]{} node[right]{$G_2$}

(E) to[cC] (E |- U.bpin 6) node[circ](F){} to[short] (F -| G) node[ocirc]{} node[right]{M}

(U.bpin 6) to[short] (F)

(U.bpin 2) to[short] ++(-3,0) node[ocirc]{} node[left]{IN}
(U.bpin 3) to[short] ++(-3,0) node[ocirc]{} node[left]{$\bar{\mathrm{SD}}$}
;
\end{circuitikz}
\end{document}
```
