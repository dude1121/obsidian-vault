---
tags:
  - ohms-law
  - ohms
  - resistance
  - voltage
  - current
  - resistor
  - battery
  - source
  - load
  - electromagnetism
  - circuit-analysis
  - physics
---
**Ohm's Law** (named after [[Georg Ohm]]) states that the [[current]] through a conductor between two points is proportional to the [[voltage]] across the two points and inversely proportional to the [[resistance]] through the two points.
$$
I\propto VR^{-1}
$$
In other words,
$$
\begin{aligned}
I&=\frac{V}{R}&V&=IR&R&=\frac{V}{I}
\end{aligned}
$$


# Circuit Analysis

Consider the simple circuit below.

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=$E_{S1}$, a=$12$V] (0,-2)
(0,0) to[short, f=$I_1$] (4,0)
to[R, l_=$R_1$, a^=$1$k$\Omega$, v<=$V_{R1}$, voltage shift=4] (4,-2)
(4,-2) -- (0,-2) node[ground]{}
;
\end{circuitikz}
\end{document}
```

In this circuit, we have a **[[Voltage Sources|source]]**, the [[Battery|battery]], and a **load**, the [[Resistor|resistor]]. The source, denoted as $E_{S1}$, provides an _[[Electromotive Force]]_ to the circuit (which is why we use $E$ to denote the source) and this force induces a voltage across the source and a current in the conductor and through the load.

We can use Ohm’s Law to find the current through the circuit and the voltage across the resistor.
$$
\begin{aligned}
I_1&=\frac{E_{S1}}{R_1}\\
&=\frac{12\text{V}}{1\text{k}\Omega}\\
&=12\text{mA}
\end{aligned}
$$
$$
\begin{aligned}
V_{R1}&=I_1R_1\\&=(12\text{mA})(1\text{k}\Omega)\\&=12\text{V}
\end{aligned}
$$
## AC Circuits

In an [[AC Electricity|ac circuit]], we can use [[phasor]] values and Ohm's Law still holds. Instead of resistance, however, we use [[impedance]].
$$
\begin{aligned}
\mathbf{I}&=\frac{\mathbf{V}}{\mathbf{Z}}&\mathbf{V}&=\mathbf{IZ}&\mathbf{Z}=\frac{\mathbf{V}}{\mathbf{I}}
\end{aligned}
$$

# Electrodynamics

Ohm's Law has a much more robust definition than the one typically used in circuit analysis. This reformulation states:
$$
\mathbf{J}=\sigma \mathbf{E}
$$
where $\mathbf{J}$ is the [[Current Density|current density]] at a given location, $\sigma$ is the material's [[Conductance|conductivity]], and $\mathbf{E}$ is the [[Electric Field|electric field]].