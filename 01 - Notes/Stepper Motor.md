---
tags:
  - physics
  - electromagnetism
  - electrical-machines
  - electrical-engineering
---
A **stepper motor** is a specialty [[Motor|motor]] used when the motion and position of a motor needs to be precisely controlled. Stepper motors rotate in discrete *steps* that can vary anywhere from $90\degree$, $45\degree$, or smaller steps up to a fraction of a degree per pulse. By varying the pulse rate, the speed of the motor can be controlled. The sequence of pulses can also control the direction of rotation.

Typically a stepper motor is controlled by a [[Microcontroller|microcontroller]] or [[Microprocessor|microprocessor]] which keeps track of the pulses sent to the motor, meaning its position is known at all times. This makes stepper motors very useful in precise positioning applications like 3d printers or CNC machines. 

# Elementary Stepper Motor
![[elementary-stepper.png]]
In a simple stepper motor as shown above, there are three [[Salient Pole|salient poles]] with a 2-pole rotor. The switches A, B, and C control which pole behaves as the North, attracting the south side of the rotor. The sequence $A,B,C,A,B,C, \dots$ would cause the motor to rotate counter clockwise (ccw) in steps of $60\degree$/pulse. Changing the sequence to $A,C,B,A,C,B, \dots$ would make the motor rotate clockwise (cw). 

When power is removed from the motor, the *residual magnetism* of the stator and rotor holds the motor in place. The amount of [[Torque|torque]] required to move the rotor from this state is called the *holding torque*. In contrast, the amount of torque the motor exerts as it moves from one position to the next is called the *pull-over torque*. 

# Effects of Inertia

Consider the motor above. Initially at pole A, we send a pulse to move it to pole B. The motor accelerates and moves towards pole B, but due to its [[Angular Momentum|angular momentum]] and [[Moment of Inertia|inertia]], the rotor overshoots the pole instead of coming to rest at pole B. When it does this, the pole will pull on the rotor in the opposite direction, which will again induce a torque and acceleration in the opposite direction as before. It will once again overshoot pole B, and the same thing will occur until the rotor finally settles.
![[stepper-oscillation.png]]
This oscillation (see above) will eventually die out, but these oscillations pose a problem if precision is needed for the stepper motor's application. As the motor gets larger, or if the moment of inertia is somehow increased, this oscillation will get worse. 
![[stepper-oscillation-higher-inertia.png]]
To fix this, two methods can be used. 

## Viscous Damping
![[stepper-oscillation-viscous.png]]
If we increase the friction inside the motor by filling it with a fluid like oil, we can reduce the effect of the oscillations. This has the drawback of increasing the pull-over torque of the motor.

## Increasing the Load
![[stepper-oscillation-load.png]]
When compared to the first diagram, increasing the load makes the motor take a little longer to reach its final position, however the oscillations are dampened more quickly. This shows, however, that increasing either the load or the motor's moment of inertia has the effect of prolonging the time the motor takes to reach the next step.

# Slewing

Slewing in terms of a stepper motor refers to sending a new pulse to the motor before it reaches the previous location. For example, in the diagram above, imagine that the switch B is closed and switch A is opened, causing the motor to rotate ccw. However, before the bottom part of the rotor moves to pole B, we open switch B and close switch C, causing the rotor to continue its motion in the ccw direction and move towards pole C. Because the motor is moving at essentially constant speed, the inertial effects can be ignored. 

While slewing, a stepper motor can carry a greater load torque, so long as the motor does not fall out of step.