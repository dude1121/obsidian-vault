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
In this lumped circuit model, the resistance $R$ represents the power losses of the power line, since only the resistance can dissipate real power. The inductor represents the absorbed [[Reactive Power|reactive power]] $Q_{L}$ whereas the capacitor represents the delivered reactive power $Q_{C}$. These power values can be found by,
$$
\begin{align}
P_{J}=I^2R&&Q_{L}=I^2X_{L}&&Q_{C}=\frac{E^2}{X_{C}}
\end{align}
$$
In some cases as discussed below, $P_{J}$ and $Q_{C}$ are so small that they become negligible and can be ignored for analysis purposes.

>[!question] Example
>A 3-$\Phi$ transmission line delivers $300\ \pu{ MW }$ to a $3-\Phi$ load. Its parameters are: $R=3.25\ \Omega$, $X_{L}=25\ \Omega$, and $X_{C}=6\ \pu{ k}\Omega$. The line voltage at both ends is $230\ \pu{ kV}$. Determine:
>a) the active and reactive power associated with the line
>b) the approximate equivalent circuit per phase
>
>a) Per phase:
>$P_{\Phi}=\frac{300\ \pu{ MW}}{3}=100\ \pu{ MW}$
>$E_{\Phi}=\frac{E_{L}}{\sqrt{ 3}}=\frac{230\ \pu{ kV}}{\sqrt{ 3 }}=132.791\ \pu{ kV}$
>$I_{\Phi}=\frac{P_{\Phi}}{E_{\Phi}}=\frac{100\ \pu{ MW}}{132.791\ \pu{ kV}}=753.066\ \pu{ A}$
>$P_{J}=I^2R=(753.066\ \pu{ A})^2(3.25\ \Omega)\boxed{=1.843\ \pu{ MW}}$
>$Q_{L}=I^2X_{L}=(753.066\ \pu{ A})^2(25\ \Omega)\boxed{=14.178\ \pu{ MVAR_{L}}}$
>$Q_{C}=\frac{E^2}{X_{C}}=\frac{132.791\ \pu{ kV}^2}{6\ \pu{ k}\Omega}\boxed{=2.939\ \pu{ MVAR_{C}}}$

### Short low voltage line
In a short, low [[Voltage|voltage]] transmission line, we can simplify the lumped circuit. Since $Q_{C}=\frac{E^2}{X_{C}}$ and $X_{C}=\frac{x_{C}}{l}$ and both $l$ and $E$ are relatively small values here, we can ignore the reactive power.
### Long high voltage line
In a long, high voltage transmission line, we can also simplify the lumped circuit. In this case, we use high voltage in power transmission lines such that the [[Current|current]] is very small. This means that, since $P_{J}=I^2R$ and $R$ is already going to be a very small value, the real losses of the line are going to be negligible. 
## Simplified transmission line
Since we can cut the resistive and capacitive portions under different conditions, we can make the transmission circuit even simpler by removing the resistance and capacitance entirely. This makes our circuit,
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[vsource, l=$E_S$] ++(0,-3)
(0,0) to[L, l=$X_L$] ++(3,0) to[generic, l=Load, v<=$E_R$] ++(0,-3) to[short] (0,-3) 
;
\end{circuitikz}
\end{document}
```
The difference between $E_{S}$ and $E_{R}$ will be the voltage drop on the transmission line due to the inductance. While drawn as a static resistor here, we recognize that this load "resistance" is always changing. To analyze the power that can be delivered by a given transmission line, we can analyze this circuit for varying levels of $R$.
![[max-power-transmission-line.png]]
From the above plot we see that the power is maximum when the load resistance is equivalent to the line reactance. This is the principle of [[Maximum Power Transfer|maximum power transfer]]. When this occurs, the voltage at the load will be less than the source voltage by a factor of $\sqrt{ 2}$. That is, at maximum power
$$
E_{R}=\frac{E_{S}}{\sqrt{ 2 }}
$$
This is interesting because it means that the maximum power of a line is determined by the source voltage and the length of the cable, not the cable itself. Specifically, the maximum power is determined by,
$$
P_{\ \text{max}}=\frac{E_{S}^2}{2X_{L}}
$$
## Compensation capacitors
As noted above we can model a transmission line as a simple [[Inductor|inductor]], neglecting the stray [[Capacitance|capacitance]] and [[Resistance|resistance]] present in the line, since it is the line's [[Inductance|inductance]] that has the greatest impact on the line's performance. 

This inductance is still not desired in the line since it introduces a [[Phase Shift|phase shift]] into the transmission line, and it reduces the load voltage $E_{R}$ down to about $70\%$ of the generated voltage value $E_{S}$. It is this voltage drop that is especially undesirable that needs to be compensated for.  

To account for this, we can add a capacitor in parallel with the load that corrects the [[Power Factor|power factor]] to increase the load voltage.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[vsource, l=$E_S$] ++(0,-3)
(0,0) to[L, l=$X_L$] ++(3,0) node[circ](A){} to[short] ++(2,0) to[generic, l=Load, v<=$E_R$] ++(0,-3) to[short] (0,-3) 
(A) to[vC, l_=$C$, invert, mirror] ++(0,-3) node[circ]{}
;
\end{circuitikz}
\end{document}
```
As denoted in the circuit diagram, the capacitor is variable. This allows it to be adjusted to react to changes in the inductance of the line. Adding this capacitor causes it to deliver the [[Reactive Power|reactive power]] stored by the line's inductance. 

