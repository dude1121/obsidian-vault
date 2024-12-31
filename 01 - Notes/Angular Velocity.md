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
Recall that the particles  of an object in rotational motion travels along some arc path $s$. The linear tangential velocity of those particles can therefore be given by,
$$
v_{\perp}=\frac{ds}{dt}
$$
Since $s=r\theta$,
$$
v_{\perp}=r\frac{d\theta}{dt}
$$
And because angular velocity is $\frac{d\theta}{dt}$,
$$
\boxed{v_{\perp}=r\omega}
$$
where $v_{\perp}$ is the tangential velocity of the point, which could be expressed as $v_{\perp}=v\sin \theta$ where $\theta$ is the angle of the velocity vector with respect to the position vector. Due to this, we could also express this relationship in terms of the velocity magnitude.
$$
v=\frac{r\omega}{\sin \theta}
$$
That is that the tangential velocity of a point on a rotating body is the perpendicular distance of that point from the centre of rotation multiplied by the angular velocity of the body. **Although all points on a rotating body have the same angular speed, their tangential speed varies according to how far from the centre of rotation they are.** 

Angular velocity is, however, a [[Vector|vector]] quantity and requires a direction. To factor in this direction, angular velocity is related to tangential velocity and position by means of the [[Cross Product|cross product]]. Rearranging the above relationship,
$$
\omega =\frac{v\sin \theta}{r}
$$
In terms of the cross product, this is represented as,
$$
\pmb{\vec{\omega}}=\frac{\mathbf{\vec{r}}\times \mathbf{\vec{v}}}{r^2}
$$
We can also therefore express the tangential velocity in terms of the cross product,
$$
\mathbf{\vec{v}}_{\perp}=\mathbf{\vec{r}}\times \pmb{\vec{\omega}}
$$
The tangential acceleration can therefore be found by taking the derivative of the tangential speed.
$$
a_{t}=r\frac{d\omega}{dt}=r\alpha
$$

# Relation to angular momentum

The magnitude of the total [[Angular Momentum|angular momentum]] of a rotating body can be expressed as the product of the body's angular velocity and its [[Moment of Inertia|moment of inertia]].
$$
\mathbf{\vec{L}}=I\pmb{\vec{\omega}}
$$
