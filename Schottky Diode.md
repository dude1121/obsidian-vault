---
tags:
  - semiconductors
  - electronics
  - electromagnetism
  - physics
  - components
---
A **Schottky diode** (named after German physicist Walter H. Schottky) is a high-[[Current|current]] [[Diode|diode]] used primarily in high [[Frequency|frequency]] and fast-switching applications. 

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[sD*, bipoles/length=1cm, o-o] ++(4,0)
;
\end{circuitikz}
\end{document}
```

They are sometimes called "Hot-Carrier diodes" due to the fact that there is a higher energy level of [[Electron|electrons]] in the *n*-region than in the metal region. 
# Construction

Rather than a typical [[PN Junction|pn junction]], a Schottky diode is constructed by joining a doped semiconductor region (typically *n*-type) with a [[Metal|metal]] such as [[Gold|gold]], [[Silver|silver]], or [[Platinum|platinum]]. The resulting junction is called a [[Schottky Barrier]]. Because there is no depletion region, the forward voltage of a Schottky diode is $V_{F}\approx 0.3\pu{ V}$ instead of the usual $V_{F}\approx 0.7\pu{ V}$ in a typical diode.

# Operating Principle

There are only majority carriers (electrons) in a Schottky diode and no minority carriers, and therefore no reverse leakage current. The metal region is heavily occupied by conduction electrons, and the *n*-type region is lightly doped. When the diode is forward biased, the higher-energy electrons in the *n*-region are injected into the metal region. Since there are no minority carriers, the diode reacts very quickly to a change in bias.