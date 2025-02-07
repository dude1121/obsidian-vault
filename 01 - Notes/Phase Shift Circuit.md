---
tags:
  - electrical-engineering
  - electronics
---
A **phase shift circuit** is a circuit that can generate pulses for an [[Rectifier#Controlling the output voltage|SCR rectifier]] to adjust the phase shift angle $\delta$ in the rectifier.
# Example
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[ocirc](AC1){} node[left]{$AC1$} to[R, l=$R_1$, a=$10\mathrm{k}\Omega$] ++(2,0) node[circ](A){}
to[R, l=$R_2$, a=$1\mathrm{k}\Omega$] ++(0,-2) node[ground]{}
(A) to[short] ++(1,0) node[circ](B){} to[short] ++(1,0)
node[op amp, anchor=+, yscale=-1](U1){}

(0,-3) node[ocirc](AC2){} node[left]{$AC2$} to[R, l=$R_3$, a=$10\mathrm{k}\Omega$] ++(2,0) node[circ](C){}
to[R, l=$R_4$, a=$1\mathrm{k}\Omega$] ++(0,-2) node[ground]{}
(C) to[short] ++(1.5,0) node[circ](D){} to[short] ++(0.5,0)
node[op amp, anchor=+, yscale=-1](U2){}

(U1.-) to[short] (U1.- -| D) to[short] (D)
(U2.-) to[short] (U2.- -| B) to[short] (B)

(U1.out) to[short] ++(1,0) node[circ](E){} to[R, l=$R_5$, a=$10\mathrm{k}\Omega$] ++(0,2) node[ocirc]{} node[above]{$5\mathrm{V}$}

(E) to[short] ++(0,-0.5) to[R,l=$R_6$, a=$10\mathrm{k}\Omega$] ++(2,0) node[circ](F){} to[cC, l=$C_1$] node[xshift=10mm, yshift=1mm]{$0.1\mu\mathrm{F}$} ++(0,-1) node[ground]{}

(E) to[short] ++(4,0) node[nand port, anchor=in 1](U3){}
(U3.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$}

(U2.out) to[short] ++(1,0) node[circ](H){} to[R, l=$R_7$, a=$10\mathrm{k}\Omega$] ++(0,2) node[ocirc]{} node[above]{$5\mathrm{V}$}

(H) to[short] ++(0,-1) to[R,l=$R_8$, a=$10\mathrm{k}\Omega$] ++(2,0) node[circ](I){} to[cC, l=$C_2$] node[xshift=10mm, yshift=1mm]{$0.1\mu\mathrm{F}$} ++(0,-1) node[ground]{}

(H) to[short] ++(4,0) node[nand port, anchor=in 2](U4){}
(U4.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$}

(F) to[short] ++(1.5,0) node[](F1){} to[short] (F1 |- U4.in 1) to[short] (U4.in 1)

(I) to[short] ++(1.75,0) node[](I1){} to[short] (I1 |- U3.in 2)
to[short] (U3.in 2)

(U3.out) to[short] ++(2,0) node[nand port, anchor=in 1](U5){}
(U5.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$}

(U4.out) to[short] ++(1.5,0) node[](U4A){} to[short] (U4A |- U5.in 2)
to[short] (U5.in 2)
;
\end{circuitikz}
\end{document}
```
