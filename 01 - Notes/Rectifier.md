---
tags:
  - electromagnetism
  - physics
  - circuit-analysis
---
A **rectifier** is a circuit that converts an [[AC Electricity|ac voltage]] into a [[DC Electricity|dc voltage]]. A rectifier may be [[Half Wave Rectifier|half wave]] or [[Full Wave Rectifier|full wave]], single phase or three phase. 
# Applications
Rectifier circuits are used in various applications from converting [[Receptacle|receptacle]] ac voltage into a usable dc voltage for electronics, to storing [[Power Systems|power grid]] energy in [[Battery|batteries]], to usage in [[Variable Frequency Drive|VFDs]]. 
# Controlling the output voltage
A standard rectifier either half wave or full wave typically uses [[Diode|diodes]] to rectify the voltage from ac to dc. For some cases, this is sufficient. In other cases however, it is more useful to have control over *when* the diodes conduct and rectify the voltage. By controlling when the diodes begin conducting (also known as the *firing angle*) we can alter the average output voltage from the rectifier.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[sV, l=$V_s$] ++(0,-3)
(0,0) to[thyristor] ++(3,0)
to[R, l=$R_\mathrm{L}$] ++(0,-3) node[ground]{}
to[short] ++(-3,0)

(6,0) to[sV, l=$V_s$] ++(0,-2) node[](A){}
(6,0) to[short] ++(1,0) node[circ](B){}
to[thyristor, l=$T_1$] ++(0,3) to[short] ++(2,0) node[circ](E){}
to[thyristor, l=$T_2$, invert, mirror] ++(0,-3) to[short] ++(0,-2) node[circ](C){}
(A) to[short] (C)
to[thyristor, l=$T_4$, invert, mirror] ++(0,-3) node[circ](D){}
(B) to[short] ++(0,-2) to[thyristor, l=$T_3$, invert, mirror] ++(0,-3) to[short] ++(5,0) node[circ]{} node[ground](G){}
(E) to[short] (E -| G) node[circ]{} to[R, l=$R_\mathrm{L}$] (G)
;
\end{circuitikz}
\end{document}
```

Above are both half wave and full wave rectifier circuits with [[Silicon-Controlled Rectifier|SCRs]] instead of diodes that allow us to control the average output voltage.
## Full wave
![[full-wave-firing-angle.png]]
Above is a timing diagram of an input sinusoidal voltage like in the full wave rectifier circuit above. For the positive half-cycle, the SCRs $T_{1}$ and $T_{4}$ are triggered on. For the negative half-cycle, $T_{2}$ and $T_{3}$ are on. If these SCRs are triggered to match the input voltage [[Frequency|frequency]], then this circuit would be essentially a normal rectifier circuit. However, if we delay the on-time for the SCR triggers, we get an altered rectified output. 

The time (in degrees or radians) it takes for the SCRs to trigger is called the *phase shift angle* and it is denoted by $\delta$. Conversely, the time that the SCRs are conducting is called the *conduction angle* and it is denoted by $\alpha$. It stands to reason then that.
$$
\delta+\alpha=180\degree=\pi
$$
The average output is given by,
$$
V_{\text{av}}=\frac{1}{\pi}\int_{\delta}^\pi V_{\text{pk}}\sin \theta \ d\theta
$$
or, if $t$ is the time delay for the SCR to begin conducting and $T$ is the period,
$$
V_{\text{av}}=\frac{1}{T}\int_{t}^TV_{\text{pk}}\sin(\omega t)\ dt
$$
Evaluating the first integral though has this expression simplify to
$$
V_{\text{av}}=\frac{V_{\text{pk}}}{\pi}(1+\cos \delta)
$$
