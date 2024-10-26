---
tags:
  - electromagnetism
  - electrical-engineering
  - physics
---
**Resonance** is a phenomenon that has varying applications in many different fields. Typically, resonance deals with the [[Frequency|frequency]] of some signal or wave.

# Electrical Engineering

In EE, a circuit is said to be in *resonance* if the frequency of the applied voltage is such that the all [[Reactance|reactive]] elements have their reactive attributes canceled out, such that only resistive elements have an impact on the circuit. A resonant circuit *must* have [[Inductor|inductive]] and [[Capacitor|capacitive]] elements. 

Resonant circuits can be either series or parallel. 

## Series Resonant Circuits

Consider the following circuit:
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
	(0,0) to[sinusoidal voltage source, l=\Large $e_{S}$] (0,-4)
	(0,0) to[short, f=\Large$i$] (0.5,0)
	to[R, l=\Large$R$] (4.5,0)
	to[L, l=\Large$L$] (7.5,0)
	to[C,l=\Large$C$] (7.5,-4)
	to[short] (0,-4) node[ground]{}
;
\end{circuitikz}
\end{document}
```
The total [[impedance]] of this circuit at any given frequency is,
$$
\mathbf{Z_{T}}=R+jX_{L}-jX_{C}=R+j(X_{L}-X_{C})
$$
At resonance, $X_{L}=X_{C}$. The total impedance is therefore,
$$
\mathbf{Z_{T_{S}}}=R
$$
The subscript $_{s}$ indicates this is a circuit at *series* resonant conditions. The frequency for a series resonant circuit is given by,
$$
\begin{aligned}
X_{L}&=X_{C}\\
2\pi fL&=\frac{1}{2\pi fC}\\
(2\pi)^2LCf^2&=1\\
f^2&=\frac{1}{(2\pi)^2LC}\\
f&=\frac{1}{2\pi \sqrt{ LC }}
\end{aligned}
$$
Note that at resonance, $\mathbf{Z_{T}}$ is at its minimum value. Since current is given by,
$$
\mathbf{I}=\frac{\mathbf{E}}{\mathbf{Z}}
$$
this means that at resonance, the current will be at its maximum value. The input voltage and current are also *in phase* since the [[Resistance|resistive]] element introduces no [[Phase Shift|phase shift]].

### Quality Factor

The [[Quality Factor|quality factor]] $Q_{s}$ for a series resonant circuit is defined as,
$$
Q_{s}=\frac{\text{Reactive Power}}{\text{Average Power}}=\frac{Q}{P}
$$
This factor is an indication of how much energy is placed in "storage" compared to that dissipated. The lower the level of dissipation, the higher the $Q_{s}$ factor and the region of resonance is more concentrated. We can substitute in values to find:
$$
\begin{aligned}
Q_{s}&=\frac{I^2X_{L}}{I^2R}\\
&=\frac{X_{L}}{R}
\end{aligned}
$$
If there is no additional resistance in the circuit other than the inductor's coil resistance, then $Q_{s}=Q_{l}$. However, the inductor's quality factor will vary with frequency, so the quality factor can be found a different way. If we substitute our equation for the resonant frequency into the equation for the quality factor we get,
$$
\begin{aligned}
Q_{s}&=\frac{X_{L}}{R}\\
&=\frac{2\pi f_{s} L}{R}\\
&=\frac{2\pi L}{R}\left(\frac{1}{2\pi \sqrt{ LC }}\right)\\
&=\frac{2\pi L}{2\pi R\sqrt{ LC }}\\
&=\frac{L}{R\sqrt{ LC }}\cdot\frac{\sqrt{ L }}{\sqrt{ L }}\\
&=\frac{1}{R}\sqrt{ \frac{L}{C} }
\end{aligned}
$$
### Selectivity

![[series-resonance.png]]
Above is a plot of the current through a given series resonant circuit as a [[Function|function]] of frequency. As can be seen, at resonance frequency, $f_{s}$, the current is at a maximum. For this circuit in particular, that frequency is about $f=15\text{kHz}$. Note that this curve is not entirely symmetrical. This is due to the fact that while inductive reactance is linear, capacitive reactance is not, and the current vs frequency curve falls off much slower as $f\rightarrow \infty$ than as $f\rightarrow 0$. 
![[series-resonance-impedance.png]]
The impedance vs frequency graph seems to mirror the current vs frequency graph, which makes sense since $\mathbf{I} \propto \mathbf{Z}^{-1}$. 

Note the dashed green lines in the current vs. frequency plot. The horizontal graph corresponds to the value $\frac{\mathbf{I}_{max}}{\sqrt{ 2 }}$. This value is important and known as the *half power* value. This is because,
$$
P_{max}=\mathbf{I}_{max}^2R
$$
$$
P_{half-power}=\left(\frac{\mathbf{I}_{max}}{\sqrt{ 2 }}\right)^2R=\frac{1}{2}\mathbf{I}_{max}^2R=\frac{1}{2}P_{max}
$$
Therefore, using this value of current will give us the point where the power dissipated in the circuit is exactly *half* its maximum values. Any resonant circuit will have two frequencies for which the power is half its maximum value, and these are called various names be it *cut-off frequencies*, *half-power frequencies*, *corner frequencies*, or, the one I will use here, *[[Band Frequency|band frequencies]]*. They are commonly denoted as $f_{1}$ and $f_{2}$. The range between the two is called the [[Bandwidth|bandwidth]]. 
$$
BW=f_{2}-f_{1}
$$
Since a resonant circuit is adjusted to select a band of frequencies, the curve of current vs frequency is called the *[[Selectivity Curve]]*.

The shape of the selectivity curve is dependant on the components within the circuit. A larger resistance reduces the bandwidth and vice versa. A higher resistance also reduces the quality factor since 
$$
Q_{s}=\frac{X_{L}}{R}
$$
Since resistance is the way in which the bandwidth is changed, the bandwidth is therefore related to the quality factor. 
![[series-resonance-various-r.png]]
As the resistance increases, the bandwidth increases with it, and the peak of the maximum current widens. At very low resistances (and therefore very high quality factors) the peak is nearly symmetrical about the resonance frequency. However, as resistance increases (and the quality factor lowers) the plot becomes less and less symmetrical.

If $Q_{s}\geq 10$, we can assume the plot is symmetrical, and therefore,
$$
f_{2}=f_{s}+(f_{s}-f_{1})
$$
However if $Q_{s}<10$, the frequencies must be determined with a more precise equation,
$$
f_{1}=\left[\frac{1}{2\pi}\left(-\frac{R}{2L}+\left[\left(\frac{1}{2}\sqrt{ \left(\frac{R}{L}\right)^2+\frac{4}{LC} }\right)\right]\right)\right]
$$
$$
f_{2}=\left[\frac{1}{2\pi}\left(\frac{R}{2L}+\left[\left(\frac{1}{2}\sqrt{ \left(\frac{R}{L}\right)^2+\frac{4}{LC} }\right)\right]\right)\right]
$$
### Practical Considerations

In a series resonant circuit, the resistance of any given resistor is not the only resistance that must be considered. Both the voltage source and the inductor have internal resistances.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[sinusoidal voltage source, l_=\Large $E_{S}$] (0,-4)
(0,0) to[R, l=\Large $R_S$] (2,0)
to[R, l=\Large$R$] (6,0)
to[R, l=\Large$R_L$] (8,0)
to[L, l=\Large$L$] (10,0)
to[C, l=\Large$C$] (10,-4)
to[short] (0,-4) node[ground] {}
;
\end{circuitikz}
\end{document}
```
When calculating the circuit quality factor, then, the *entire* resistance must be considered.

