---
tags:
  - physics
  - electrical-engineering
  - power-systems
---
**Power systems** are systems that handle the *generation*, *transmission*, and *distribution* of electrical power to consumers.  This system must provide a constant source of power for consumers to use, and this power has five requirements:
1. Stable voltage $\pm 10\%$.
2. Stable frequency $\pm 0.1\pu{\! Hz}$
3. Supply energy at an acceptable price
4. Comply with safety standards
5. Respect environmental standards
![[power-systems-single-line.png]]
# Generation
Electrical power systems make use of large generation stations that generate electricity by means of [[Generator|generators]]. The generated [[Voltage|voltage]] at these stations ranges from $1-30\pu{ kV}$. Ideally, the generated power must be balanced. That is, at any given moment, the power generated must be the same as the power being consumed.
$$
P_{\text{G}}=P_{\text{C}}
$$
Even something like storing power in batteries is considered *consumed* power, until that battery is used in power generation in which case it becomes part of the *generated* power. From a power systems design perspective, the generated power is what we have control over.

If this demand is not met, the load will increase and this increase in load will slow down the generator. Since in a generator, [[Angular Velocity|rotational speed]] is proportional to the output [[Frequency|frequency]], an unbalanced generation system will have a frequency that is not exactly $60\pu{ Hz}$. If the power demand exceeds the generation, the generator speed will decrease and the frequency will be less than $60\pu{ Hz}$. If, on the other hand, the generation exceeds the power demand, the generator speed will increase and the frequency will be greater than $60\pu{ Hz}$. This makes *frequency* the indicator as to whether the generated power matches the power demand.

In a given power plant, the generator's speed is monitored by a *speed regulator* or *governor*. These regulators can detect a change of $0.02\%$ in the generator's speed, or a change in frequency of about $0.012\pu{ Hz}$. 

Note that this idea of power "balancing" is a *local* job. For example, in North America all power grids are connected, but this can be thought of as the *base* power stations being connected, whereas peak and intermediate power stations are local stations that can react to local demands.
## Power Demand
The consumed power is also known as the *power demand*. The power demand is how the consumer behaves and when they require more or less power. The average daily power demand is shown below (source: ieso.ca):
![[daily-power-demand.png]]
Over time various patterns emerge from this data.
- **Base demand**. This base demand is around $1\pu{ GW}$ and is needed all the time.
- **Intermediate demand**. This demand is around $4\pu{ GW}$ and is constant for quite a bit of time but not all the time.
- **Peak demand**. This demand is around an additional $3\pu{ GW}$ but it is changing all the time and must be adjusted constantly. 

To meet these types of power demands, we have three different types of generation stations. They are named after the demand they fill: *Base station*, *Intermediate station*, and *Peak station*.
### Base-Power stations
These stations deliver full power at all times and never changes. An example of this type of power station is a [[Nuclear Power Plant|nuclear power plant]] which takes *days* to adjust their power output.
### Intermediate-Power stations
These stations respond relatively quickly to demand changes. An example of this type is a [[Hydroelectric Power Station|hydroelectric power station]].
### Peak-Power stations
These stations respond *very* quickly to changes (matter of minutes or even seconds). Examples of peak power stations are diesel engines or gas turbines (see [[Thermal Power Station|thermal power station]]). This is the main issue with fully renewable power sources: renewable sources struggle to react quickly to changes in the power demand. 
## Types of generation stations
![[ontario-generation-capacity.png]]
Above is a chart depicting the current (as of Jan. 2025) breakdown of all Ontario power generation capacity. The actual delivered power is shown below:
![[ontario-generation-output.png]]
While only making up $33\%$ of the total power generation capacity, nuclear power makes up $53\%$ of the actual generated power used in 2023. 

The most commonly used generation stations are:
- [[Hydroelectric Power Station]]
- [[Thermal Power Station]]
- [[Nuclear Power Plant]]
- [[Wind Turbine]]
- [[Solar Power Plant]]
- [[Biomass Power Station]]
# Transmission
From generation stations, electricity is transmitted via [[Transmission Line|transmission lines]] to distribution stations. Before leaving the generation station, the voltage is [[Transformer|stepped up]] to anywhere from $115\pu{ kV}$ to $800\pu{ kV}$. This high voltage serves to reduce the [[Current|current]] in transmission lines which serves 2 purposes: 1) lower current means less internal losses due to the transmission lines, and 2) lower current means smaller cables to carry that current. 
## Voltage standards
| Designation              | Value                           |
| ------------------------ | ------------------------------- |
| Low Voltage (LV)         | $<600\pu{\! V}$                 |
| Medium Voltage (MV)      | $2.4\pu{\! kV} - 69\pu{\! kV}$  |
| High Voltage (HV)        | $115\pu{ \! kV}-230\pu{ \! kV}$ |
| Extra High Voltage (EHV) | $345\pu{ \! kV}-800\pu{ \! kV}$ |
As mentioned above, higher voltages reduce losses in the transmission lines by reducing the current in the lines.
### Low voltage
In single phase, low voltage is typically $120\pu{\! V}$ or $120/240\pu{ \! V}$. In three phase, typical line voltage is $480\pu{ \! V}$ or $600\pu{ \! V}$. This is typically used for factories, homes, or commercial buildings.
### Medium voltage
Medium voltage, along with higher designations, are always three phases. Common values are: $2.4\pu{ \! kV}$, $4.16\pu{ \! kV}$, $4.8\pu{ \! kV}$, $6.9\pu{ \! kV}$, $13.8\pu{ \! kV}$, $23\pu{ \! kV}$, $27.6\pu{ \! kV}$, $34.5\pu{ \! kV}$, $46\pu{ \! kV}$, and $69\pu{ \! kV}$. In Ontario, the values used are typically $4.16\pu{ \! kV}$, $27.6\pu{ \! kV}$, and $69\pu{ \! kV}$. 

