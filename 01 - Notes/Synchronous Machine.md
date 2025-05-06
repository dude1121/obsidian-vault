---
tags:
  - physics
  - electromagnetism
  - electrical-machines
  - electrical-engineering
---
A **synchronous machine** is an [[Electrical Machine|electrical machine]] that can be operated as a [[Generator|generator]] or [[Motor|motor]]. Synchronous machines are ac machines and they are called as such because the speed of the rotating [[Magnetic Field|magnetic field]] is the same as the speed of rotation of the rotor. The speed at which they rotate is called the *synchronous speed* and it is determined by the frequency of the applied ac voltage $f$ and the number of poles in the motor $p$.
$$
n_{s}=\frac{120f}{p}
$$
In the above formulation, $n_{s}$ is measured in rotations-per-minute $[\mathrm{rpm}]$.
# Construction and saliency
As with most electrical machines, we can separate the parts of a synchronous machine into its stator and rotor.

The *stator* is composed of a three-phase distributed winding similar to in an [[Induction Machine|induction machine]]. Unlike the [[DC Machine|dc machine]], the stator winding is sometimes called the *armature winding*. It is designed for high voltage and high current, and typically has a very low resistance.

The *rotor* has a winding called the *field winding* which carries dc, not ac. The field winding is fed from an external dc source through slip rings and brushes, similar to how the dc machine powers its rotor winding.

Synchronous machines can be largely divided into two categories: high-speed machines with cylindrical (or non-salient pole) rotors and low-speed machines with salient pole rotors.

Non-salient pole rotors have one distributed winding and a practically uniform air gap. These motors are used in large generators with two or sometimes four poles and are usually driven by steam turbines (think [[Thermal Power Station|thermal]] or [[Nuclear Power Plant|nuclear]] power stations). These rotors are long with a small diameter.

Salient pole rotors have a lot more poles, sometimes as many as 50, and run at much lower speeds than non-salient motors. The generators used in [[Hydroelectric Power Station|hydroelectric power stations]] are typically salient pole generators and are rated for tens or hundred of megawatts. These rotors are shorter but have a larger diameter than non-salient pole machines. Salient pole machines are also used as back-up generators and pump motors.
# As a generator
Synchronous machines are most commonly used as generators where they are called synchronous generators or, more commonly, **alternators**. These are the generators found in most [[Power Systems#Generation|generation stations]]. 
![[sync-generator-1.png]]
Above is a diagram of a salient pole generator. When a field current is passed through the rotor $I_{\mathrm{f}}$ (or as I'll often denote it, $I_{\mathrm{x}}$), it establishes a sinusoidally distributed flux in the air gap. If the rotor is then rotated by some prime mover, a revolving field is produced in the air gap. This field is known as the *excitation field*. The rotating flux will change the flux linkage of each winding, $aa'$, $bb'$, and $cc'$, which will generate a voltage in each winding according to [[Faraday's Law|Faraday's law]].
$$
\mathcal{E}=N\ \frac{d\Phi}{dt}
$$
The induced voltages in each winding will have the same magnitudes but will be phase shifted $120\degree$ from one another due to the physical positioning of the windings. The rms value of this voltage is,
$$
E=\frac{2\pi}{\sqrt{ 2 }}f\Phi NK_{w}
$$
where $f$ is the frequency of the rotor, given by $f=\frac{np}{120}$, $\Phi$ is the [[Magnetic Flux|flux]] per pole, $N$ is the number of turns in each phase's winding, and $K_{w}$ is the 'winding factor', a factor derived [[Synchronous Machine#Winding Factor|below]]. From this above relationship though we can see that,
$$
E\propto n\Phi
$$
This variation is not entirely linear, however. Initially, the output voltage will rise linearly with the field excitation current, but as the field current is further increased, the flux $\Phi$ does not increase linearly with $I_{\mathrm{x}}$ due to the saturation of the [[Magnetic Circuit|magnetic circuit]] and therefore the terminal voltage will begin to level off. 
# As a motor
Synchronous machines when used as motors have various uses. Large synchronous motors are used for pumps in some generation stations, and small fractional [[Horsepower|horsepower]] motors are used in things like clocks, timers, record turntables, and other applications where a constant speed is desired or required. This is also where they are commonly used in industry, as unlike their more common [[Induction Machine#Three phase induction motors|induction motor]] counterparts, synchronous motors operate at a constant speed.

Sync motors also find industrial application as a way to correct [[Power Factor|power factor]]. Synchronous machines can be operated with an adjustable power factor, allowing a motor to run with a leading power factor to counteract the lagging power factor of induction motors. 
### Starting the motor
There are two primary ways to start a synchronous motor: as an [[Induction Machine|induction motor]] or with a [[Variable Frequency Drive|VFD]].
#### Starting as an induction motor
If a VFD is not available or the motor does not have to run at various speeds, it can be started as an induction motor. For this purpose there is an additional winding which resembles the 'squirrel cage' of an induction motor is added. This winding is sometimes called a *damper* or *amortisseur* winding. To start the motor, the field is de-energized and the motor terminals are connected to ac supply. This causes the motor to rotate in the same way that a squirrel cage in an induction motor causes it to rotate. When the motor has been brought up to near synchronous speed, the field winding is excited, and the motor is pulled to synchronous speed.

While the motor is running, the damper winding also serves to bring the motor back to synchronous speed when it becomes loaded. This is because the increase in torque causes a current to flow in the winding, therefore increasing the flux density in the motor and accelerating it back to synchronous speed.
#### Starting with a VFD
Starting a synchronous motor with a controller is much simpler as the controller can slowly increase the frequency until the motor reaches the desired speed. This is important because if the frequency is not slowly increased the motor could be damaged due to the sudden inrush current and resultant torque.
## Variable power factor
As mentioned above, a synchronous motor can be run at a variable power factor. This is because a synchronous motor is doubly fed: ac in the stator windings and dc in the rotor poles. If the rotor field winding is excited to a certain level, the stator will draw no reactive current; that is, the motor will operate at a unity power factor. Decreasing the field current will cause the motor to draw *lagging* reactive current and increasing the field current will cause the motor to draw *leading* reactive current. This means that the value of $I_{\mathrm{x}}$ determines the power factor of the machine.

If we were to operate a sync machine with no load and simply use this quality of sync machines to correct power factor, this is called a *synchronous condenser*. 
# Characteristics
## Winding factor
The winding factor $K_{w}$ is a factor that depends on the construction of the synchronous machine. It is defined as the product of the distribution factor $K_{d}$ and the pitch factor $K_{p}$.
$$
K_{w}=K_{d}\cdot K_{p}
$$
The distribution factor arises because the windings are spread across multiple slots within the machine. It can be found by,
$$
K_{d}=\frac{\sin \left( \frac{n\delta}{2} \right)}{n\sin\left( \frac{\delta}{2} \right)}
$$
where $n$ is the slots per pole per phase and $\delta$ is the electrical angle between adjacent slots given by
$$
\delta=\frac{p\alpha}{2}
$$
where $p$ is the number of poles and $\alpha$ is the mechanical angle between the rotor and stator poles.
# Equivalent circuit
