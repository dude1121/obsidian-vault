---
tags:
  - telecommunications
  - electrical-engineering
  - power-systems
---
A **transmission line** is a means of transferring [[Energy|energy]] between [[Communication System|system]] elements that are carrying signal power. In essence, transmission lines are simply [[Wire|wires]], but at [[Radio|radio frequencies]] the conductors behave differently than at typical frequencies. For example, at high frequencies, the stray [[Inductance|inductances]] and [[Capacitance|capacitances]] that were negligible at low frequencies now become important. If the [[Impedance|impedances]] at either end of the transmission line are mismatched, then signals can be reflected back towards the source. This makes the concept of [[Impedance Matching|impedance matching]] very important in telecommunications.

Transmission lines are also used in [[Power Systems|power systems]] as a means of distributing power from generation to transmission to distribution. These transmission lines are much different from their telecommunication counterpart but they essentially serve the same purpose.
# Equivalent circuit
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\ctikzset{resistors/scale=0.5}
\ctikzset{inductors/scale=0.5}
\ctikzset{capacitors/scale=0.5}
\draw
(0,0) node[ocirc](A){} to[L, l=$x_L$] ++(1,0) to[R, l=$r$] ++(1,0) node[circ](B){}

(A) ++(0,-2) node[ocirc](C){} to[short] ++(2,0) node[circ](D){}

(B) to[cC, l=$x_C$] (D)

(B) to[L] ++(1,0) to[R] ++(1,0) node[circ](E){}
(D) to[short] ++(2,0) node[circ](F){}
(E) to[cC] (F)

(E) to[L] ++(1,0) to[R] ++(1,0) node[circ](G){}
(F) to[short] ++(2,0) node[circ](H){}
(G) to[cC] (H)

