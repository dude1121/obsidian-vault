---
tags:
  - telecommunications
  - electrical-engineering
  - power-systems
---
A **transmission line** is a means of transferring [[Energy|energy]] between [[Communication System|system]] elements that are carrying signal power. In essence, transmission lines are simply [[Wire|wires]], but at [[Radio|radio frequencies]] the conductors behave differently than at typical frequencies. For example, at high frequencies, the stray [[Inductance|inductances]] and [[Capacitance|capacitances]] that were negligible at low frequencies now become important. If the [[Impedance|impedances]] at either end of the transmission line are mismatched, then signals can be reflected back towards the source. This makes the concept of [[Impedance Matching|impedance matching]] very important in telecommunications.

Transmission lines are also used in [[Power Systems|power systems]] as a means of distributing power from generation to transmission to distribution. These transmission lines are much different from their telecommunication counterpart but they essentially serve the same purpose.
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

