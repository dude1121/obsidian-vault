---
tags:
  - electromagnetism
  - electrical-engineering
---
A **dc machine** is an [[Electrical Machine|electrical machine]] that runs on [[DC Electricity|dc electricity]]. It can be operated as either a [[Generator|generator]] or a [[Motor|motor]].
# As a Generator

In a dc generator, a conductor is put in a magnetic field. Some external force rotates this conductor, such that it induces a [[voltage]] in the conductor. This voltage is given by,
$$
\mathcal{E}=B\ell v
$$
where $B$ is the magnetic flux density in [[Tesla|teslas]] $[\text{T}]$, $\ell$ is the active length of the conductor (i.e. the length of conductor that crosses through the perpendicular [[magnetic field]]) in [[Metre|metres]] $[\text{m}]$, and $v$ is the relative speed of the conductor with respect to the magnetic field $[\text{m/s}]$. This specific relationship only holds if all three variables (the magnetic field, the conductor, and it's velocity) are perpendicular to one another.[^1]

![[simple-generator.png]]

The ends of the conductor winding are in constant contact with *slip rings*. This simple construction would output an ac signal, since, because each slip ring is always in contact with the same end of the winding, at times x will be more positive than y, and other times it will be more negative than y. This would produce an alternating signal.

To convert this signal to dc, we add a [[Commutator|commutator]] to the end. This way, one half of the commutator is always touching the part of the winding that is more positive and the other half is always touching the part that is more negative. This produces a pulsating dc output. If we add more contact points we can smooth this waveform out until it is almost a perfect dc signal. Modern dc generators produce voltages having a [[Voltage Ripple|ripple]] of $r\leq5\%$. 

The additional contacts are really just more conductors, additional windings in the generator. These windings, along with the laminated iron cylinder that houses them, are known as the [[Armature|armature]] of the machine.

The stator side of a dc generator consists of a magnetic field winding (basically large coils of wire that generate magnetic fields) and the brushes that make contact with the commutator. The rotor side is the armature and it's windings, and the commutator. Note that in a dc generator with a permanent magnet there are no field windings. 

## Induced Voltage

The voltage induced by a given generator is,
$$
E_0=\frac{zn\phi}{60}
$$
where $E_0$ is the induced voltage $[\text{V}]$, $z$ is the number of conductors on the armature, $n$ is the speed of rotation in revolutions-per-minute $[\text{rpm}]$, and $\phi$ is the [[magnetic flux]] per pole $[\text{Wb}]$. Dividing the expression by $60$ serves to convert rotations per minute into rotations per second.

This equation shows that for a given generator the voltage is directly proportional to the flux per pole and to the speed of rotation. The equation only holds if the brushes are on the neutral position. Shifting the brushes off neutral is equivalent to reducing the number of conductors. 

This shift may occur due to an increased load on the generator (see the commutator page). To correct the neutral zone shift, *commutating poles* (or sometimes, *compensation windings*) are added perpendicular to the stator field. These compensation windings serve to counteract the armature reaction and shift the neutral zone back to its no-load position.  

## Wiring Configurations

A DC generator can be wired in three primary configurations: *separately excited*, *self-excited*, and *compound*. 

### Separately Excited

In a separately excited dc generator, the field windings are powered from an external dc source. When the generator is wired in this fashion, the exciting current $I_{\mathrm{x}}$ is directly proportional to the induced voltage. This relationship is nearly linear until it reaches a "knee", wherein the iron core is saturated with magnetic flux, and the induced voltage begins to have diminishing returns with added excitation current.
![[no-load-sep-excited-v-vs-ix.png]]

This increase in induced voltage arises because an increase in the excitation current increases the strength of the generated magnetic flux. This increase in flux increases the induced voltage according to the relationship $E=\frac{cn\Phi}{60}$. 

Under load, the separately excited generator's terminal voltage decreases slightly with increased load, to the point that the full load voltage is about 10% less than the no-load voltage. 

### Self-Excited

A self-excited dc generator (also called a *shunt* excited generator, since shunt means "parallel") is a generator whose field winding is energized from the armature itself. This has the advantage of not requiring an external dc source to energize the field winding.

This process works because of *residual magnetism*. When a generator is operated, the iron core becomes magnetized. But when the power is shut off, the iron is not fully demagnetized (see [[Hysteresis|hysteresis]]). This residual magnetism allows there to be a weaker magnetic field through the poles, allowing the generator to generate some voltage. This voltage in turn is fed into the field windings which strengthen the magnetic field at the poles, generating an even larger voltage, until the core is saturated.

The trade off with this configuration is that a self-excited generator's output voltage will tend to drop as load is increased. This is because as the terminal voltage drops, the field current drops as well, reduced the generated $\Phi$. The voltage regulation of a self-excited generator is around 15%.

### Compound

A compound dc generator makes use of an additional *series winding* to prevent the terminal voltage from dropping with additional load. The series winding is, as the name implies, in series with the armature winding. As the armature current increases, it also flows through the series winding which generates an additional mmf that aids the shunt field mmf. This causes the induced voltage to increase since the magnetic flux density is increasing. When well designed, the series coil can make the voltage nearly constant from no-load to full-load. 

A generator may be over-compounded if there are additional turns added to the series winding which actually causes the terminal voltage $E_{o}$ to *increase* as load increases.

#### Differential Compound

A special case of the compound generator is the differential compound generator, where the series winding is wired in such a way that its mmf actually opposes the field winding's mmf. This has the effect of drastically lowering $E_{o}$ as the load increases. 

# As a Motor

As a motor the dc machine operates very similarly to the dc generator. Instead of an external force providing the relative motion in the armature, a voltage is applied to the armature and the field windings to generate this motion.

## Starting the Motor

If a voltage is applied to the field winding, the winding generates a magnetic field within the machine. When a voltage is then applied to the armature, a very high current passes through the armature (since the armature's [[Resistance|resistance]] is relatively small). Since there are now many current carrying conductors in a magnetic field, they being to experience a force due to Lorenz's Law that causes the machine to rotate. 

However, applying the entire source voltage across the armature at once would cause a large in-rush current that could damage the armature windings. To solve this problem, a large resistance is added via a motor starter like the one shown below.
![[dc-motor-starter.png]]
As the arm moves along the contacts, the effective resistance in the armature circuit decreases until there is only the base winding resistance. This ensures that the starting current is not too high for the machine. The [[Solenoid|solenoid]] at position 4 holds the contact arm in place as long as there is a field in place. If, for whatever reason, the field circuit opens or loses power, the arm is let go by the magnet and the motor is de-energized.

Another solution to the starting problem is electronic methods like [[Variable Frequency Drive|VFDs]] or solid-state solutions.

## Counter-emf

The rotation of the armature in the presence of a magnetic field is a similar situation to the generator. The physics does not change just because we want it to operate as a motor. Due to this motion, the armature generates an induced voltage $E_{o}$ proportional to the speed of rotation and flux per pole in the same way for a generator.
$$
E_{o}=\frac{Zn\phi}{60}
$$
In the case of a motor, however, we call this voltage the *counter-emf* or *back-emf* because its polarity is always against the applied voltage. That means that the net voltage across the armature is 
$$
E_{A}=E_{s}-E_{o}
$$
This has the effect that the armature current,
$$
I_{A}=\frac{E_{s}-E_{o}}{R_{A}}
$$
will decrease as the speed of the motor increases. However, the motor can not accelerate infinitely. It will settle around a no-load maximum speed such that $E_{o}$ is slightly less than $E_{s}$ (if $E_{o}=E_{s}$, then the armature net voltage would be $0\pu{ V}$, meaning no current would be present and therefore no force would act on the conductors, causing the motor to slow down). When under load, the motor will run at a speed that allows $I_{A}$ to generate the correct amount of [[Torque|torque]] to match the load torque.

---
[^1]: Technically to find the induced [[emf]] you would need to rearrange [[Lorentz Force Law|Lorenz's law]] but for practical cases only the maximum induced emf is important, which occurs when the three position vectors are perpendicular to one another. 