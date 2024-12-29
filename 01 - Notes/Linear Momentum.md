---
tags:
  - physics
  - kinematics
---
**Linear Momentum** is a [[Law of Conservation of Linear Momentum|conserved]] quantity defined as the product of the [[Mass|mass]] $m$ of some object and that object's [[Velocity|velocity]] $\mathbf{\vec{v}}$. Linear momentum is a [[Vector|vector]] quantity and it is measured in [[Kilogram|kilogram]]-[[Metre|metres]] per [[Second|second]] $[\pu{ kg \cdot m/s}]$. It is commonly denoted with a $\mathbf{\vec{p}}$.  
$$
\mathbf{\vec{p}}=m\mathbf{\vec{v}}
$$
# Relation to force

Recall [[Newton's Laws|Newton's second law]]:
$$
\sum \mathbf{\vec{F}}=m\mathbf{\vec{a}}
$$
Since [[Acceleration|acceleration]] is the [[Time|time]] [[Derivative|derivative]] of velocity,
$$
\sum \mathbf{\vec{F}}=m\frac{d\mathbf{\vec{v}}}{dt}
$$
Mass is constant, so we can bring it inside of the derivative,
$$
\sum \mathbf{\vec{F}}=\frac{d(m\mathbf{\vec{v}})}{dt}=\frac{d\mathbf{\vec{p}}}{dt}
$$
Therefore the time rate of change of linear momentum is equivalent to the net [[Force|force]] acting on the object. In fact, this form of Newton's second law is the form in which [[Isaac Newton|Newton]] originally presented it. This form of the second law makes modelling force possible when mass is not constant, such as when a rocket is launching and its mass is decreasing due to fuel consumption.

# Total linear momentum of a system

The velocity of the [[Centre of Mass|centre of mass]] of a system is,
$$
\mathbf{\vec{v}}_{\text{CM}}=\frac{1}{M}\displaystyle \sum_{i}m_{i}\mathbf{\vec{v}}_{i}
$$
where $\mathbf{\vec{v}}_{i}$ is the velocity of the $i$th particle. Rearranging, we get
$$
M\mathbf{\vec{v}}_{\text{CM}}=\displaystyle \sum_{i}m_{i}\mathbf{\vec{v}}_{i}=\displaystyle \sum_{i} \ \mathbf{\vec{p}}_{i}=\mathbf{\vec{p}}_{\text{T}}
$$
where $\mathbf{\vec{p}}_{\text{T}}$ is the total linear momentum of the system. Therefore the total linear momentum of a system is the total mass of that system multiplied by the velocity of the centre of mass.