---
tags:
  - circuit-analysis
  - electromagnetism
  - physics
  - components
  - resistor
  - resistance
  - resistivity
  - ohms
  - rheostat
  - potentiometer
---
A **Resistor** is a two-terminal component that provides [[Resistance|resistance]] to an electrical circuit. Resistors can be manufactured to have a wide range of resistances and a wide range of [[Power|power]] ratings. Resistors can be fixed or variable. A variable resistor is typically called a *rheostat* which can have its resistance altered manually, but there are also *thermistors* that have their resistance altered by temperature, and *photoconductive cells* which can vary their resistance based on the amount of light they are exposed to. Thermistors and photoconductive cells are not strictly-speaking "resistors" and instead fall under the category of [[Semiconductor|semiconductors]]. 

A three-terminal variable resistor may also be called a *potentiometer*, or "pot". Potentiometers have two terminals on each end of the resistor as normal, but have a third "sweeper" arm that can move along the resistor to vary the resistance between the middle leg and either of the two end terminals.

# Behaviour

## DC Circuits

Resistors are the only source of opposition in a dc circuit. They impact the circuit according to [[Ohm's Law]].

## AC Circuits

In an ac circuit, ideal resistors do not introduce any sort of [[Phase Shift|phase shift]] between the applied current and resulting current. That is,
$$
\theta_{v}=\theta_{i}
$$
This means that the power dissipated by a resistor is entirely [[Real Power|real]] with no [[Reactive Power|reactive]] component. This also means that the [[Impedance|impedance]] of a resistor is purely real with no imaginary component (i.e. $X_{R}=0\Omega$).

### Frequency Response

For [[Frequency|frequencies]] up to a few hundred $\text{kHz}$, resistance is unaffected by frequency. The resistor can be treated as a constant. However, due to a resistor's construction there is some stray capacitance and impedance that becomes an issue at higher frequencies. Resistors with a higher resistance will have a more drastic response at lower frequencies. 
![[resistor-frequency.png]]
A $100\Omega$ resistor is essentially stable up until $f=300\text{MHz}$ whereas a $100\text{k}\Omega$ resistor will begin to drop off around $f=15\text{MHz}$. 