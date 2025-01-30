---
tags:
  - physics
  - electrical-engineering
  - semiconductors
---
A **triac** is a [[Semiconductor|semiconductor]] device that is similar to a [[Diac|diac]] but it has a gate terminal. 
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[left] {T$_1$} to[full triac, n=TRI] (3,0) node[right] {T$_2$}
(TRI.G) node[above] {G}
;
\end{circuitikz}
\end{document}
```
Unlike a typical [[Diode|diode]], the terminals are not denoted as $A$ and $K$. This is because a triac is designed for [[AC Electricity|ac]] applications where the both terminals $T_{1}$ and $T_{2}$ are connected to an anode and cathode simultaneously. A triac can be thought of as two [[Silicon-Controlled Rectifier|SCRs]] connected in parallel and in opposite directions with the gates shorted together. Unlike the SCR however, the triac can conduct in either direction when it is triggered on.
![[triac-construction.png]]
Much like the SCR, as the gate [[Current|current]] $I_{G}$ increases, the breakover [[Voltage|voltage]] decreases, making it easier to trigger the triac.  However due to the dual nature of a triac, there are four "quadrant" in which the triac can be triggered in with different effects.
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[very thick, <->] (-3,0) -- (3,0) node[anchor=north west] {G};
\draw[very thick, <->] (0,-3) -- (0,3) node[anchor=south east] {T1};
\draw (1.5,1.5) node[anchor=center] {I};
\draw (1.5,1) node[anchor=center] {G+, T$_1$+};
\draw (-1.5,1.5) node[anchor=center] {II};
\draw (-1.5,1) node[anchor=center] {G-, T$_1$+};
\draw (-1.5,-1) node[anchor=center] {III};
\draw (-1.5,-1.5) node[anchor=center] {G-, T$_1$-};
\draw (1.5,-1) node[anchor=center] {IV};
\draw (1.5,-1.5) node[anchor=center] {G+, T$_1$-};
\end{tikzpicture}
\end{document}
```
Triacs are frequently used in low-[[Power|power]] applications. It is much cheaper and easier to control compared to two SCRs connected antiparallel. However, a triac has a lower $dv/dt$ capability and a longer turnoff time, and it is not available in high voltage and high current ratings.

Similar to the SCR, the triac can be turned off by sufficiently dropping the anode current to the holding current $I_{\text{H}}$.  This value is dependant on the gate current with increasing levels of $I_{\text{G}}$ decreasing the holding current $I_{\text{H}}$. Dropping the anode current is most easily done by reversing the polarity of the triac or removing the $T_{1} - T_{2}$ voltage.
# Parameters
- *Off-state voltage*, $V_{\text{DRM}}$. This is the  maximum voltage across the triac when the gate is not triggered. This is similar to the "reverse breakdown voltage" in an SCR, but since a triac is symmetrical a "reverse" voltage has little meaning. This parameter should be $2-3$ times the design value.
- *On-state voltage*, $V_{\text{T}}$. This is the voltage across the triac when it is conducting. This value should ideally be as small as possible so as to reduce losses in the triac.
- *On-state current*, $I_\text{T}$. This is the maximum current the triac can sustain while conducting. This should also be $2-3$ times the design value.
- *Gate trigger current*, $I_{\text{GT}}$. This value is different depending on the quadrant the triac is operating in and the datasheet will communicate this difference.