---
tags:
  - physics
  - electromagnetism
  - electrical-machines
  - electrical-engineering
---
An **induction machine** is an [[Electrical Machine|electrical machine]] that can be run as either a [[Generator|generator]] or a [[Motor|motor]], but is more frequently encountered as a motor. An induction machine can be either single phase or three phase, but always runs off of [[AC Electricity|ac electricity]]. Speed in induction machines is frequency-dependent which means that speed control is only possible through [[Variable Frequency Drive|VFDs]] and other solid state solutions. The two most common forms of induction machines, whether single or three phase, is the *squirrel cage* machine or the *wound-rotor* machine.
# Single phase induction motors
Single phase ($1-\Phi$) induction machines are among the most common of all electric motors and are found in many appliances and power tools. They are typically employed when $3-\Phi$ power is not available or practical.
## Construction
$1-\Phi$ induction motors are constructed very similarly to $3-\Phi$ motors. They are composed of a squirrel-cage rotor and a stator. The stator has a *main winding* which generates a set of north and south [[Magnetic Pole|magnetic poles]], as well as an *auxiliary winding* that operates only during start-up. The auxiliary winding has the same number of poles as the main winding. These windings are lodged straddling the main windings.
## Speed
$1-\Phi$ motors have their synchronous speed defined the same as $3-\Phi$ motors. That is,
$$
n_{s}=\frac{120f}{p}
$$
Just like $3-\Phi$ motors, $1-\Phi$ motors will operate at just below synchronous speed, typically with a [[Slip|slip]] anywhere between 3 - 5%. 
## Operation
A $1-\Phi$ motor will not spin if a $1-\Phi$ ac [[Voltage|voltage]] is applied across its terminals. Instead, if the motor is stationary and a voltage is applied across it, the rotor will oscillate at the frequency of the applied voltage, and essentially behave like the secondary winding of a [[Transformer|transformer]] that has been short-circuited. If, however, the rotor is spun either clockwise or counterclockwise, the $1-\Phi$ ac voltage is sufficient to keep it in motion, in fact it will accelerate until it reaches its nominal speed, just below synchronous speed. This [[Angular Acceleration|acceleration]] indicates that there is an increase in [[Torque|torque]] as the motor approaches sync speed.

The operation of the motor can be explained by the *double revolving field theory*.
### Double Revolving Field Theory
#### Rotor at Standstill
Before the motor is turned on, the rotor is stationary and the stator winding is connected to a $1-\Phi$ supply. A pulsating [[Magnetomotive Force|mmf]], and therefore a pulsating [[Magnetic Flux|flux]] $\Phi_{s}$ is established in the machine along the axis of the stator winding. This flux induces a [[Current|current]] in the rotor bars, which in turn produces a pulsating flux $\Phi_{r}$ acting along the same axis as the stator flux $\Phi_{s}$. By [[Lenz's Law|Lenz's law]], these two fluxes will oppose one another. However, the angle between them is $0\degree$, so there is not starting torque developed.
#### Rotor while Running
Assume the rotor has begun moving either by manually spinning the rotor or by using circuitry to move the rotor. In this condition, the motor is able to develop a torque. We can represent the pulsating mmfs as sinusoidal functions. Specifically, for a sinusoidally distributed stator winding, the mmf along a position $\theta$ is given by,
$$
\mathcal{F}(\theta)=Ni\cos \theta
$$
where $N$ is the effective number of turns of the stator winding. We can represent the current sinusoidally as well, namely, $i=I_{\mathrm{max}}\cos \omega t$,
$$
\begin{aligned}
\mathcal{F}(\theta)&=NI_{\mathrm{max}}\cos \theta \cos \omega t\\
&=\frac{NI_{\mathrm{max}}}{2}\cos(\omega t-\theta)+\frac{NI_{\mathrm{max}}}{2}\cos(\omega t+\theta)\\
&=\mathcal{F}_{f}+\mathcal{F}_{b}\\
\end{aligned}
$$
where $\mathcal{F}_{f}$ is a rotating mmf in the direction of $\theta$ and $\mathcal{F}_{b}$ is a rotating mmf in the opposite direction of $\theta$. Both of these mmfs produce a torque, but in opposite directions. At standstill, these two torques are equal in magnitude, so the rotor does not move. At any other speed, the torques are unequal, and therefore the motor continues to rotate.
![[torque-vs-speed-revolving-field.png]]
The speed of these rotating mmfs can be found by finding their slips. For the forward mmf,
$$
s_{f}=\frac{n_{s}-n}{n_{s}}=s
$$
that is to say that the forward mmf slip is the same as the slip of the motor itself. For the backwards mmf,
$$
\begin{aligned}
s_{b}&=\frac{n_{s}-(-n)}{n_{s}}\\
&=\frac{n_{s}+n}{n_{s}}\\
&=\frac{2n_{s}-n_{s}+n}{n_{s}}\\
&=\frac{2n_{s}}{n_{s}}-\frac{n_{s}-n}{n_{s}}\\
\Aboxed{&=2-s}
\end{aligned}
$$
## Starting the Motor
To produce a starting torque a revolving field must be created somehow. This is done in many different ways but they all include an auxiliary winding of some sort. 
### Locked-Rotor Torque
The torque of the locked rotor is given by,
$$
\tau_{LR}=kI_{m}I_{a}\sin \alpha
$$
where $k$ is a constant dependant on the motor equivalent to,
$$
k=\frac{2a(R_{f}+R_{b})}{\omega_{\mathrm{sync}}}
$$
where $a$ is the turns ratio between the main and auxiliary windings, $R_{f}$ and $R_{b}$ are the [[Complex Numbers|real components]] of the forward and backward [[Impedance|impedances]], respectively, and $\omega_{\mathrm{sync}}$ is the synchronous [[Angular Velocity|angular velocity]].

