---
tags:
  - electronics
  - electromagnetism
  - physics
  - circuit-analysis
  - components
  - semiconductors
---
A **BJT** (**B**ipolar **J**unction **T**ransistor) is a type of [[Transistor|transistor]] used for signal amplification and switching. It comes in two types: *npn* and *pnp*, referring to the arrangement of the doped regions within the device.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[npn](Q){}
(Q.C) -- ++(0,1) node[ocirc, label=\Large C]{}
(Q.B) -- ++(-1,0) node[ocirc, label=left:\Large B]{}
(Q.E) -- ++(0,-1) node[ocirc, label=below:\Large E]{}
;
\end{circuitikz}
\end{document}
```
This is called a *bipolar* transistor because it makes use of both [[Electron|electrons]] and [[Hole Current|holes]] as current carriers.

# Construction

A BJT consists of three [[Semiconductor|semiconductor]] regions, each doped in an alternating pattern. In an *npn* BJT, there are two *n*-type regions and one *p*-type regions, and the opposite is true in a *pnp* BJT.
![[bjt construction.png]]
The [[PN Junction|pn junction]] joining the base and the emitter is fittingly called the *base-emitter junction*. 