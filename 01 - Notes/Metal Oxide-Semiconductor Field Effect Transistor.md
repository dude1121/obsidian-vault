---
tags:
  - physics
  - electrical-engineering
  - electronics
  - semiconductors
---
A **metal oxide-semiconductor field effect transistor**, better known as a **MOSFET**, is a [[Field Effect Transistor|field effect transistor]] that uses a layer of [[Silicon Dioxide|silicon dioxide]] ($\ce{SiO_{2}}$) to isolate the gate from the channel. There are two main types of MOSFETs: *ehancement* and *depletion*. MOSFETs are typically used for low [[Voltage|voltage]], high [[Current|current]] applications. The voltage cutoff point is typically around $250\pu{ V}$, anything above this limit will typically make use of an [[Isolated-Gate Bipolar Transitor|IGBT]].
# Enhancement-type
![[mosfet-construction.png]]
An enhancement MOSFET consists of a substrate of either *n* or *p* type material with a drain and source terminal connected to a smaller region of the oppositely doped material. When a voltage is applied to the gate terminal, a channel of the material attached to the drain and source forms, allowing current to flow from the drain to source (or source to drain). If, as in the picture above, the channel that forms is *n* type, then we call this an *n-channel E-MOSFET*. If instead the channel is formed from *p* type material, it is called a *p-channel E-MOSFET*.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[nigfete](Q){}
(Q.D) node[ocirc]{} node[above=2mm]{D}
(Q.S) node[ocirc]{} node[below=2mm]{S}
(Q.G) node[ocirc]{} node[left=2mm]{G}

(3,0) node[pigfete](Q2){}
(Q2.D) node[ocirc]{} node[below=2mm]{D}
(Q2.S) node[ocirc]{} node[above=2mm]{S}
(Q2.G) node[ocirc]{} node[left=2mm]{G}
;
\end{circuitikz}
\end{document}
```
## Operation
An *n-channel* device requires a positive gate-to-source voltage $V_{\text{GS}}$ whereas a *p-channel* device requires a negative $V_{\text{GS}}$. The plots of the drain current vs the gate-source voltage for both n-channel and p-channel E-MOSFETs are shown below.
![[e-mosfet-id-vs-vgs.png]]Note that neither transistor can conduct when $V_{\text{GS}}=0\pu{ V}$. When the transistor is biased, the drain-source channel acts as a small [[Resistor|resistor]] whose value is typically denoted as $R_{\text{ds(on)}}$. This means that once the MOSFET is properly biased, the current can conduct in either direction and the voltage across the FET is $I_{\text{D}}\cdot R_{\text{ds(on)}}$.

The current through the MOSEFET $I_{\text{D}}$ is given by the relation,
$$
I_{\text{D}}=K(V_{\text{GS}}-V_{\text{GS(th)}})^2
$$
where $K$ is a constant that depends on the particular MOSFET and can be determined from the datasheet by taking the $I_{\text{D(on)}}$ and the given value of $V_{\text{GS}}$ given and rearranging the above equation for $K$. 

To turn the MOSFET off, $V_{\text{GS}}$ must be brought below the MOSFET's threshold, $V_{\text{GS(th)}}$.
## Biasing
### Voltage-divider bias
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{resistors/scale=0.75}
\draw
(0,0) node[ocirc]{} node[above=2mm]{$+V_{DD}$}
to[short] ++(0,-0.5) node[circ](A){}
to[R, l=$R_\mathrm{D}$] ++(0,-2) node[nigfete,anchor=D, scale=1.2](Q){$Q_1$} 
(A) to[short] ++(-2,0) node[](B){} to[R, l=$R_1$] (B |- Q.G) node[circ](C){} to[short] (Q.G)
(C) to[R, l=$R_2$] ++(0,-1.5) node[ground](G){}
(Q.S) to[short] (Q.S |- G) node[ground]{}
;
\end{circuitikz}
\end{document}
```
In the above configuration, the MOSFET  $Q_{1}$ is biased by the voltage divider between $R_{1}$ and $R_{2}$ along with a current limiting resistor $R_{D}$. The gate-source voltage can be found in this configuration by,
$$
V_{\text{GS}}=\left(\frac{R_{2}}{R_{1}+R_{2}}\right)V_{\text{DD}}
$$
and the drain-source voltage can be found by,
$$
V_{\text{DS}}=V_{\text{DD}}-I_{\text{D}}R_{\text{D}}
$$
where $I_{\text{D}}$ is found by the method [[Metal Oxide-Semiconductor Field Effect Transistor#Operation|above]].
### Drain-feedback bias
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{resistors/scale=0.75}
\draw
(0,0) node[ocirc]{} node[above=2mm]{$+V_{DD}$}
to[R, l=$R_\mathrm{D}$] ++(0,-2) node[circ](A){} to[short] ++(0,-0.5) 
node[nigfete,anchor=D, scale=1.2](Q){$Q_1$} 
(A) to[R, l=$R_\mathrm{G}$] ++(-2,0) node[](B){} to[short] (B |- Q.G) to[short] (Q.G)
(Q.S) to[short] ++(0,-1) node[ground]{}
;
\end{circuitikz}
\end{document}
```
In this configuration, there is a negligible gate current $I_{\text{G}}$. Therefore, we can assume that there is no voltage across $R_{\text{G}}$ making $V_{\ \text{GS}}=V_{\ \text{DS}}$. 
## Parameters
- *Off-state voltage* $V_{\text{DSS}}$. This is the maximum voltage the MOSFET can withstand. This value should be $2-3$ times the designed value.
- *On-state drain-source resistance* $R_{\text{DS(on)}}$. This is the drain-source resistance of the MOSFET at approximately two times the gate threshold voltage. This should be as low as feasibly and financially possible.
- *On-state drain current* $I_{\text{D}}$. This is the maximum continuous drain current the MOSFET can withstand. This should be $2-3$ times the design value.
- *Gate threshold voltage* $V_{\text{GS(th)}}$. This is the minimum gate-to-source voltage at which the MOSFET begins to conduct. For logic level circuits this should be less than $3\pu{ V}$ and for regular circuits this should be more than $5\pu{ V}$.
- *Power dissipation* $P_{\ \text{D}}$. This is the maximum power allowed for safe operation and is based in junction to case temperature. 