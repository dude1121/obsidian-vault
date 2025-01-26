---
tags:
  - canadian-electrical-code
---
# 8-102 Voltage drop
## 1)
> The voltage drop in an installation shall be based on the connected load of the feeder or branch circuit if known; otherwise it shall be based on 80% of the rating of the overload or overcurrent device protecting the branch circuit or feeder, and not exceed
> 	a) 3% in a feeder or branch circuit; and
> 	b) 5% from the supply side of the consumer’s service (or equivalent) to the point of utilization.
> - [[Canadian Electrical Code|CEC, 25th Edition]]

The connected load voltage should be used if known, else use $80\%$ of the rating of the [[Overcurrent Device|overcurrent device]] to find the [[Voltage Drop|voltage drop]]. This calculated voltage drop can not be more than $3\%$ in a feeder or branch circuit and it can not be more than $5\%$ of the total service voltage.
# 8-104 Maximum circuit loading
## 5)
> Where a fused switch or circuit breaker is marked for continuous operation at 100% of the ampere rating of its overcurrent devices, the continuous load as determined from the calculated load shall not exceed the continuous operation marking on the fused switch or circuit breaker and
> 	a) except as required by Item b), shall not exceed 100% of the allowable ampacities of conductors selected in accordance with Section 4; or
> 	b) shall not exceed 85% of the allowable ampacities of single conductors selected in accordance with Section 4.
> - [[Canadian Electrical Code|CEC, 25th Edition]]

In other words, *if the equipment is designed to operate at 100% of its rating you can load the circuit to 100% capacity **if** the wiring is in a [[Raceway (Electrical)|raceway]] or [[Cable|cable]]. **If** the wiring is instead using single conductors, then you can load the circuit only to 85% capacity.* The ampacity of a given circuit is determined by the load of the circuit, and the [[Overcurrent Device|overcurrent device]] selected is determined by the ampacity (see [[CEC s.14#14-104|CEC s.14-104]])

However, in Canada, most equipment is designed for 80% load. This leads us to sentence 6)...
## 6)
>Where a fused switch or circuit breaker is marked for continuous operation at 80% of the ampere rating of its overcurrent devices, the continuous load as determined from the calculated load shall not exceed the continuous operation marking on the fused switch or circuit breaker and
>	a) except as required by Item b), shall not exceed 80% of the allowable ampacities of conductors selected in accordance with Section 4; or
>	b) shall not exceed 70% of the allowable ampacities of single conductors selected in accordance with Section 4.
>- [[Canadian Electrical Code|CEC, 25th Edition]]

That is, *since normal equipment is designed for 80% load in Canada, **if** the wiring is in a cable/raceway you can load the circuit to 80% capacity, **else** if it is a single conductor it can only be loaded to 70% capacity.*
# 8-304 Maximum number of outlets per circuit
## 1)
> Except as permitted by other Rules of this Code, the maximum number of outlets on any 2-wire branch circuit shall not exceed the following:
> 	a) 12 outlets for a 15 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 80%;
> 	b) 15 outlets for a 15 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 100%;
> 	c) 16 outlets for a 20 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 80%; and
> 	d) 20 outlets for a 20 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 100%.

| Rating  | Ampacity    | Max no. outlets |
| ------- | ----------- | --------------- |
| $80\%$  | $15\pu{ A}$ | $12$            |
| $80\%$  | $20\pu{ A}$ | $16$            |
| $100\%$ | $15\pu{ A}$ | $15$            |
| $100\%$ | $20\pu{ A}$ | $20$            |
**Note:** "Outlets" can be [[Electrical Receptacle|receptacles]] or [[Light Fixture|lights]]. In *residential* construction, lights and receptacles *can* be on the same circuit. In *commercial*/*industrial* applications, these loads are typically on separate circuits.

## 3)
> Where the connected load is known, the number of outlets shall be permitted to exceed the maximum number permitted in Subrule 1), provided that the load current does not exceed the continuous operation marking on the overcurrent device protecting the circuit.

If the connected load is something like lights, the load is known, and so long as the designer does not exceed the ampacity rating of the circuit, more than the maximum number of outlets may be used.