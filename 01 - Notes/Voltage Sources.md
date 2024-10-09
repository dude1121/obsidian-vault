---
tags:
  - electromagnetism
  - circuit-analysis
  - physics
  - voltage
  - source
---
A **voltage source** is anything that provides [[Voltage|voltage]] to an electrical circuit. This may in the the form of [[DC Electricity|DC]] or [[AC Electricity|AC]] voltage sources. An example of an ac voltage source is the output of a [[Generator|generator]] or from an ac [[Receptacle|receptacle]], and a dc voltage source may be from a [[Battery|battery]] or rectified ac output. 
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=$E_{S1}$, v_<=$12$V, invert, bipole/is voltage=false, voltage shift =2, voltage=american] ++(0,4)
to[short, f=$I_1$] ++(4,0)
to[R, l2=$R_1$ and $1$k$\Omega$, v<=$V_{R1}$, voltage shift = 2] ++(0,-4)
-- (0,0) node[ground]{}
;
\end{circuitikz}
\end{document}
```

We typically use $E$ to denote a voltage source, since it is a *source* of voltage, not a voltage *drop* (where $V$ would be used instead). In the circuit above, the symbol for a battery is shown, indicating this is a [[Series Circuits|series dc circuit]].  

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[sV, l=$E_{S1}$, v_<=$12$V, invert, bipole/is voltage=false, voltage shift =2, voltage=american] ++(0,4)
to[short, f=$I_1$] ++(4,0)
to[R, l2=$R_1$ and $1$k$\Omega$, v<=$V_{R1}$, voltage shift = 2] ++(0,-4)
-- (0,0) node[ground]{}
;
\end{circuitikz}
\end{document}
```

In an ac circuit, the voltage source symbol changes to reflect its sinusoidal nature. 

# Independent and Dependent Sources

Voltage sources can either be independent or dependent. An independent voltage source is like the sources above, a battery, ac receptacle, etc. It's voltage is not dependent on any other component. A dependent source can vary depending on some other external force. Dependent voltage sources can either be voltage-controlled (VCVS) or current-controlled (CCVS) and can of course be either dc or ac. 

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[american controlled voltage source, v_<=$E_{S1}$, invert, bipole/is voltage=false, voltage shift =2, voltage=american] ++(0,4)
to[short, f=$I_1$] ++(4,0)
to[R, l2=$R_1$ and $1$k$\Omega$, v<=$V_{R1}$, voltage shift = 2] ++(0,-4)
-- (0,0) node[ground]{}
;
\end{circuitikz}
\end{document}
```

Dependent sources are typically depicted as a diamond with either a plus and minus to indicate dc current directionality,

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[controlled sinusoidal voltage source, v_<=$E_{S1}$, invert, bipole/is voltage=false, voltage shift =2, voltage=american] ++(0,4)
to[short, f=$I_1$] ++(4,0)
to[R, l2=$R_1$ and $1$k$\Omega$, v<=$V_{R1}$, voltage shift = 2] ++(0,-4)
-- (0,0) node[ground]{}
;
\end{circuitikz}
\end{document}
```

or a sinusoid to indicated a dependent ac voltage source.