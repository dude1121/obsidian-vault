---
tags:
  - electronics
  - electromagnetism
  - physics
  - semiconductors
  - components
  - circuit-analysis
---
A **photodiode** is a special type of [[Diode|diode]] that operates in reverse bias. 

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[pD*, o-o, bipoles/length=1cm] ++(4,0)
;
\end{circuitikz}
\end{document}
```
Its symbol is very similar to an [[LED]], but the arrows point *into* the diode, showing that the diode does not emit [[Light|light]] but rather *receives* light.

# Usage

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages]
\draw
(0,0) to[battery, invert, v<=$V_R$, bipole/is voltage=false, voltage shift=2] ++(4,0)
-- ++(0,2)
to[pD*, invert, mirror, bipoles/length=1cm, f=\large$I_\lambda$] ++(-4,0)
-- (0,0) node[ground]{}
;
\end{circuitikz}
\end{document}
```

When operating in reverse bias with no external light source, an ideal photodiode does not conduct. In reality there will be some small reverse current $I_{\lambda}$. We call this small reverse current *dark current*. When the photodiode is exposed to light, i.e., when the light intensity (or [[Irradiance|irradiance]]) the photodiode is exposed to increases, the depletion region of the photodiode's [[PN Junction|pn junction]] shrinks, and the current $I_{\lambda}$ increases.

Another way of stating this behaviour is that the irradiance the photodiode experiences $E_{e}$ is directly proportional to the diode's [[Conductance|conductance]] $G_{D}$. 
$$
E_{e} \propto G_{D}
$$
