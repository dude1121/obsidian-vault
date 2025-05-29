---
tags:
  - electronics
  - instrumentation
---
A **peak detector** circuit is a circuit that is used to determine the peak value of a varying voltage signal, ac or dc.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
node[ocirc](A){} node[above]{$V_\mathrm{in}$} ++(0.1,0) to[diode, l=$D$] ++(3,0) node[circ](B){}
(B) to[cC, l=$C$] ++(0,-3) node[circ](G){} node[ground]{}
(B) to[short] ++(2,0) node[circ](D){} to[R, l=$R$] ++(0,-3) node[](C){}
(C) to[short] (G)
(D) to[short] ++(2,0) node[ocirc]{} node[above]{$V_\mathrm{out}$}
;
\end{circuitikz}
\end{document}
```
The RC time constant should be chosen to be about ten times higher than the period of the input signal. That is, if we want to use a peak detector on a $f=60\ \mathrm{Hz}$ signal, our time constant should be about $\approx 150\ \mathrm{ms}$. 