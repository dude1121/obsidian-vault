---
tags:
  - physics
  - electromagnetism
---
A **magnetic circuit** is a circuit that consists of a magnetic source (typically a [[Solenoid|solenoid]] of some sort) coupled to a ferromagnetic core of some uniform or varying material. Magnetic circuits can be thought of as parallels to electrical circuits in many ways.

The source [[Magnetomotive Force|magnetomotive force]] (mmf) can be thought of as a [[Voltage Sources|voltage source]] where the mmf $\mathcal{F}$ is akin to the source voltage $E$. The mmf induces [[Magnetic Flux|magnetic flux]] in the material $\Phi$ which is similar to the [[Current|current]] induced in a conductor. This flux is proportional to the mmf and inversely proportional to the [[Reluctance|reluctance]] $\mathcal{R}$ of the material, which is a parallel to [[Resistance|resistance]]. Whereas in an electrical circuit there is a voltage drop across some load, in a magnetic circuit this "drop" can be thought of as the [[Magnetizing Force|magnetizing force]] $H$. 

These concepts bring about a set of equations for analyzing magnetic circuits:

$$
\begin{aligned}
\mathcal{F}&=NI&\mathcal{F}&=\Phi \mathcal{R}&\mathcal{F}&=H\ell&\Sigma_{\circlearrowright}\mathcal{F}&=0
\end{aligned}
$$
The first equation is similar to if the voltage source is dependent, where $N$ and $I$ are the factors the source is dependant on. The second is [[Ohm's Law|Ohm's law for magnetic circuits]]. The third has no real analogue to electrical circuits but it is a way of making the magnetizing force and mmf equal, with the length of the material the proportionality constant. The fourth relationship is essentially [[Kirchhoff’s Voltage Law|Kirchhoff's voltage law]].

For analysis purposes, we can draw a magnetic circuit in a way that resembles its electrical counterpart.
![[magnetic-circuit.png]] ![[magnetic-circuit-diagram.png]]

A [[Transformer|transformer]] can be represented as a magnetic circuit.
![[transformer-magnetic-circuit.png]]
Knowing the properties of the core of a transformer allows us to make more accurate predictions for a transformer's behaviour by analyzing it as a magnetic circuit.