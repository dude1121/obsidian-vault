---
tags:
  - electrical-engineering
  - electrical-machines
  - electronics
---
A **variable frequency drive** (or, **VFD**) is a motor (primarily [[Induction Machine|induction motors]]) [[Driver Circuit|driver circuit]] that allows us to vary the speed of an ac motor. Essentially, a VFD converts a *CVCF* (constant [[Voltage|voltage]], constant [[Frequency|frequency]]) signal into a VVVF (variable voltage, variable frequency) signal. This is accomplished by taking the ac signal, [[Rectifier|rectifying]] it, and then [[Inverter|inverting]] it back into an ac signal, but this time at a frequency we can control.

This overview is demonstrated by the block diagram below.
![[vfd-block-diagram.png]]
# Sample circuit
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
node[ocirc](A){} node[left]{A} ++(0,-1) node[ocirc](B){} node[left]{B} ++(0,-1) node[ocirc](C){} node[left]{C}

(A) to[short] ++(1,0) node[circ](A1){} to[diode] ++(0,3) node[](P1){}
(A1) to[short] ++(0,-2) to[diode, invert] ++(0,-3) node[](N1){}

(B) to[short] ++(3,0) node[circ](B1){} to[short] ++(0,1) to[diode] ++(0,3) node[circ](P2){}
(B1) to[short] ++(0,-1) to[diode, invert] ++(0,-3) node[circ](N2){}

(C) to[short] ++(5,0) node[circ](C1){} to[short] ++(0,2) to[diode] ++(0,3) node[circ](P3){}
(C1) to[diode, invert] ++(0,-3) node[circ](N3){}

(P3) ++(2,0) node[circ](Cap1){} to[cC] (Cap1 |- N3) node[circ](Cap2){}

(Cap1) ++(2,0) node[circ](UP){} to[short] ++(0,-0.5) node[nigbt,bodydiode,anchor=D](Q1){} (Q1.S) to[short] (Q1.S |- A) node[circ](U){} node[left]{U} to[short] ++(0,-2.5) node[nigbt,bodydiode,anchor=D](Q2){} (Q2.S) to[short] (Q2.S |- N3) node[circ](UN){}

(UP) ++(2,0) node[circ](VP){} to[short] ++(0,-0.5) node[nigbt,bodydiode,anchor=D](Q3){} (Q3.S) to[short] (Q3.S |- B) node[circ](V){} node[left]{V} to[short] ++(0,-1.5) node[nigbt,bodydiode,anchor=D](Q4){} (Q4.S) to[short] (Q4.S |- N3) node[circ](VN){}

(VP) ++(2,0) node[circ](WP){} to[short] ++(0,-0.5) node[nigbt,bodydiode,anchor=D](Q5){} (Q5.S) to[short] (Q5.S |- C) node[circ](W){} node[left]{W} to[short] ++(0,-0.5) node[nigbt,bodydiode,anchor=D](Q6){} (Q6.S) to[short] (Q6.S |- N3) node[circ](WN){}

(U) to[short] ++(5,0) node[ocirc](){}
(V) to[short] ++(3,0) node[ocirc](){}
(W) to[short] ++(1,0) node[ocirc](){}

(P1) to[short] (WP)
(N1) to[short] (WN)
;
\end{circuitikz}
\end{document}
```
The VFD has essentially three main points: the rectifier, the dc link, and the inverter. The voltage at the dc link can be determined by,
$$
\begin{align}
V_{\mathrm{dc\ (no\ load)}}&=V_{\mathrm{s.l.peak}} \\
V_{\mathrm{dc}}&=\frac{3}{\pi}V_{\mathrm{s.l.peak}}
\end{align}
$$
where $V_{\mathrm{s.l.peak}}$ is the peak voltage of the rectifier, typically $\sqrt{ 2 }\cdot V_{\mathrm{in}}$. The equation for $V_{\mathrm{dc}}$ comes from averaging the voltage over a period from $60\degree-120\degree$ as shown below,
$$
\begin{align}
V_{\mathrm{dc}}=\frac{1}{\frac{1}{3}\pi}\int_{\frac{\pi}{3}}^{\frac{2\pi}{3}}V_{\mathrm{ab}}\ d\theta
\end{align}
$$
The duty cycle of the inverter will determine the output voltage of that phase.
$$
\begin{align}
V_{\mathrm{u}}&=D_{\mathrm{u}}V_{\mathrm{dc}} \\
V_{\mathrm{v}}&=D_{\mathrm{v}}V_{\mathrm{dc}} \\
V_{\mathrm{w}}&=D_{\mathrm{w}}V_{\mathrm{dc}}
\end{align}
$$
To get a steady sine wave output, the duty cycle must follow a [[Sinusoidal Function|sinusoidal]] pattern. This is often achieved by using a $50\%$ offset, as this simplifies the programming since the duty cycle is a comparatively simple equation.
![[3-phase-vvvf-vfd.png]]
In this case, the voltages of each phase are given by,
$$
\begin{align}
V_{\mathrm{u}}&=\frac{V_{\mathrm{dc}}}{2}+V_{\mathrm{pk}}\sin \omega t \\
V_{\mathrm{v}}&=\frac{V_{\mathrm{dc}}}{2}+V_{\mathrm{pk}}\sin (\omega t -120\degree)  \\
V_{\mathrm{w}}&=\frac{V_{\mathrm{dc}}}{2}+V_{\mathrm{pk}}\sin (\omega t +120\degree)
\end{align}
$$
For the corresponding duty cycles then,
$$
\begin{align}
D_{\mathrm{u}}&=\frac{1}{2}+D_{\mathrm{pk}}\sin \omega t \\
D_{\mathrm{v}}&=\frac{1}{2}+D_{\mathrm{pk}}\sin (\omega t - 120\degree) \\
D_{\mathrm{w}}&=\frac{1}{2}+D_{\mathrm{pk}}\sin (\omega t + 120\degree) 
\end{align}
$$
Where the $D_{\mathrm{pk}}$ is the peak duty cycle for a given output voltage. The output line voltage is given by,
$$
V_{\mathrm{uv}}=V_{\mathrm{u}}-V_{\mathrm{v}}=\sqrt{ 3 }V_{\mathrm{pk}}\sin\left( \omega t+\frac{\pi}{6} \right)
$$
This means that the peak line voltage is 
$$
V_{\mathrm{l.pk}}=\sqrt{ 3 }V_{\mathrm{pk}}
$$
and the [[Root Mean Square|rms]] line voltage,
$$
V_{\mathrm{l}}=\frac{V_{\mathrm{l.pk}}}{\sqrt{ 2 }}
$$
