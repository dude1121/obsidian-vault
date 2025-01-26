---
tags:
  - physics
  - electrical-engineering
---
![[electromechanical-relay.jpg]]
An **relay** is a device that allows a small control [[Current|current]] to control a much larger current. It is an electrically operated switch and consists of a coil (through which the control current flows) and a set of contacts (through which the main current flows). Relays are often described by the number of different inputs (poles) and the number of outputs from those inputs (throws). 
![[types-of-relays.png]]
In the examples above, $Y$ outputs are called *normally open*, because they will be open when the coil is not energized. The $Z$ outputs are *normally closed* since they are closed when the coil is not energized.

Relays are used for switching contacts in a circuit. More recently, relays have fallen out of favour in place of [[Solid state relay|solid state relays]] or [[Transistor|transistors]] which are cheaper, less noisy, and can switch much faster than relays. 
# Operation
When a current is passed through the coil, it generates a [[Magnetic Field|magnetic field]]. This magnetic field pulls the contact closed (or open, if the contact is *normally closed*). This allows us to control the flow of current indirectly by powering the coil.
## Flyback diode
Since the coil is essentially an [[Inductor|inductor]], when the coil is de-energized it will begin discharging. If there is nothing in place to dissipate this large [[Voltage|voltage]] spike, the high current from the coil could damage other components in the circuit. To prevent this, a relay is typically coupled with a [[Diode|diode]] in parallel, called a *flyback diode*, that is oriented so that in normal operation the diode is reverse-biased, but when the inductor discharges the current flows through the diode and back into the inductor, allowing it to discharge safely.
# Parameters
The main parameters a designer should keep in mind is the voltage and [[Resistance|resistance]] of the coil, as well as the voltage and current ratings for the contacts, which should be ideally $\geq$ the design value.