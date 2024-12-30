---
tags:
  - physics
  - kinematics
---
**Acceleration** is a change in an object's [[Velocity|velocity]] with respect to [[Time|time]]. Average acceleration is found by
$$
a_{av}=\frac{v_{f}-v_{i}}{t_{f}-t_{i}}=\frac{\Delta v}{\Delta t}
$$
As $\Delta t$ approaches $0$, we get closer to the instantaneous acceleration. This can be defined as the time [[Derivative|derivative]] of velocity, or the second derivative of [[Position|position]].
$$
\mathbf{\vec{a}}=\frac{d}{dt}\mathbf{\vec{v}}=\frac{d^2}{dt^2}\mathbf{\vec{r}}
$$
Acceleration is a [[Vector|vector]] quantity and does not have a scalar counterpart. As given by [[Newton's Laws|Newton's second law]], acceleration is proportional to [[Force|force]].
$$
\mathbf{\vec{F}}\propto \mathbf{\vec{a}}
$$
# Tangential and centripetal acceleration

If an object is rotating about some point $O$, its acceleration is split into two components: the *tangential* acceleration, and the *centripetal* acceleration. Tangential acceleration is directed [[Tangent Line|tangent]] to the point being examined, whereas centripetal acceleration is directed toward the centre point, $O$.  The following relationships allow us to calculate both forms of acceleration:
$$
a_{t}=r\alpha
$$
$$
a_{c}=\frac{v^2}{r}=r\omega^2
$$
For the first relationship, $a_{t}$ is the tangential acceleration's magnitude, $r$ is the distance (or, radius) from the centre $O$, and $\alpha$ is the body's [[Angular Acceleration|angular acceleration]].  For the second relationship, $a_{c}$ is the centripetal acceleration's magnitude, $r$ is once again the distance from $O$, and $\omega$ is the body's [[Angular Velocity|angular velocity]].  The magnitude of the total acceleration is therefore,
$$
a=\sqrt{ a_{t}^2+a_{c}^2 }=\sqrt{ r^2(\alpha^2+\omega^4) }=r\sqrt{ \alpha^2+\omega^4 }
$$
![[rotational-acceleration.png]]