Going back to the locked-rotor torque, $I_{m}$ and $I_{a}$ are the currents through the main and auxiliary windings, and $\alpha$ is the phase angle between the two currents.
## Types of Single Phase Induction Motors
As mentioned above, the methods of creating a phase shift varies from motor to motor. Below are some commonly found methods of doing so.
### Resistance Split-Phase Motor

In this type of motor, the auxiliary winding is made of a relatively small number of turns of fine wire. Makes the winding more [[Resistance|resistive]] and less [[Reactance|reactive]] than the main winding, making the auxiliary current more in phase with the source voltage than the main current. This produces a slight phase shift between the auxiliary mmf and the main mmf, which in turn produces a starting torque.

This is a cheaper alternative to the other methods, however during start-up the auxiliary winding heats up very quickly, so this motor is not well-suited for high-[[Moment of Inertia|inertia]] loads nor for situations that require frequent starting. Typical power ratings for split-phase motors are $60\pu{ W}-250\pu{ W}\ (\frac{1}{12}\pu{ hp}-\frac{1}{3}\pu{ hp})$. 
### Capacitor Start Motor
This motor is similar to the split-phase motor except that the auxiliary winding has about the same number of turns as the main winding. An electrolytic [[Capacitor|capacitor]] and centrifugal switch are connected in series with the auxiliary winding. The capacitor is chosen such that it introduces a phase shift of about $80\degree$. This gives it a much higher starting torque than a split-phase motor. The locked-rotor line current is also lower than the split-phase motor.

Cap-start motors are better suited for loads that require a high starting torque or frequent starting periods. Typical power ratings for cap-start motors are $120\pu{ W}-7.5\pu{ kW}\ (\frac{1}{6}\pu{ hp}-10\pu{ hp})$. 
### Capacitor Run Motor
This motor is essentially a $2-\Phi$ motor that receives power from a $1-\Phi$ source. Its auxiliary winding is connected in series with a paper capacitor and has a large number of turns of relatively fine wire compared to the main winding. This gives it a high [[Power Factor|power factor]] and makes it run particularly quiet in comparison to the other motors, however it has a rather low starting torque. 
### Cap-Start, Cap-Run Motor
The properties of capacitor-start and capacitor-run motors can be combined into one motor that has the benefits of the high power factor of the cap-run motor but also the high starting torque of the cap-start motor. This motor is more expensive than the other motors, so it is only used when absolutely necessary.
### Shaded Pole Motor
A shaded pole motor has a very simple construction. It essentially is a squirrel cage motor where the auxiliary winding is composed of a copper ring surrounding a portion of each pole.
![[shaded-pole.png]]
The copper rings produce a slight delay in the magnetic flux, which induces motion in the rotor. Shaded pole motors have very low torque and power (about $40\pu{ W}$ or $0.05\pu{ hp}$) and can not have their  direction changed. However, for applications where this does not matter, shaded pole motors are a good choice for their simplicity and low cost.
### Universal Motor
Universal motors are very similar to [[DC Machine|dc series motors]] and can operate on either ac or [[DC Electricity|dc]] with no change to its torque-speed curve (hence the name *universal*). The field and the armature are connected in series, which means that when connected to an ac source the field and armature flip polarity at the same time, meaning the direction of rotation never changes. This machine does not produce a revolving field, instead operating on the same principle as a dc machine.
![[universal-motor.png]]
These motors have high speeds and high starting torque which lends them well to uses in vacuum cleaners or portable tools like saws and drills. No load speeds ranging from $5000\pu{ rpm}-15000\pu{ rpm}$ are possible with these motors, but as with any series motor, the speed decreases with an increase in load torque. Universal motors are however very noisy and require more maintenance than other types of motors. 

### Hysteresis Motor

The hysteresis motor 
# Three phase induction motors
TODO!