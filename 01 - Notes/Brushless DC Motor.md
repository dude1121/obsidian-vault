---
tags:
  - physics
  - electrical-machines
  - electrical-engineering
  - electromagnetism
---
A **brushless dc motor** is a special type of [[Motor|motor]] and [[DC Machine|dc machine]]. It differs from its brushed counterpart in that it has no brushes attached to a [[Commutator|commutator]] that converts a [[DC Electricity|dc]] [[Voltage|voltage]] into an [[AC Electricity|ac]] waveform that allows the motor to operate. 
![[brushless-dc-motor.png]]
Instead, a BLDC requires an electronic controller to send pulses to the various poles within the motor. A [[Hall Effect Sensor|hall effect sensor]] is typically used to sense the position of the rotor, therefore determining when to send the next pulse. The width of these pulses can be varied to change the motor's speed (see [[Pulse Width Modulation]]).
![[brushless-dc-controller.png]]
The above circuit is a sample controller for a brushless dc motor. As the rotor spins, the hall effect sensor detects the change in the magnetic field, sending a pulse to $Q_{1}$ and allowing coil $A$ to energize, de-energizing coil $B$ by shorting out $Q_{2}$. 

Technically speaking, a brushless dc motor is a [[Synchronous Machine|synchronous motor]] with a permanent magnet in the rotor. 

As the controller turns on each coil, the rotor essentially "chases" the magnetic field. BLDCs can be either outrunners (the rotor is the exterior casing) or inrunners (the rotor is inside the casing). 

When compared to typical brushed dc motors, BLDCs have a few advantages. Their rotor sizes are typically smaller due to BLDCs not requiring a commutator, brushes, or field windings. BLDCs have lower [[Moment of Inertia|inertia]], meaning they react much quicker to changes in speed. Their speed capacity and [[Torque|torque]] capability is greater as well. Since there are fewer parts, BLDCs typically have a lower maintenance cost and are overall more reliable than their brushed counterparts.

When compared to [[Induction Machine|induction motors]], BLDCs are more efficient, have higher [[Power|power]] and torque density, and operate at lower temperatures.

However, there are some disadvantages. Neither brushed dc motors nor induction motors require the complex power electronics that BLDCs require, making BLDCs more expensive up front. An accidental overload or fault can cause the permanent magnets within the BLDC to become demagnetized, an issue the other machines don't have. However, these disadvantages are typically outweighed by their advantages.

BLDCs are used in many different applications including but not limited to computer [[Hard Drive|hard disk drives]], servo drives, robotics, machine tools, [[Electric Vehicle|electric vehicles]], [[Windmill|electric windmills]], and more.