These are used in distribution subsystems, high-rise buildings, shopping centres, campuses, and factories. 
### High voltage
High voltage common values are: $115\pu{ \! kV}$, $138\pu{ \! kV}$, $161\pu{ \! kV}$, and $230\pu{ \! kV}$. In Ontario only $230\pu{ \! kV}$ is typically used. These are only used between two power systems, and between generating stations and main substations.
### Extra high voltage
Extra high voltage common values are: $345\pu{ \! kV}$, $500\pu{ \! kV}$, $735\pu{ \! kV}$ - $765\pu{ \! kV}$. In Ontario, the commonly used value is $500\pu{ \! kV}$. These are used for very long distance transmission lines.
# Distribution
Before power is sent to consumers, it arrives at distribution stations. Here, it is stepped down to anywhere from $2.4\pu{ kV}$ to $69\pu{ kV}$. This distribution voltage is what is sent to the consumers.

Similar to how generation stations monitor frequency changes for varying power demands, distribution stations also monitor frequency in case of emergencies. If extra power can not be put into the system by either increasing peak and intermediate plants or by buying power from neighbouring grids, distribution stations may need to *load shed*. This is where the distribution station cuts off power from consumers in order to balance the power generated with the power demand.
## Substations
Distribution substations are complexes that receive high voltage from transmission lines and steps it down to distribution level. In Ontario, this is typically stepping down $230\ \pu{ kV}$ to $27.6\ \pu{ kV}$.
![[distribution-transformer.jpg]]
As distribution lines send electricity to consumers, they will further step down the voltage to either $600\ \pu{ V}$ or $240\ \pu{ V}$.

At these distribution stations, there are also circuit breakers that protect the station and lines downstream from overcurrent. These circuit breakers can be of three main types: [[Oil Circuit Breaker|oil]], [[Air Blast Circuit Breaker|air blast]], or [[Vacuum Circuit Breaker|vacuum]].
![[air-blast-circuit-breaker.jpg]]
Distribution stations will further have over voltage protection in the form of [[Surge Arrester|surge arresters]]. Finally, there is additional overcurrent protection in the form of [[Current Transformer|current transformers]] and [[Relay|relays]] that, when the current in the secondary of the transformer is sufficient to energize the relay coil, it will trip the circuit breaker.
### Circuit breakers
The circuit breakers at distribution stations operate well up to a certain point. Say we have a station with a circuit breaker rated for $200\ \pu{ A}$. This breaker will operate fine for currents around its rating, but if there is a short circuit that brings the current above $4000\ \pu{ A}$, the circuit breaker may not be able to open and it will melt, fusing it closed. If this is not fixed, the transformer supplying the circuit breaker can be damaged. This is illustrated below.
![[non-limited-fault.png]]
To remedy this, we add some impedance before each circuit breaker. This impedance is, in theory, entirely reactive, because a resistive impedance would increase losses in the system.
![[limited-fault.png]]
This impedance successfully limits the fault current to a level that is manageable for the circuit breaker.
# Power Flow
![[power-systems-flow.png]]
Traditionally, power only flows in one direction: from the generation stations to the consumers. However, due to renewable options becoming more prevalent, more and more the power flow becomes bidirectional, as someone with a solar panel may generate more power than they consume, sending the remainder back to the utilities.
## Transmission regions
Within Ontario, the province is divided into various different regions that are all connected to one another. Some regions have external connections to either Quebec or Michigan or New York.
![[ontario-transmission-zones.png]]
We can simplify the circuit between two regions as 
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[vsource, l=$E_S$] ++(0,-2) to[short] ++(3,0) to[vsource, l=$E_R$] ++(0,2)
(0,0) to[L, l=$X$] ++(3,0) 
;
\end{circuitikz}
\end{document}
```
Where $E_{S}$ is the voltage source in region $S$ and $E_{R}$ is the voltage source in region $R$. These two regions have the same nominal voltage. We can use [[Phasor|phasor]] diagrams to model this as well.
![[es-er-phasor.png]]
The power transferred in this transmission line is
$$
P=\frac{E_{S}E_{R}}{X}\sin \delta
$$
where $\delta$ is the phase angle between $E_{S}$ and $E_{R}$. However, since $E_{S}=E_{R}$ we can simplify this to,
$$
P=\frac{E_{S}^2}{X}\sin \delta
$$
If there is no phase angle, i.e. $\delta=0$, then there is no power transmitted because there is now no voltage difference at any point in time between $E_{S}$ and $E_{R}$ and therefore no current $I$. We call this *synchronization*. 

If we want to send power or receive power from a given region, we can adjust $\delta$. If $E_{S}$ leads $E_{R}$, then $E_{S}$ *delivers* power to $E_{R}$. If $E_{S}$ lags $E_{R}$, then $E_{S}$ *receives* power from $E_{R}$. This is done via a [[Phase Shift Transformer|phase shift transformer]].

As we increase the phase angle we increase the amount of power transferred. 
![[phase-shift-power-plot.png]]
While power transferred is maximum at $90\degree$, we realistically never operate above $60\degree$, but commonly it is operated at around $30\degree$. At $\delta=30\degree$ we can see that $50\%$ of power is transferred, which is typically sufficient.