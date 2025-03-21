---
tags:
  - electrical-engineering
---
An **inverter gate driver** is a [[Driver Circuit|driver circuit]] for an [[Inverter|inverter]]. It is similar to a typical [[Half-Bridge Circuit#Driver circuit|half-bridge driver]] but with some modifications. The goal is to ensure that only one half of the [[H-Bridge|H-bridge]] is active at a time, with a duty cycle corresponding to the designed output voltage.
# Sample circuit
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[ocirc]{} node[above]{$V_{CC}$} to[short] ++(1,0) node[circ](A){}
to[short] ++(1,0) node[circ](B){} to[short] ++(0,-1) node[circ](C){} to[short] ++(1,0)
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

(A) to[short] ++(0,-2) to[cC] (A |- U.bpin 4) to[short] ++(1.5,0) node[circ](D){}
to[short] ++(0,-2) node[circ](E){} node[ground]{}
(D) to[short] (U.bpin 4)

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
