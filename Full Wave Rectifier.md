---
tags:
  - electromagnetism
  - physics
  - circuit-analysis
---
A **full wave rectifier** is a [[Rectifier|rectifier]] circuit that converts the entire [[AC Electricity|ac waveform]] into a steady [[DC Electricity|dc signal]].

# Full Wave (Centre-Tapped)
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[sinusoidal voltage source] (0, 4)
to[short] (3,4)
to[L] (3,0)
to[short] (0,0)

(4, 4) to[L, name=1, mirror] (4,0) node[circle] at(1.midtap) (A){}
(A) to[short] ++(1,0) node[ground] (B){}
(4,4) to[diode, l=$D_1$, bipoles/length=1cm] (7,4)
(4,0) to[diode, l=$D_2$, bipoles/length=1cm] (7,0)
to[short, -*] (7,2) to[short] (7,4)
(7,2) -- (8,2) to[R, l=$R_L$] (8,0) node[ground]{}

;
\end{circuitikz}
\end{document}
```
The above circuit is a full wave rectifier that makes use of a centre-tapped [[Transformer|transformer]]. In the positive half-cycle of the input signal, [[diode]] $D_{1}$ will conduct, and $D_{2}$ will be reverse biased. In the negative half-cycle, diode $D_{1}$ will be reverse biased and diode $D_{2}$ will conduct. This results in the entire waveform being converted into a dc signal through the load resistor $R_{L}$. However, since this uses a centre-tapped transformer, the peak [[Voltage|voltage]] across the output $V_{o}$ will be half the transformer's secondary voltage, minus the diode's $V_{F}\approx 0.7\pu{ V}$. 
$$
V_{o-pk}=\frac{V_{S-pk}}{2}-V_{F}
$$
## Peak Inverse Voltage

A key attribute of rectifying diodes is their Peak Inverse Voltage rating (PIV). This refers to the maximum amount of reverse voltage that the diode will experience during normal operation of the circuit. In the case above, during the positive half-cycle, diode $D_{1}$ will have no reverse voltage since it is in conduction, but $D_{2}$ will have the *entire* secondary voltage dropped across it, less $D_{1}$'s $V_{F}$. When selecting a diode, the designer must make sure the component can withstand a reverse voltage greater than the calculated PIV. 

# Full Wave (Bridge Rectifier)

A bridge rectifier is a way to rectify ac voltage that does not require a centre-tapped transformer. It consists of 4 diodes arranged in a bridge network that will output a dc signal.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages]
\draw
(0,-1) to[sinusoidal voltage source] (0,4) -- (2,4)
to[L] (2,-1) -- (0,-1) node[ground]{}
(2.75,4) to[L, mirror, v^=$V_s$, f<=$I$, voltage shift=5] (2.75,-1)
(2.75,4) to[short, f=$I$] (8,4) -- (8,3.75)
to[diode, *-, bipoles/length=1cm, v^=$D_1$, f>_=$I$] (10.121,1.629) node[](A){}
to[diode, *-, bipoles/length=1cm, invert, v=$D_4$] (8,-0.492) node[](B){}
to[diode, *-, bipoles/length=1cm, invert, v<=$D_2$, f<=$I$] (5.879,1.629) node[](C){}
to[diode, *-,bipoles/length=1cm, v<=$D_3$] (8, 3.75)

(2.75,-1) to[short, f<=$I$] (8,-1) to[short] (B)
(C) to[short] ++(-1,0) to[short, f<=$I$] ++(0,-1) node[ground]{}
(A) to[short, f=$I$] ++(1,0)
to[R, l=$R_L$, f=$I$] ++(0,-2) node[ground]{}
;
\end{circuitikz}
\end{document}
```

Above is a full wave bridge rectifier circuit during the positive half-cycle of an ac input, and below is during the negative half-cycle.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages]
\draw
(0,-1) to[sinusoidal voltage source] (0,4) -- (2,4)
to[L] (2,-1) -- (0,-1) node[ground]{}
(2.75,4) to[L, mirror, v^<=$V_s$, f=$I$, voltage shift=5] (2.75,-1)
(2.75,4) to[short, f<=$I$] (8,4) -- (8,3.75)
to[diode, *-, bipoles/length=1cm, v^<=$D_1$] (10.121,1.629) node[](A){}
to[diode, *-, bipoles/length=1cm, invert, v<=$D_4$, f<=$I$] (8,-0.492) node[](B){}
to[diode, *-, bipoles/length=1cm, invert, v=$D_2$] (5.879,1.629) node[](C){}
to[diode, *-,bipoles/length=1cm, v=$D_3$, f=$I$] (8, 3.75)

(2.75,-1) to[short, f=$I$] (8,-1) to[short] (B)
(C) to[short] ++(-1,0) to[short, f<=$I$] ++(0,-1) node[ground]{}
(A) to[short, f=$I$] ++(1,0)
to[R, l=$R_L$, f=$I$] ++(0,-2) node[ground]{}
;
\end{circuitikz}
\end{document}
```

Note that regardless of the direction of current going into the rectifier, it always comes out in one direction. This is what makes it a full-wave rectifier. This configuration is useful because it does not require a centre-tapped transformer. The peak output voltage in this case is also nearly the entire voltage across the transformer's secondary, less two diode drops.
$$
V_{o-pk}=V_{S}-2V_{F}
$$
## Filtering

The output of a full wave bridge rectifier as shown above would be a pulsing signal.
![[full-wave-unfiltered.png]]
While this is technically DC, it is not very stable. Ideally, we want a completely flat line at some voltage level. By adding a capacitor in parallel with our output, we can smooth out the waveform.
![[Full-Wave Ripple.png]]
Generally speaking, the larger the capacitor value added in parallel, the better quality the output waveform. We can qualify how well the output is filtered by the [[Ripple Factor|ripple factor]]. 

![[Ripple Factor]]

The peak-to-peak ripple voltage and the average "DC" value can be approximated by,
$$
V_{r-pp}=\left(\frac{1}{fR_{L}C}\right)V_{pk(rect)}
$$
and
$$
V_{DC}\approx\left(1 -\frac{1}{2fR_{L}C} \right)V_{pk(rect)}
$$
where $V_{pk(rect)}$ is the peak rectified voltage, $f$ is the frequency of the *rectified* voltage (important to note this is *not* the input frequency, but rather the output frequency, which will be double the input frequency), $R_{L}$ is the resistance of the load, and $C$ is the capacitance of the filtering capacitor. 