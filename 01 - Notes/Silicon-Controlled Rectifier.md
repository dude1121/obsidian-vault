---
tags:
  - physics
  - electrical-engineering
  - electronics
---
A **silicon-controlled rectifier** or **SCR** is a [[Thyristor|thyristor]] that behaves as a [[Diode|diode]] (complete with an anode and cathode) with a gate terminal to control conduction.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[left] {A} to[full thyristor, n=TRI] (3,0) node[right] {K}
(TRI.G) node[above] {G}
;
\end{circuitikz}
\end{document}
```
SCRs are used in high [[Voltage|voltage]] and high [[Current|current]] switching applications, but crucially these applications must be *low [[Frequency|frequency]]*. An SCR can be represented as a *pnpn* junction, with the gate connected to a *p-type* section.
![[scr.png]]
The current through the SCR $I_{\text{AK}}$ can be controlled by a relatively low-current "control" signal current $I_{\text{G}}$. To "turn on" the SCR, it must be *forward biased*, i.e., $V_{\text{A}}>V_{\text{K}}$ and $V_{\text{G}}>V_{\text{K}}$. This is a very important concept, as the cathode voltage may not necessarily be at ground potential. The designer must take into consideration what potential $V_{\text{K}}$ will be at and design a [[Driver Circuit|driver circuit]] to achieve a proper gate voltage. 

The current at the gate will lower the barrier voltage required to allow the SCR to conduct. Conversely, if the gate voltage is negative with respect to the cathode, the barrier voltage *increases*. When this barrier voltage is reached, the voltage $V_{\text{AK}}$ will dramatically drop as it enters conduction. Once it enters conduction, the only way to "turn off" the SCR, the polarity across the device must be reversed and the current $I_{\text{AK}}$ must drop below the *holding current* $I_{\text{H}}$, which is the minimum current the device can operate in when first entering conduction. It is not sufficient to remove the gate voltage to turn off the device.
![[scr-performance-plot.png]]
# Parameters
Common datasheet values for SCRs are defined as,
- *Forward-breakover voltage* $V_{\text{BR(F)}}$. This is the voltage at which the SCR enters conduction. This value is maximum when $I_{\text{G}}=0\pu{ A}$ and it is designated as $V_{\text{BR(F0)}}$. 
- *Holding current* $I_{\text{H}}$. This is the value of anode current $I_{\text{AK}}$ below which the SCR switches from forward-conduction to the forward-blocking region. This value increases with decreasing values of $I_{\text{G}}$ and is maximum for $I_{\text{G}}=0\pu{ A}$.
- *Gate trigger current* $I_{\text{GT}}$. This is the value of gate current necessary to switch the SCR from the forward-blocking region to the forward-conduction region under specified conditions.
- *Average forward current* $I_{\text{F(avg)}}$ or $I_{\text{T}}$. This is the maximum continuous anode current that the device can withstand in the conduction state under specified conditions.
- *Forward-conduction region*. This region corresponds to the *on* condition of the SCR where there is forward current from anode to cathode through the very low [[Resistance|resistance]] of the SCR.
- *Reverse-breakdown voltage* $V_{\text{BR(R)}}$ or $V_{\text{DRM}}$. This is the value of reverse voltage from cathode to anode at which the device breaks into the avalanche region and begins to conduct heavily. 
- *On-state voltage* $V_{\text{T}}$. This is voltage across the SCR from anode to cathode when it is conducting. Ideally this parameter should be as low as feasibly and financially possible.
Note when making design choices for any component including SCRs, a safety margin of $2-3$ times the design value should be used.