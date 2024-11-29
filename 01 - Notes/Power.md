---
tags:
  - physics
---
Power is the time rate of [[Energy|energy]] transfer and it is defined as
$$
	\mathscr{P}=\frac{dE}{dt}=\dot{E}
$$
In some branches of physics, power is denoted with a scripted $\mathscr{P}$ as above, but in fields like electricity it is often denoted as a normal $P$. The [[Units of Measurement|unit]] of power is the [[Watt]] \[$\text{W}$] which is defined as 
$$
	1\text{W}=1\text{J}\cdot\text{s}^{-1}=1\text{kg}\cdot\text{m}^2\cdot\text{s}^{-3}
$$
## Electromagnetism

Recall that a [[Volts|volt]] is defined as:
$$
	V=\frac{W}{Q}=\frac{\text{[J]}}{\text{[C]}}
$$
Also recall that an [[Amperes|amp]] is defined as:
$$
	I=\frac{dQ}{dt}=\frac{\text{[C]}}{\text{[s]}}
$$
If we multiply volts and amps together we get
$$
	VI=\frac{\text{[J][C]}}{\text{[C][s]}}=\frac{\text{[J]}}{\text{[s]}}=\text{[W]}
$$
Therefore, by means of dimensional analysis, we find our first equation for power, namely,
$$ P=VI $$
Power is therefore proportional to voltage and current. This relationship is known as _[[Joule’s Law]]_. But, due to [[Ohm's Law]] we know that $I=V/R$. We can therefore further derive that,
$$ P=\frac{V^2}{R} $$
and since $V=IR$,
$$ P=I^2R $$
Returning to this circuit from [[Ohm's Law]],
![[Ohm's Law Circuit.png]]
we are now able to calculate the power dissipated by the [[Resistor|resistor]] $R_1$.
$$ P=\frac{V^2}{R}=\frac{12\text{V}^2}{1\text{k}\Omega}=144\text{mW} $$
In the case of an electrical circuit, this power represents the amount of energy lost from the circuit due to [[Heat|heat]]. 

Let’s say that this circuit was powered for 3 hours. How much energy did the resistor consume? We can find this by multiplying the power dissipated by the time for which it was energized.

$$ E=Pt=(144\text{mW})(10\text{h})=1.44\text{Wh} $$

Typically, energy is measured in Joules \[$\text{J}$], but in the case of electrical components we tend to use the unit Watt-hours \[$\text{W}\cdot \text{h}$]. This is often seen in the case of utility bills, where consumers are charged based on their kilowatt-hour consumption.

In ac applications, power becomes more complicated, and is often split into three types: *[[Real Power]]* $P$, *[[Reactive Power]]* $Q$, and *[[Apparent Power]]* $S$. They are related by what is often called the *power triangle*.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[short, l_=$P$] (4,0)
(0,0) to[short, l=$Q$] (0, 3)
(0,3) to[short, l=$S$] (4,0)
;
\end{circuitikz}
\end{document}
```
This means that all relationships that hold for basic right angle triangles hold for these types of power.
$$
S^2=P^2+Q^2
$$
The angle between $P$ and $S$ is the [[Power Factor|power factor]] angle. 
$$
\cos \theta=\frac{P}{S}
$$
$S$ can also be found as the [[vector sum]] of $P$ and $Q$.
$$
\vec{S}=\vec{P}+\vec{Q}
$$
Notably, in ac circuits most power values are assumed to be the *average* value, given by using [[Root Mean Square|rms]] values in its calculation.
$$
P_{avg}=V_{rms}I_{rms}
$$
Power factor is accounted for by adding $\cos \theta$ to the end.
$$
P_{avg}=V_{rms}I_{rms}\cos \theta
$$
