---
tags:
  - physics
  - electromagnetism
  - electrical-engineering
  - electrical-machines
---
A **motor** is an [[Electrical Machine|electrical machine]] that converts [[Electrical Energy|electrical energy]] into [[Mechanical Energy|mechanical energy]]. Motors can be powered by either [[DC Electricity|dc]] or [[AC Electricity|ac electricity]]. 

Similar to a [[Generator|generator]], a motor operates based off the interaction of two [[Magnetic Field|magnetic fields]] that produce rotation in the motor. Common machines that are run as motors include [[DC Machine|dc machines]], [[Synchronous Machine|synchronous machines]], and [[Induction Machine|induction machines]]. In addition, there are some specialty motors including the [[Stepper Motor|stepper motor]], [[Servomotor|servomotor]], and [[Brushless DC Motor|brushless dc motors]].

# Power Flow
Motors require some sort of electrical input power. This input power can consist of both an armature / rotor power source as well as a dc field power source, or just the former. Motors are not 100% efficient, so some of this input power is lost in the form of [[Friction|frictional]] losses, [[Hysteresis|hysteresis]] losses, or other losses. The output power of a motor is given by,
$$
P_{o}=\omega \tau
$$
where $\omega$ is the [[Angular Velocity|angular velocity]] of the rotor in [[Radian|radians]] per [[Second|second]] $[\pu{ rads/s}]$, and $\tau$ is the [[Torque|torque]] of the motor in [[Newton]]-[[Metre|metres]] $[\pu{ Nm}]$. Alternatively, this relationship is sometimes given by,
$$
P_{o}=\frac{n\tau \pi}{30}\approx \frac{n\tau}{9.55}
$$
where $n$ is the rotational speed in revolutions-per-minute $[\pu{ rpm}]$. The $\pi$ and $30$ (reduced from $\frac{2\pi}{60}$) are there to convert $\pu{ rpm}$s into $\pu{ rads/s}$. 