---
tags:
  - physics
  - electrical-engineering
  - semiconductors
---
A **solid state relay** is an electrical switch that is similar in principle to a [[Relay|electromechanical relay]] but contains no moving parts and last much longer. A solid state relay typically makes use of optical coupling (lending it to sometimes be called an **optocoupler**) by having an [[LED]] emit [[Infrared|infrared]] light onto a [[Phototransistor|phototransistor]] that biases the transistor, allowing current to flow through its terminals.

SSRs can switch much quicker than EM relays and are completely silent.
# Parameters
- *Trigger LED current* $I_{\text{FT}}$. This is the current to turn on the internal LED. The design value should be about double the datasheet value, since we want the LED to be fully on.