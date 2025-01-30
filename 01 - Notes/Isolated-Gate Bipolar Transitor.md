---
tags:
  - physics
  - electronics
  - electrical-engineering
  - semiconductors
---
The **insulated-gate bipolar transistor**, or **IGBT**, is a [[Semiconductor|semiconductor]] device that has the output conduction characteristics of a [[Bipolar junction transistor|bipolar junction transistor]] but is [[Voltage|voltage]] controlled like a [[Field Effect Transistor|FET]].  Much like a BJT, the IGBT comes in both *npn* and *pnp* types. 
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[above=2mm]{npn} node[ocirc]{} to[short] ++(0,-0.25)
node[nigbt, anchor=C, bodydiode](Q1){}
(Q1.E) to[short] ++(0,-0.25) node[ocirc]{}
(Q1.G) node[left]{G} node[ocirc]{}
(Q1.C) node[right]{C}
(Q1.E) node[right]{E}

(4,0) node[above=2mm]{pnp} node[ocirc]{} to[short] ++(0,-0.25)
node[pigbt, anchor=E, bodydiode](Q2){}
(Q2.C) to[short] ++(0,-0.25) node[ocirc]{}
(Q2.G) node[left]{G} node[ocirc]{}
(Q2.C) node[right]{C}
(Q2.E) node[right]{E}

;
\end{circuitikz}
\end{document}
```
Also like a BJT, an IGBT contains a *collector* and *emitter* terminal, and the type of IGBT determines whether [[Current|current]] flows from collector to emitter (npn) or emitter to collector (pnp). Unlike the BJT, however, the transistor is controlled by a *gate* voltage. Since a BJT can not operate with a reverse voltage applied across it, most IGBTs contain a "body diode", a diode that is connected in parallel with the collector and emitter such that when the IGBT is reverse biased the IGBT itself is protected.

IGBTs are much better at handling high voltage and high current than MOSFETs and they typically exhibit a lower saturation voltage than [[Metal Oxide-Semiconductor Field Effect Transistor|MOSFETs]]. They also are better than BJTs for switching purposes since an IGBT can switch faster than a BJT. 
# Operating the IGBT
In order to make an IGBT conduct, the voltage across the gate to the emitter $V_{\text{GE}}$ must be greater than some threshold value determined by the specific component. This voltage must also be great enough to drive the IGBT into saturation (around double the threshold value). The IGBT itself must also be properly biased depending on its construction. The voltage across the IGBT in saturation is typically around $0.3\pu{ V}$ but this will vary from component to component. 

To turn the IGBT off, the gate voltage must be lowered beneath the threshold. Rule of thumb, though, is to remove the gate voltage entirely. In instances where we need to ensure that the IGBT is fully off, a negative gate voltage may even be applied. In this state, we can assume that the current through the component is $0\pu{ A}$. 
# Parameters
When selecting an IGBT the following parameters are important to consider:
- *Off-state voltage* $V_{\text{CES}}$. This is the maximum voltage that can be applied across the IGBT when it is not conducting. This should ideally be about $2-3$ times the design value.
- *On-state saturation voltage* $V_{\text{CE(sat)}}$. This is the voltage across the IGBT when it is driven into saturation. This should be as low as feasibly and financially possible.
- *On-state collector current* $I_{\text{C}}$. This is the maximum continuous current that can be sent through the IGBT when it is conducting. This should also be about $2-3$ times the design value.
- *Gate threshold voltage* $V_{\text{GE(th)}}$. This is the threshold voltage that must be applied to the gate that will allow the IGBT to begin conducting.
The parameters of the included body diode must also be considered.
- *Reverse voltage* $V_{\text{r}}$.
- *On-state forward voltage* $V_{\text{F}}$.
- *On-state forward current* $I_{\text{F}}$.