In theory the capacitor should deliver *all* the reactive power stored by the line. But in reality this is not necessary. If we design our capacitor to deliver at least half of the stored reactive power, this will be sufficient to correct the load voltage. This is because in designing the transmission system we assume that the source takes care of the other half. Not only that, but adding a compensating capacitor will increase the maximum power rating of the line, given by
$$
P_{\ \text{max}}=\frac{E_{S}^2}{X}
$$
The reactive power supplied by the capacitor is,
$$
Q_{c}=\frac{E_{R}^2}{X_{C}}
$$
The absorbed reactive power by the line inductance is given by,
$$
Q_{L}=I^2X_{L}
$$
We can select our capacitor size by sizing it such that
$$
Q_{C}=\frac{Q_{L}}{2}
$$
>[!question] Example
>A single-phase transmission line has an inductive reactance of $10\ \Omega$. The source voltage is $1000\ \pu{ V}$. If it is fully compensated, calculate:
>a) The maximum active power that can be delivered to a resistive load
>b) The $X_{C}$ that must be installed for maximum power
>c) The $X_{C}$ that must be installed for $40\ \pu{ kW}$.
>
>a) $P_{\ \text{max}}=\frac{E_{S}^2}{X_{L}}=\frac{1000\ \pu{ V}^2}{10\ \Omega}\boxed{=100\ \pu{ kW}}$
>b) $I_{R}=\frac{P}{E_{R}}=\frac{100\ \pu{ kW}}{1000\ \pu{ V}}=100\ \pu{ A}$
>$\mathbf{I}=\mathbf{I}_{C}+\mathbf{I}_{R}=I_{C}^2+I_{R}^2=I_{C}^2+100\ \pu{ A}^2$
>$Q_{L}=I^2X_{L}=(I_{C}^2+100\ \pu{ A}^2) \cdot 10=10I_{C}^2+100\ 000$
>$Q_{C}=E_{R}I_{C}=1000I_{C}$
>Under full compensation:
>$Q_{C}=\frac{1}{2}Q_{L} \to 1000I_{C}^2=\frac{1}{2}(10I_{C}^2+100\ 000)$
>Solving the quadratic equation gives us
>$I_{C}=100\ \pu{ A}$
>$X_{C}=\frac{E_{C}}{I_{C}}=\frac{1000\ \pu{ V}}{100\ \pu{ A}}\boxed{=10\ \Omega}$
>
## Voltage rating for transmission lines
We discussed above that for a non-compensated line, the maximum power can be found by 
$$
P_{\text{max}}=\frac{E_{S}^2}{2X}
$$
and in a compensated line,
$$
P_{\text{max}}=\frac{E_{S}^2}{X}
$$
We can generalize this and define our max power as,
$$
P_{\text{max}}=\frac{E_{S}^2}{cX}
$$
where $c=1$ for compensated lines and $c=2$ for uncompensated lines. We can simplify by remembering that $X=xl$ and solve for the voltage.
$$
\begin{align}
P_{\text{max}}&=\frac{E_{S}^2}{cxl} \\
E_{S}^2&=cxlP_{\text{max}} \\
E_{S}&=\sqrt{ cxlP_{\text{max}} } \\
E_{L}=\sqrt{ 3 }E_{S}&=\sqrt{ 3 }\cdot\sqrt{ cxlP_{\text{max}} }\ \boxed{=k\sqrt{ Pl }} \\
\end{align}
$$
where $k$ converts the other terms into one coefficient. Due to engineering magic, this value is typically either $k=0.1$ for uncompensated lines and $k=0.06$ for compensated lines. When establishing the line voltage for a transmission line, we typically state the voltage within a range where the minimum voltage $E_{\text{min}}=0.6E$ and the maximum voltage $E_{\text{max}}=1.5E$. These ranges help an engineer to determine the standard voltage rating. 
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

