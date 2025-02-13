---
tags:
  - canadian-electrical-code
---
# 42-002 Special terminology
**[[Duty Cycle]]** - the ratio of the time during which the [[Welder|welder]] is loaded to the total time required for one complete operation.
	- This information is typically available on the welder's nameplate given as a percentage
# 42-004 Receptacles and attachment plugs
## 1)
> Where a welder is cord-connected, the rating of the [[Receptacle|receptacle]] and attachment plug shall be permitted to be less than the rating of the [[Overcurrent Device|overcurrent devices]] protecting them, but not less than the rated primary current of the cord-connected welder.
## 2)
> Where a welder receptacle is installed, it shall be labelled to indicate
> 		a) the receptacle is intended for welder connection use only;
		b) the receptacle supply conductor [[AWG]] size;
		c) the supply conductor composition (i.e. "Cu" or "Al");
		d) the supply conductor insulation designation and its temperature rating; and
		e) the [[Amperes|ampere]] rating of the overcurrent device protecting the receptacle supply conductors based on the duty rating of the overcurrent device (i.e., $80\%$ or $100\%$).

# Transformer arc welders and inverter welders
## 42-006 Supply conductors
### 1)
> The insulated supply conductors for an individual [[Transformer|transformer]] [[Welder#Arc welder|arc welder]] or [[Welder#Inverter welder|inverter welder]] shall have an ampacity of not less than the value obtained by multiplying the rated primary current of that welder in amperes by the applicable factor from [[CEC t.42A|Table 42A]].
![[CEC t.42A]]
### 2)
> The insulated supply conductors for a group of transformer arc welders or inverter welders shall have an ampacity not less than the sum of the currents determined for each welder in the group in accordance with Subrule 1) multiplied by a demand factor or
> a) $100\%$ of the two largest calculated currents of the welders in the group; plus
> b) $85\%$ of the third largest calculated current of the welders in the group; plus
> c) $70\%$ of the fourth largest calculated current of the welders in the group; plus
> d) $60\%$ of the calculated currents of all remaining welders in the group.
### 3)
> Lower values than those given in Subrule 2) shall be permitted in cases where the work is such that a high operating duty cycle for individual welders is impossible.

## 42-008 Overcurrent protection for transformer arc welders and inverter welders
### 1)
> Each transformer arc welder and inverter welder shall have overcurrent protection rated or set at not more than $200\%$ of the rated primary current of the welder, unless the overcurrent device protecting the insulated supply conductors meets this requirement.
### 2)
> Each ungrounded conductor supplying a transformer arc welder and inverter welder shall have overcurrent protection rated or set at not more than $200\%$ of the ampacity of the insulated conductor as specified in table [[CEC t.1|1]], [[CEC t.2|2]], [[CEC t.3|3]], or [[CEC t.4|4]], except that the next higher rating or setting shall be permitted to be used where
> a) the nearest standard rating of the overcurrent device is less than the rating or setting otherwise required by this Rule; or
> b) the rating or setting otherwise required by this Rule results in too frequent opening of the overcurrent device.

That is, to size the overcurrent device, take $2\text{x}$ the welder full load current and take $2\text{x}$ the conductor ampacity from the appropriate table and choose the smaller of the two values.
### 3)
> The maximum rating or setting of an overcurrent device protecting a feeder supplying a group of transformer arc welders and inverter welders shall not exceed a value calculated by determining the maximum rating or setting of overcurrent protection and adding to this value the sum of ampacities as calculated by Rule [[#42-006 Supply conductors|42-006]] 1) for all other welders in the group.