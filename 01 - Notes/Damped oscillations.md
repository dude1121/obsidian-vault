---
tags:
  - physics
  - oscillatory-motion
---
**Damped oscillations** are [[Simple harmonic motion|oscillations]] that occur in the presence of some [[Retarding Force|retarding force]] $\mathbf{\vec{R}}$, typically friction of some sort. This damping reduces the total [[Mechanical Energy|mechanical energy]] in the system and therefore leads to the oscillations dying out if no additional energy is added to the system.

When the retarding force is small compared with the maximum restoring force, that is, when the [[Damping Coefficient|damping coefficient]] $b$ is small, the position of the oscillator is given by
$$
x(t)=Ae^{-(b/2m)t}\cos(\omega t+\varphi)
$$
The [[Angular Frequency|angular frequency]] of the oscillations is
$$
\omega=\sqrt{ \frac{k}{m} -\left(\frac{b}{2m}\right)^2}
$$
It is, however, more often written as
$$
\omega=\sqrt{ \omega_{0}^2-\left(\frac{b}{2m}\right)^2 }
$$
where $\omega_{0}=\sqrt{ \frac{k}{m} }$ represents the angular frequency absence in the retarding force. The quantity $\omega_{0}$ is known as the *natural frequency* of the system. When the retarding force is small, the oscillatory character of the motion is preserved by the amplitude decreases in time with the result that the motion ultimately ceases. This is the definition of a damped oscillator.
![[damped-oscillator-underdamped.png]]
The plot of a damped oscillator can be seen above. The dashed blue lines represent the *envelope* of the oscillatory curve. In this state, where $\frac{b}{2m}<\omega_{0}$, we say the system is *underdamped*.

If we increase the value of $b$, the system begins to behave differently. If $\frac{b}{2m}=\omega_{0}$, the system is *critically damped*. In this state, the oscillator simply moves back to its equilibrium point and remains there.
![[damped-oscillator-critically-damped.png]]
If we keep increasing $b$ such that $\frac{b}{2m}>\omega_{0}$, the system is now *overdamped*. As the system becomes more damped past the critical point, the only change is the time it takes for the oscillator to return to its equilibrium. In these last two cases, the solution to the differential equation shown above is no longer valid.