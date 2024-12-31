---
tags:
  - physics
  - kinematics
---
**Angular velocity** is the angular counterpart to [[Velocity|velocity]]. It is denoted with $\omega$ or $\mathbf{\vec{\omega}}$. Angular speed is the magnitude of angular velocity, and it is given by,
$$
\omega=\frac{d\theta}{dt}
$$
It has units of [[Radian|radians]] per [[Second|second]] $[\text{rad/s}]$.  Angular speed $\omega$ and angular velocity $\mathbf{\vec{\omega}}$ differ in that angular velocity's direction is the direction along the axis of rotation.  If an object rotates in the $xy$ plane, the direction of $\mathbf{\vec{\omega}}$ is out of the plane when the rotation is counterclockwise and into the plane when it is clockwise. This convention can be remembered using the *right hand rule*. Wrap the four fingers in the direction of rotation and the thumb points in the direction of $\mathbf{\vec{\omega}}$.

Much like how the derivative of velocity yield [[Acceleration|acceleration]], the derivative of angular velocity yields [[Angular Acceleration|angular acceleration]].
$$
\mathbf{\vec{\alpha}}=\frac{d\mathbf{\vec{\omega}}}{dt}
$$
# Relation to linear velocity and acceleration
Recall that the particles  of an object in rotational motion travels along some arc path $s$. The linear velocity of those particles can therefore be given by,
$$
v=\frac{ds}{dt}
$$
Since $s=r\theta$,
$$
v=r\frac{d\theta}{dt}
$$
And because angular velocity is $\frac{d\theta}{dt}$,
$$
\boxed{v=r\omega}
$$
That is that the tangential velocity of a point on a rotating body is the perpendicular distance of that point from the centre of rotation multiplied by the angular velocity of the body. **Although all points on a rotating body have the same angular speed, their tangential speed varies according to how far from the centre of rotation they are.** 

The tangential acceleration can therefore be found by taking the derivative of the tangential speed.
$$
a_{t}=r\frac{d\omega}{dt}=r\alpha
$$

# Relation to angular momentum

The magnitude of the total [[Angular Momentum|angular momentum]] of a rotating body can be expressed as the product of the body's angular velocity and its [[Moment of Inertia|moment of inertia]].
$$
L=I\omega
$$