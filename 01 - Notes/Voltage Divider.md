---
tags:
  - electrical-engineering
  - electromagnetism
  - circuit-analysis
---
A **voltage divider** is a type of [[Linear Circuit|linear circuit]] that produces an output [[Voltage|voltage]] that is proportional to its input voltage. 

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[ocirc]{} node[left]{$V_{cc}$} to[short] ++(1,0) to[generic, l=$Z_1$] ++(0,-2) node[circ](A){} to[generic, l=$Z_2$] ++(0,-2) node[tlground]{}
(A) to[short] ++(1,0) node[ocirc]{} node[right]{$V_o$}
;
\end{circuitikz}
\end{document}
```

The output voltage $V_{o}$ can be found by applying the *voltage divider rule*.
$$
V_{o}=V_{cc}\left(\frac{Z_{2}}{Z_{1}+Z_{2}}\right)
$$
The ratio of $Z_{2}$ to the sum of $Z_{1}$ and $Z_{2}$ is the [[Proportionality Constant|proportionality constant]]. 