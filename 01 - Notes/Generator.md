---
tags:
  - physics
  - electromagnetism
  - electrical-engineering
  - electrical-machines
---
A **Generator** is a machine that converts [[Mechanical Energy|mechanical energy]] into [[Electrical Energy|electrical energy]]. It can be configured to produce both [[DC Electricity]] and [[AC Electricity]]. 

A generator works based off [[Faraday's Law]].
$$
\mathcal{E}=N\frac{d\Phi_{B}}{dt}
$$
It typically consists of two main parts: the *rotor* and the *stator*. 

# DC Generator

In a dc generator, a conductor is put in a magnetic field. Some external force rotates this conductor, such that it induces a [[voltage]] in the conductor. This voltage is given by,
$$
E=B\ell v
$$
where $B$ is the magnetic flux density in [[Tesla|teslas]] $[\text{T}]$, $\ell$ is the active length of the conductor (i.e. the length of conductor that crosses through the perpendicular [[magnetic field]]) in [[Metre|metres]] $[\text{m}]$, and $v$ is the relative speed of the conductor with respect to the magnetic field $[\text{m/s}]$. This specific relationship only holds if all three variables (the magnetic field, the conductor, and it's velocity) are perpendicular to one another.
![[simple-generator.png]]
The ends of the conductor winding are in constant contact with *slip rings*. This simple construction would output an ac signal, since, because each slip ring is always in contact with the same end of the winding, at times x will be more positive than y, and other times it will be more negative than y. This would produce an alternating signal.

To convert this signal to dc, we add a [[Commutator]] to the end. This way, one half of the commutator is always touching the part of the winding that is more positive and the other half is always touching the part that is more negative. This produces a pulsating dc output. If we add more contact points we can smooth this waveform out until it is almost a perfect dc signal. Modern dc generators produce voltages having a [[Voltage Ripple|ripple]] of $r\leq5\%$. 

The additional contacts are really just more conductors, additional windings in the generator. These windings, along with the laminated iron cylinder that houses them, are known as the [[Armature|armature]] of the machine.

The stator side of a dc generator consists of a magnetic field winding (basically large coils of wire that generate magnetic fields) and the brushes that make contact with the commutator. The rotor side is the armature and it's windings, and the commutator. Note that in a dc generator with a permanent magnet there are no field windings. 

## Induced Voltage

The voltage induced by a given generator is,
$$
E_0={cn\phi}
$$
where $E_0$ is the induced voltage $[\text{V}]$, $c$ is the number of conductors on the armature, $n$ is the speed of rotation in revolutions-per-minute $[\text{rpm}]$, and $\phi$ is the [[magnetic flux]] per pole $[\text{Wb}]$. 

This equation shows that for a given generator the voltage is directly proportional to the flux per pole and to the speed of rotation. The equation only holds if the brushes are on the neutral position. Shifting the brushes off neutral is equivalent to reducing the number of conductors.