---
tags:
  - electromagnetism
  - physics
  - circuit-analysis
  - source
---
For circuit analysis purposes, it is often useful to switch between [[Voltage Sources|voltage sources]] and [[Current Sources|current sources]]. We can use **source conversion** to accomplish this, and all we really need is [[Ohm's Law]]. 
![[Source Conversion.png]]
# Voltage to Current
To convert from a voltage source to a current source, the voltage source must be in series with some sort of [[resistance]] or [[Impedance|impedance]]. The resulting current source can be found by,
$$
	I_{ES1}=\frac{E_{S1}}{R_S}
$$
where $R_S$ is the series resistance. In the example above, the equivalent current source to the voltage source on the right is given by,
$$
	I_{ES1}=\frac{15\text{V}}{500\Omega}=30\text{mA}
$$
The resistance that was in series previously is now put in parallel with the new current source. 

# Current to Voltage
To convert from a current source to a voltage source, the current source must be in parallel with some resistance or impedance. The resulting voltage source can be found by,
$$
	E_{IS1}=I_{S1}R_P
$$
where $R_P$ is the parallel resistance. Above, we can find the equivalent voltage source by,
$$
	E_{IS1}=(30\text{mA})(500\Omega)=15\text{V}
$$
The resistance that was in parallel prior now going in series with the new voltage source. 