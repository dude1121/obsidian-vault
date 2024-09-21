---
tags:
  - electromagnetism
  - physics
  - circuit-analysis
  - semiconductors
  - electronics
---
A **diode** is a circuit component that only allows [[Current|current]] flow in one direction.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[diode] (4,0)
;
\end{circuitikz}
\end{document}
```

The symbol for a diode points in the direction in which it will allow current to flow. The left side is known as the *anode* (A) and the right side is known as the *cathode* (K). On a physical diode, the cathode is typically denoted with a band or tab.

# Construction

A diode is, at its core, a [[PN Junction]]. The anode is connected to the p-type region and the cathode is connected to the n-type region. When a [[Voltage|voltage]] is applied across the diode, more electrons pass through the diode into the n-type region, and are able to overcome the barrier voltage. This shrinks the depletion region, and it allows current to flow.

# Biasing

A diode is said to be in *forward bias* if the condition described above is met. That is, if a voltage is applied across the diode that is sufficiently large to overcome the [[Barrier Potential|barrier potential]], current is able to flow through the diode. The applied voltage must also be in the correct polarity, that is, the anode must be more positive than the cathode.

A diode is in *reverse bias* if the applied voltage is in reverse polarity, where the cathode is more positive than the anode. In this state, a typical diode will not conduct current. This is because the applied voltage has the opposite effect on the depletion region than in forward bias. The depletion region is enlarged and (in theory) no current is able to flow. In reality, a small *reverse current* will be allowed to flow, but in most cases it is too small to be noticeable. 

If the applied voltage in reverse bias is too large for the diode to handle, the diode enters *reverse breakdown*. The voltage that sends a diode into reverse breakdown is fittingly called the *breakdown voltage*. The high reverse-bias voltage imparts energy to the free electrons as they speed through the p-region. They then collide with valence electrons within the region and impart enough energy to jump them into the conduction band. This produces more free electrons that in turn do the same thing. This effect is known as the *avalanche effect* and if steps are not taken to limit the current it will result in damage to the diode.

# Current v. Voltage Response
![[forward-reverse bias.png]]
If the applied voltage $V_{D}$ is between the breakdown voltage $V_{BR}$ and the barrier potential $V_{B}$, there is next to no current flowing through the diode. In practice there is a little, but this current is negligible in most applications. Once the forward voltage $V_{F}>V_{B}$, the current $I_{F}$ increases drastically, but the voltage drop across the diode $V_{F}$ remains relatively constant. This is similar to but not quite the case in reverse breakdown, where the reverse voltage $V_{R}$ does increase slightly as the current $I_{R}$ increases drastically. 

If there is an increase in temperature, the response of the diode is slightly different. As a general rule, the barrier potential $V_{B}$ decreases by $2\pu{ mV}$ for each degree increase in temperature.
![[forward-reverse bias temp.png]]

# Diode Models
In circuit analysis, we can represent a diode in three different models: the ideal model, the practical model, and the complete model.

## The Ideal Model

In the ideal diode model, the diode is modeled simply as an open or closed switch, depending on if it is forward or reverse bias. 

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=\Large$E_s$] (4,0)
(0,0) to[R, l=\Large$R$] (0,4)
to[diode, l=\Large$D$] (4,4)
to[short] (4,0)

(6,0) to[battery, l=\Large$E_s$] (10,0)
(6,0) to[R, l=\Large$R$] (6,4)
to[normal closed switch, l=\Large$D$] (10,4)
to[short] (10,0)

(4.75,2) node[]{\LARGE$=$}
;
\end{circuitikz}
\end{document}
```

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(4,0) to[battery, l=\Large$E_s$] (0,0)
(0,0) to[R, l=\Large$R$] (0,4)
to[diode, l=\Large$D$] (4,4)
to[short] (4,0)

(10,0) to[battery, l=\Large$E_s$] (6,0)
(6,0) to[R, l=\Large$R$] (6,4)
to[opening switch, l=\Large$D$] (10,4)
to[short] (10,0)

(4.75,2) node[]{\LARGE$=$}
;
\end{circuitikz}
\end{document}
```
## The Practical Model
\
In the practical model, the diode is modeled as a switch still, but there is an added opposing voltage source if the diode is in forward bias, to represent the barrier potential.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=\Large$E_s$] (4,0)
(0,0) to[R, l=\Large$R$] (0,4)
to[diode, l=\Large$D$] (4,4)
to[short] (4,0)

(6,0) to[battery, l=\Large$E_s$] (10,0)
(6,0) to[R, l=\Large$R$] (6,4)
to[battery1, l=\Large$V_F$] (8,4)
to[normal closed switch] (10,4)
to[short] (10,0)

(4.75,2) node[]{\LARGE$=$}
(8,5) node[anchor=south]{\Large$D$}
;
\end{circuitikz}
\end{document}
```
## The Complete Model

This is the most accurate model of a diode. It includes the barrier potential and a switch, like the practical model, but it also includes the dynamic [[Resistance|resistance]] of the diode, $r_{d}'$.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=\Large$E_s$] (4,0)
(0,0) to[R, l=\Large$R$] (0,4)
to[diode, l=\Large$D$] (4,4)
to[short] (4,0)

(6,0) to[battery, l=\Large$E_s$] (10,0)
(6,0) to[R, l=\Large$R$] (6,4)
to[battery1, l=\Large$V_F$] (7,4)
to[R, l=\Large$r_d'$] (9,4)
to[normal closed switch] (10,4)
to[short] (10,0)

(4.75,2) node[]{\LARGE$=$}
(8,5) node[anchor=south]{\Large$D$}
;
\end{circuitikz}
\end{document}
```

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=\Large$E_s$] (4,0)
(0,0) to[R, l=\Large$R$] (0,4)
to[diode, l=\Large$D$] (4,4)
to[short] (4,0)

(10,0) to[battery, l=\Large$E_s$] (6,0)
to[R, l=\Large$R$] (6,3)
to[opening switch] (10,3)
to[short] (10,0)

(6.5,3) to[short, *-] (6.5,4)
to[R, l=\Large$r_R'$] (9.5,4)
to[short, -*] (9.5,3)

(4.75,2) node[]{\LARGE$=$}
(8,5) node[anchor=south]{\Large$D$}
;
\end{circuitikz}
\end{document}
```
 In a forward biased diode, this resistance is placed in series with the switch and the [[Voltage Sources|voltage source]]. The small resistance represents the slight increase in voltage and current as a greater $V_{BIAS}$ is applied. In a reverse biased diode, the very large reverse resistance $r_{R}'$ allows to calculate the trickle current through the diode while in reverse bias.