## Parallel Resonant Circuits

Consider the following parallel circuit.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,-4) to[american current source, l=\Large$I_S$] (0,0)
to[short] (2,0)
to[short, *-*] (4,0)
to[short] (6,0)
to[C, l=\Large$C$] (6,-4)
(2,0) to[R, l=\Large$R$, -*] (2,-4)
(4,0) to[L, l=\Large$L$, -*] (4,-4)
(6,-4) to[short] (0,-4) node[ground]{}
;
\end{circuitikz}
\end{document}
```

Recall that an inductor is actually made up of an internal series resistance with the inductor. To analyze this circuit properly, we must break up the source and the inductor into parallel resistive components. To do this with the inductor, we can make use of [[Series-Parallel R & X Conversions]]. Recall that,
$$
R_{p}=\frac{R_{L}^2+X_{L}^2}{R_{L}}
$$
$$
X_{p}=\frac{R_{L}^2+X_{L}^2}{X_{L}}
$$
Our circuit now looks something like this:
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,-4) to[american current source, l=\Large$I_S$] (0,0)
to[short] (2,0)
to[short, *-*] (4,0)
to[short] (6,0)
to[short, *-*] (8,0)
to[short] (10,0)
to[C, l=\Large$C$] (10,-4)
(2,0) to[R, l=\Large$R_S$, -*] (2,-4)
(4,0) to[R, l=\Large$R$, -*] (4,-4)
(6,0) to[R, l=\Large$R_{p}$, -*] (6,-4)
(8,0) to[L, l=\Large$X_{p}$, -*] (8,-4)
(10,-4) to[short] (0,-4) node[ground]{}
;
\end{circuitikz}
\end{document}
```
We can then combine the three resistive elements for analysis purposes into a total circuit resistance, $R_{T}$, where
$$
R_{T}=\left(R_{S}^{-1}+R^{-1}+R_{p}^{-1}\right)^{-1}
$$
For a parallel network, since the resistance in the equivalent model $R_{p}$ is frequency dependant, the frequency at which a maximum voltage across any one branch is obtained is not the same as the unity-power-factor frequency.

