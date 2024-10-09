---
tags:
  - electronics
  - electromagnetism
  - semiconductors
  - circuit-analysis
  - components
---
A **phototransistor** is a type of [[Transistor|transistor]] similar to a [[BJT]] except the base [[Current|current]] $I_{B}$ is produced and controlled by [[Light|light]] and not a [[Voltage Sources|voltage source]]. 
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[npn, photo, anchor=C, scale=1.5](Q){}
(Q.E) to[short, -o] ++(0,-1) node[label=left:$E$]{}
(0,0) to[short, -o] ++(0,1) node[label=left:$C$]{}
;
\end{circuitikz}
\end{document}
```
The collector-base [[PN Junction|pn junction]] is exposed to light via a lens in the phototransistor package. When there is no light, there is a very small collector-to-emitter leakage current $I_{CEO}$, but this current is typically on the order of $\pu{ nA}$. When light hits the collector-base junction, a base current $I_{\lambda}$ is produced. $I_{\lambda}$ varies directly with the light [[Radiant Intensity|intensity]]. The collector current is proportional to this base current with the proportionality constant being the transistor's [[Current Gain|current gain]], $\beta_{DC}$. 
$$
I_{C}=\beta_{DC}I_{\lambda}
$$
Phototransistors are most sensitive to particular wavelengths in the red and [[Infrared|infrared]] parts of the [[Electromagnetic Spectrum|EM spectrum]]. 