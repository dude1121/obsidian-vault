---
tags:
  - physics
  - kinematics
---
The **moment of inertia** of an object is a measure of the rotational [[Inertia|inertia]] of that object. That is, it is the opposition that the body exhibits to having its speed of rotation altered by the application of [[Torque|torque]]. The axis of rotation for a given moment of inertia is always fixed. It is the rotational analogue to [[Mass|mass]].

Moments of inertia are calculated by the general formula,
$$
I\equiv\displaystyle \sum_{i}m_{i}{r_{i}}^2
$$
where $I$ is the symbol for moment of inertia in [[Kilogram|kilogram]]-[[Metre|metres]] squared $[\text{kg}\cdot \text{m}^2]$, $m_{i}$ is the mass of the $i$th particle in kilograms $[\text{kg}]$, and $r_{i}$ is the distance of the $i$th particle from the centre of rotation in metres $[\text{m}]$.

Moments of inertia are used in calculating the applied torque on a body,
$$
\tau=I\alpha
$$
where $\tau$ is the torque in [[Newton]]-metres $[\text{N}\cdot \text{m}]$, and $\alpha$ is the [[Angular Acceleration|angular acceleration]] in [[Radian|rads]] per [[Second|second]] squared $[\text{rads/s}^2]$. It can also be used to calculate [[Angular Momentum|angular momentum]],
$$
L=I\omega
$$
where $L$ is the angular momentum and $\omega$ is the [[Angular Velocity|angular velocity]] in rads per second $[\text{rads/s}]$. 

The moment of inertia of a simple [[Pendulum|pendulum]] can be found simply by,
$$
I=mr^2
$$

# Calculating moments of inertia
To find the moment of inertia of a rigid object, we imagine the object to be divided into many small elements each of which having a mass of $\Delta m_{i}$. We then take the limit of our general expression above as $\Delta m_{i}$ approaches $0$.
$$
I=\lim_{ \Delta m_{i} \to 0 } \displaystyle \sum_{i}\Delta m_{i}{r_{i}}^2 
$$
Evaluating the limit,
$$
I=\int r^2dm
$$
It is however usually easier to calculate moments of inertia with respect to the object's [[Volume|volume]], not its mass. We can change mass into volume by way of using the [[Volumetric mass density|volumetric mass density]] formula,
$$
\rho \equiv \frac{m}{V}
$$
This means that our [[Differential|differential]] element $dm$ becomes,
$$
I=\int \rho r^2dV
$$
If $\rho$ is constant, the integration can be performed and the moment of inertia calculated. If it is not constant, its variation with position must be known.

The formulas for various homogeneous shapes are detailed in the table below.
![[moments-of-inertia.png]]

By use of the [[Parallel Axis Theorem|parallel axis theorem]], we can also find moments of inertia for shapes whose rotation is not perfectly symmetrical and does not fall on the [[Centre of Mass|centre of mass]] of the object.
$$
I=I_{\text{CM}}+MD^2
$$
where $I_{\text{CM}}$ is the moment of inertia at the centre of mass of the object, $M$ is the total mass of the object, and $D$ is the distance from the origin $O$ to the centre of mass.