In this case, for unity power factor, the reactance of the capacitor needs to match not the reactance of the inductor, but rather its *parallel equivalent*. That is,
$$
X_{L_{P}}=X_{C}
$$
and not
$$
X_{L}=X_{C}
$$
We can therefore find the resonant frequency by,
$$
\begin{aligned}
X_{L_{P}}&=X_{C}\\
\frac{R_{L^2+}X_{L}^2}{X_{L}}&=X_{C}\\
R_{L}^2+X_{L}^2&=X_{L}X_{C}\\
R_{L}^2+(2\pi fL)^2&=(2\pi fL)\left(\frac{1}{2\pi fC}\right)\\
R_{L}^2+(2\pi fL)^2&=\frac{L}{C}\\
(2\pi fL)^2&=\frac{L}{C}-R_{L}^2\\
2\pi fL&=\sqrt{ \frac{L}{C}-R_{L}^2 }\\
f&=\frac{1}{2\pi L}\sqrt{ \frac{L}{C}-R_{L}^2 }
\end{aligned}
$$
multiplying the top and bottom of the radicand by $\displaystyle \frac{C}{L}$ ends up becoming...
$$
\begin{aligned}
f_{p}&=\frac{1}{2\pi \sqrt{ LC }}\sqrt{ 1-\frac{R_{L}^2C}{L}}\\
&=f_{s}\sqrt{ 1-\frac{R_{L}^2C}{L} }
\end{aligned}
$$
$f_{p}$ is the parallel resonance frequency. Note that the factor of $\sqrt{ 1-R_{L}^2C/L }$ will always be less than 1, meaning that $f_{p}<f_{s}$. As the inductor's internal resistance approaches 0, ($R_{L}\rightarrow 0$), the parallel resonance frequency approaches the series resonance frequency ($f_{p}\rightarrow f_{s}$).