(G) to[short] ++(1,0) node[ocirc]{}
(H) to[short] ++(1,0) node[ocirc]{}
;
\end{circuitikz}
\end{document}
```
A transmission line can be modelled as above, with each RLC combination representing one kilometre of a transmission. The top of this circuit represents the line itself, and the bottom is the neutral line. In reality, this transmission model would extend to all three phases but we only really need to model one of them, knowing it extends to the other two phases.

This model represents the losses in the transmission line due to stray [[Reactance|reactance]] and [[Resistance|resistance]]. Typical reactance values for power transmission lines are,

| Type of Line | $X_{L}\ [\pu{ \Omega / km}]$ | $X_{C}\ [\pu{ \Omega \cdot km}]$ |
| ------------ | ---------------------------- | -------------------------------- |
| Aerial       | $0.5$                        | $300\ 000$                       |
| Underground  | $0.1$                        | $3\ 000$                         |
The typical reactances are listed in different units because the inductors and capacitors are "connected" in different configurations. Typical resistance values for power transmission lines are,

| [[American Wire Gauge\|AWG]] | [[Copper]] $[\pu{ \Omega/km}]$ | [[ACSR]] $[\pu{ \Omega/km}]$ |
| ---------------------------- | ------------------------------ | ---------------------------- |
| $1$                          | $0.5$                          | $0.9$                        |
| $3/0$                        | $0.25$                         | $0.47$                       |
| $300\ \pu{ kcmil}$           | $0.14$                         | $0.22$                       |
| $600 \ \pu{ kcmil}$          | $0.072$                        | $0.11$                       |
| $1000\ \pu{ kcmil}$          | $0.045$                        | $0.065$                      |
## Lumped circuit
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[ocirc](A){} to[short] ++(1,0) node[circ](E){} to[L, l=$X_L$] ++(2,0) to[R, l=$R$] ++(2,0) node[circ](B){} to[short] ++(1,0) node[ocirc]{}

(A) ++(0,-2) node[ocirc](C){} to[short] ++(1,0) node[circ](D){} to[short] ++(4,0) node[circ](F){} to[short] ++(1,0) node[ocirc]{}

(E) to[cC, l=$2\ X_C$] (D)

(B) to[cC, l=$2\ X_C$] (F)
;
\end{circuitikz}
\end{document}
```
To make analysis easier, we lump together the reactance and resistance of a large power line using the values above. The three values are given by,
$$
\begin{align}
R=rl&&X_{L}=x_{L}\ l&&X_{C}=\frac{x_{C}}{l}
\end{align}
$$
# Power transmission lines
## High voltage transmission lines
High voltage transmission lines transmit power with voltages anywhere from $115\pu{\! kV}$ to $800\pu{ \! kV}$. They are carried by large towers (sometimes called *pylons*) that keep the lines far away from one another to prevent arcing.
![[Transmission_tower.jpg]]
High voltage transmission lines are not the same as typical power cables of either solid or stranded [[Copper|copper]]. Instead, these lines use [[ACSR|ACSR cable]] ([[Aluminum]] Cable [[Steel]] Reinforced) which is a high-capacity, high-strength stranded conductor. It is made up of many strands of high-purity aluminum with a core of steel strands to give the cable strength. These cables do not have insulation as introducing a dielectric at such a high voltage would induce losses due to [[Reactance|reactance]].
![[acsr.png]]
These cables are preferred to copper because copper is more expensive than aluminum and is heavier than aluminum.
### Insulator
Although the ACSR cable does not have its own insulators, the transmission line still needs some sort of [[Insulator|insulator]] to connect the line to the tower that is supporting it.
![[suspension-string-insulator.jpg]]
These insulators are made of glass, porcelain, or fibreglass. They not only need to electrically isolate the support tower from the conductor but also mechanically support the cable.  There are three main types of these isolators: *pin-type*, *suspension-type*, and *polymer disc*.
#### Pin-type
![[pin-insulator.jpg]]
These insulators are typically ceramic. They have a slot on the top where the cable would sit along with a screw at the bottom that bolts the insulator to the support tower. These insulators can only be used up to $70\pu{ \! kV}$. 
#### Suspension-type
A suspension-type insulator is a series of insulator caps that look similar to a series of pin-type insulators stacked on top of one another. On its own, one suspension-type insulator can withstand $50\pu{ \! kV}$, but this rating can be increased by adding more insulators in series.
#### Polymer disc
A polymer disc insulator is like the best of both worlds of the suspension-type and pin-type insulators. It is the type pictured above. Unlike the suspension type, the polymer disc type insulators are not modular and their size must be determined when they are manufactured. However, these insulators can have a much higher voltage rating for much less material, ranging anywhere from $10\pu{ \! kV }-800\pu{ \! kV}$. 
![[polymer-disc.jpeg]]
Often times, more discs than necessary are used in the event one or two are damaged or dirtied, thereby making the insulation less effective.
#### Insulator voltage ratings
The voltage ratings for these types of insulators will consist of two primary values: the *rated voltage*, and the *basic impulse isolation level (BIL)*. The rated voltage is the [[Root Mean Square|rms]] voltage level that the insulator can withstand at a given frequency (in North America, $f=60\pu{ \! Hz}$). The basic impulse isolation level is the peak value of applied [[DC Electricity|dc]] impulse before the insulator breaks down. This value represents the absolute maximum voltage the insulator could withstand in the event of over-voltage conditions, such as [[Lightning|lightning]] strikes.
### Galloping lines
When wind acts on dangling transmission lines, the lines begin to sway back and forth. If they sway too much, they put too much stress on the insulators keeping them in place. We call lines in this state *galloping lines*. To avoid galloping lines, we add anti-galloping dampers (sometimes called *arresters*) to the power lines.
![[arrester.jpeg]]
### Corona discharge
When two high voltage lines are close to one another, the large potential difference between the lines can cause the air between conductors to be ionized in an phenomenon known as [[Corona Discharge|corona discharge]].  These discharges create losses in the transmission lines and can result in damage to the conductors and annoying noises audible to those nearby.

To solve this issue, there are two solutions. Either the conductor diameter can be increased, or the conductors can be "bundled" together, reducing the potential carried by each individual conductor.
![[bundled-conductor.jpg]]
In Ontario, $500\pu{ \! kV}$ lines are typically bundled and $230\pu{ \! kV}$ lines have their diameter increased.
### Lightning
When [[Lightning|lightning]] strikes a power line this causes the transmission line to carry more voltage than it is rated for. The lightning also ionizes the air surrounding the transmission line, creating a path to ground. This will cause the transmission line to discharge to ground. While the lightning strike itself only lasts for around $50\pu{\! \mu s }$, the path created by the lightning lasts for longer than that. This means that the current through the line will increase as it discharges, causing a breaker to trip approximately $0.07\pu{\! s}$ after the lightning strike.
![[lightning-strike-transmission-line.png]]
When lightning strikes the power line, a sort of "shockwave" of voltage is sent out in either direction along the line. The peak of this wave is much shorter than the tail, as shown above. When the wave reaches the lightning arrestor, the circuit is opened. 
## Medium voltage transmission lines

# Radio transmission lines
![[Parallel Two-Wire Line]]

