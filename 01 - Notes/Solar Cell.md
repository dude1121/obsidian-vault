---
tags:
  - electronics
  - electromagnetism
  - solar
  - physics
  - components
---
A **solar cell** is a type of semiconductor that converts sunlight into [[Voltage|electrical potential]]. A [[Silicon|silicon]] solar cell consists of a thin wafer that has been doped to create a [[PN Junction|pn junction]]. The *n*-region of the wafer is much thinner than the *p*-region to allow for [[Light|light]] to penetrate the silicon. The construction is detailed below.
![[Solar-cell.png]]
# Operating Principle
Sunlight is composed of [[Photon|photons]]. When a photon penetrates either the *n*-region or the *p*-region of the solar cell and strikes a silicon [[Atom|atom]] near the pn junction, it can knock the [[Electron|electron]] out of its orbit, promoting it from a valence electron to a conduction (or, free) electron. This leaves a [[Hole Current|hole]] in the valence band. Since the two regions are doped, the newly free electrons gather in the *n*-region and the holes gather in the *p*-region. This causes a voltage to develop across the depletion region of the solar cell. 
![[solar-cells-operation.png]]
When a load is connected across the cell, the free electrons flow out of the *n*-region and into the load.
## I-V Curve
![[pv-cell-i-v-curve.png]]
For all intents and purposes, all solar cells will follow this same I-V curve. The point at  MPP is the *maximum power point* and it is the ideal operation point for the solar cell since it generates the maximum amount of power, $P_{\ \text{MPP}}$. 

The above curve is based on the assumption that the [[Irradiance|irradiance]] of the sunlight is $G_{\text{m}}=1\pu{ kW/m^2}$. For varying levels of irradiance we get a family of curves that describe the PV cell.
![[curve-of-solar-Cell-under-Different-illumination.png]]
The other factor that affects the solar cell performance is the ambient temperature of the cell.
![[Temperature-effects-on-the-I-V-curve-of-a-PV-cell.png]]
## Power and Efficiency
The output [[Power|power]] of a solar cell is simply its output voltage times the output current.
$$
P_{\text{o}}=EI
$$
The input power is the power of the sunlight that strikes the panel. Since irradiance is power over [[Area|area]], the input power is,
$$
P_{\text{in}}=G_{m}A
$$
# Applications
A single solar cell can only produce about $E\approx 0.5\pu{ V}$. To make solar generation viable, the cells are arranged into large arrays, with each cell in series with one another, to produce a larger voltage. These arrays are called [[Solar Panel|solar panels]] and a large array of solar panels form a [[Solar Power Plant|solar power plant]] or solar farm.