When $f=f_{p}$, the impedance of the circuit will approach its maximum value, but it will not be its maximum value. The frequency for maximum impedance is denoted as $f_{m}$ and it will be slightly greater than $f_{p}$. This frequency is determined by [[Derivative|differentiating]] the impedance with respect to frequency and determining the frequency that sets its derivative to zero. This derivative is very complex but the solution ends up being:
$$
f_{m}=f_{s}\sqrt{ 1-\frac{1}{4}\left(\frac{R_{L}^2C}{L}\right) }
$$
Since this factor is greater than the factor for $f_{p}$, $f_{m}$ will always be greater than $f_{p}$ but still slightly less than $f_{s}$. In general then,
$$
f_{s}>f_{m}>f_{p}
$$
![[parallel-resonance-impedance.png]]
The above plot is of a parallel circuit's impedance vs frequency. Of note to me: the equation for $f_{m}$ does not appear to give the true maximum of this function. Maybe there's something wrong in my model? The result is close but off by around $300\pu{ Hz }$.
### Parallel Selectivity

From the above plot, we see that unlike in series resonance where the impedance was minimum at resonance, in parallel circuits the impedance is maximum at resonance. The impedance in a parallel resonant circuit follows the same pattern as the current did in a series resonant circuit. The quality factor of the circuit, $Q_{p}$, determines the selectivity response and the bandwidth of the circuit. The band frequencies in a parallel resonant circuit can be found by,
$$
f_{1}=\frac{1}{4\pi C}\left[-\frac{1}{R}+\sqrt{ \frac{1}{R^2}+\frac{4C}{L} }\right]
$$
$$
f_{2}=\frac{1}{4\pi C}\left[\frac{1}{R}+\sqrt{ \frac{1}{R^2}+\frac{4C}{L} }\right]
$$
The circuit quality factor $Q_{p}$ can be approximated by,
$$
Q_{p}=\frac{R_{s}||R_{p}}{X_{L_{p}}}
$$
but it can still be found using the general formula above,
$$
Q_{p}=\frac{1}{R}\sqrt{ \frac{L}{C} }
$$
If the quality factor of the coil $Q_{l}\geq 10$, some assumptions can be made to simplify circuit analysis.

|                      | **Any $Q_{l}$**                                                                       | **$Q_{l}\geq 10$**                                                                | **$Q_{l}\geq 10, R_{s}\gg Q_{l}^2R_{l}$**               |
| -------------------- | ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------- |
| $f_{p}$              | $\displaystyle f_{s}\sqrt{ 1-\frac{1}{Q^2} }$                                         | $f_{s}$                                                                           | $f_{s}$                                                 |
| $f_{m}$              | $\displaystyle f_{s}\sqrt{ 1-\frac{1}{2Q^4} }$                                        | $f_{s}$                                                                           | $f_{s}$                                                 |
| $\mathbf{Z}_{T_{p}}$ | $R_{s}\|\|R_{p}$                                                                      | $R_{S}\|\|Q_{l}^2R_{l}$                                                           | $Q_{l}^2R_{l}$                                          |
| $\mathbf{Z}_{T_{m}}$ | $R_{s}\|\|\mathbf{Z}_{R-L}\|\|\mathbf{Z}_{C}$                                         | $R_{s}\|\|Q_{l}^2R_{l}$                                                           | $Q_{l}^2R_{l}$                                          |
| $Q_{p}$              | $\displaystyle \frac{\mathbf{Z}_{T_{p}}}{X_{L_{p}}}=\frac{\mathbf{Z}_{T_{p}}}{X_{C}}$ | $\displaystyle \frac{\mathbf{Z}_{T_{p}}}{X_{L}}=\frac{\mathbf{Z}_{T_{p}}}{X_{C}}$ | $Q_{l}$                                                 |
| $BW$                 | $\displaystyle \frac{f_{p}}{Q_{p}}$ or $\displaystyle \frac{f_{m}}{Q_{p}}$            | $\displaystyle \frac{f_{p}}{Q_{p}}=\frac{f_{s}}{Q_{p}}$                           | $\displaystyle \frac{f_{p}}{Q_{p}}=\frac{f_{s}}{Q_{p}}$ |
| $I_{L}$, $I_{C}$     | Network Analysis                                                                      | $I_{L}=I_{C}=Q_{l}I_{T}$                                                          | $I_{L}=I_{C}=Q_{l}I_{T}$                                |
