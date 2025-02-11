---
tags:
  - electrical-engineering
  - electronics
---
A **dc-dc convertor** is a circuit that can step up or step down [[DC Electricity|dc]] [[Voltage|voltage]]. Technically speaking, the convertor is the dc equivalent of a [[Transformer|transformer]]. Dc-dc convertors are typically used in [[Switch-mode Power Supply|switch-mode power supplies]] since they have fewer losses than [[Voltage Regulator|voltage regulator]] ICs. 

Like their ac counterpart, dc-dc convertors have (ideally) the same input power as the output power. That is,
$$
P_{\ \text{in}}=P_{\ \text{out}}
$$
In reality of course there will be losses in the conversion process. The average efficiency is around $90\%$, meaning $10\%$ of the input power is lost. The type of dc-dc convertor varies depending on the output voltage value compared to the input.

| Voltage Status                                                           | Designation          |
| ------------------------------------------------------------------------ | -------------------- |
| $V_{\ \text{in}}>V_{\ \text{out}}$                                       | Buck Convertor       |
| $V_{\ \text{in}}<V_{\ \text{out}}$                                       | Boost Convertor      |
| $V_{\ \text{in}}>V_{\ \text{out}}$ or $V_{\ \text{in}}<V_{\ \text{out}}$ | Buck-Boost Convertor |

# Overview of design
![[dc-dc-overview.png]]
Any dc-dc convertor can be broken down into three main components: the *power section*, consisting of the convertor itself; the *gate driver*, a supplementary circuit that will energize the gate of the switching components; and the *PWM control*, a circuit that times the gate circuit using [[Pulse Width Modulation|pulse width modulation]]. This final part is typically done via software. 