---
tags:
  - electromagnetism
  - physics
  - circuit-analysis
---
An **H-bridge** is a circuit that switches the polarity of a [[Voltage|voltage]] applied across a load. It is typically used to control the direction of rotation of a [[DC Motor|dc motor]]. 
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[vsource] ++(0,5)
-- ++(3,0) to[nos, invert, l=$S_1$, *-] ++(0,-2.5) node[circ](A){}
to[nos, invert, l=$S_2$, -*] ++(0,-2.5) node[ground](G){}
-- ++(4,0) to[nos, l=$S_4$] ++(0,2.5) node[circ](B){}
to[nos, l=$S_3$] ++(0,2.5) -- ++(-4,0)
(0,0) -- (G)

(A) to[Telmech=M,n=motor] (B)
;
\end{circuitikz}
\end{document}
```
If switches $S_{1}$ and $S_{4}$ are closed, current will flow through the motor from the left side to the right, and the motor will have a positive voltage across it. If instead switches $S_{2}$ and $S_{3}$ are closed, the motor will have a negative voltage across it. This will result in the motor rotating in the opposite direction it rotated in with a positive voltage across it. 

Care must be taken to ensure that switches $S_{1}$ and $S_{2}$ are not closed at the same time (same with switches $S_{3}$ and $S_{4}$) otherwise the motor will be shorted out.