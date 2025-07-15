---
tags:
  - canadian-electrical-code
---
# Section 14 — Protection and control
# General Requirements
## 14-012 Ratings of protective and control equipment
> In circuits of $750\ \mathrm{V}$ or less,
> <span>&emsp;</span>a) electrical equipment required to interrupt fault currents shall have ratings sufficient for the voltage employed and for the fault current that is available at the terminals; and
> <span>&emsp;</span>b) electrical equipment required to interrupt current at other than fault levels shall have ratings sufficient for the voltage employed and for the current it must interrupt.
# 14-100 Overcurrent protection of conductors

> 1) Each ungrounded conductor shall be protected by an overcurrent device at the point where it receives its supply of current and at each point where the size of conductor is decreased, except that such protection shall be permitted to be omitted in each of the following cases:
> 	<span>&emsp;</span>a) where the overcurrent device in a larger conductor properly protects the smaller conductor;
> 	<span>&emsp;</span>b) where the smaller conductor
> 			<span>&emsp;</span><span>&emsp;</span>i) has an ampacity not less than the combined computed loads of the circuits supplied by the smaller conductor and not less than the ampere rating of the switchboard, panelboard, or control device supplied by the smaller conductor;
> 	<span>&emsp;</span><span>&emsp;</span>ii) is not over 3 m long;
> 	<span>&emsp;</span><span>&emsp;</span>iii) does not extend beyond the switchboard, panelboard, or control device that it supplies; and
> 	<span>&emsp;</span><span>&emsp;</span>iv) is enclosed in non-ventilated raceways, armoured cable, or metal-sheathed cable when not part of the wiring in the switchboard, panelboard, or other control devices;
> 	<span>&emsp;</span>c) where the smaller conductor
> 		<span>&emsp;</span><span>&emsp;</span>i) has an ampacity not less than one-third that of the larger conductor from which it is supplied; and
> 		<span>&emsp;</span><span>&emsp;</span>ii) is suitably protected from mechanical damage, is not more than 7.5 m long, and terminates in a single overcurrent device rated or set at a value not exceeding the ampacity of the conductor, but beyond the single overcurrent device the conductor shall be permitted to supply any number of overcurrent devices;
> 	<span>&emsp;</span>d) where the conductor
> 		<span>&emsp;</span><span>&emsp;</span>i) forms part of the only circuit supplied from a power or distribution transformer rated over 750 V with primary protection in accordance with [[CEC s.26#26-250 Overcurrent protection for power and distribution transformer circuits rated over $750 pu{ V}$|Rule 26-250]] 1), 2), and 3) and that supplies only that circuit;
> 		<span>&emsp;</span><span>&emsp;</span>ii) terminates at a single overcurrent device with a rating not exceeding the ampacity of the conductor(s) in the circuit; and
> 		<span>&emsp;</span><span>&emsp;</span>iii) is protected from mechanical damage;
> 	<span>&emsp;</span>e) where the smaller conductor is No. 14 AWG or larger, is in a control circuit, and is located external to the control equipment enclosure, and
> 		<span>&emsp;</span><span>&emsp;</span>i) the rating or setting of the branch circuit overcurrent device is not more than 300% of the ampacity of the control circuit conductor; or
> 		<span>&emsp;</span><span>&emsp;</span>ii) the opening of the control circuit would create a hazard;
> 	<span>&emsp;</span>f) where the smaller conductor supplies a transformer, and
> 		<span>&emsp;</span><span>&emsp;</span>i) the conductor supplying the primary of the transformer has an ampacity not less than one-third that of the larger conductor;
> 		<span>&emsp;</span><span>&emsp;</span>ii) the conductor supplied by the secondary of the transformer has an ampacity not less than the ampacity of the primary conductor multiplied by the ratio of the primary to the secondary voltage;
> 		<span>&emsp;</span><span>&emsp;</span>iii) the total length of one primary plus one secondary conductor (the longest, if more than one winding), excluding any portion of the primary conductor that is protected at its own ampacity, does not exceed 7.5 m;
> 		<span>&emsp;</span><span>&emsp;</span>iv) the primary and secondary conductors are protected from mechanical damage; and
> 		<span>&emsp;</span><span>&emsp;</span>v) the secondary conductor terminates in a single overcurrent device rated or set at a value not exceeding its ampacity; or
> 	<span>&emsp;</span>g) where the smaller conductor
> 		<span>&emsp;</span><span>&emsp;</span>i) is supplied by a circuit at not more than 750 V;
> 		<span>&emsp;</span><span>&emsp;</span>ii) is supplied from an overhead or underground circuit and is run overhead or underground except where it enters a building;
> 		<span>&emsp;</span><span>&emsp;</span>iii) is installed in accordance with the requirements of Section 6; and
> 		<span>&emsp;</span><span>&emsp;</span>iv) terminates in service equipment in accordance with [[CEC s.6|Section 6]].

In summary, an ungrounded conductor requires overcurrent protection unless:
1. If it is a smaller conductor connected to a larger conductor, the larger conductor already has an o/c device that covers the smaller conductor.
2. If it is a smaller conductor, if the conductor is adequately sized to handle the rest of the current, is not longer than $3\ \mathrm{m}$ and doesn't extend past the device it supplies. If it isn't part of a switchboard or panel, then it needs to be in plenum, armoured cable, or metal-sheathed cable.
3. If it is a smaller conductor, if its ampacity is not less than $\frac{1}{3}$ of the larger conductor's ampacity, not more than $7.5\ \mathrm{m}$ long, and terminates in a single o/c device.
4. If the conductor is the secondary of a transformer that has adequate protection on the primary side (see [[CEC s.26#26-250 Overcurrent protection for power and distribution transformer circuits rated over $750 pu{ V}$|26-250]]) and terminates in a single o/c device.
5. If it is a smaller conductor and $> \#14$ AWG in a control circuit, the rating of the o/c device can't be more than $3$ times the ampacity of the smaller control conductor. The opening of this control circuit must be demonstrated to create a hazard for this to apply.
6. If the conductor supplies the primary of a transformer and has an ampacity not less than $\frac{1}{3}$ the ampacity of the larger conductor
# 14-102 Ground fault protection

> 1) Ground fault protection shall be provided to de-energize all normally ungrounded conductors of a faulted circuit that are downstream from the point or points marked with an asterisk in [[CEC d.3|Diagram 3]] in the event of a ground fault in those conductors as follows:
> 	<span>&emsp;</span>a) for circuits of solidly grounded systems rated more than 150 volts-to-ground, less than 750 V phase-to-phase, and 1000 A or more; and
> 	<span>&emsp;</span>b) for circuits of solidly grounded systems rated 150 V or less to ground and 2000 A or more.
> 2) Except as permitted by Subrule 8), the maximum setting of the ground fault protection shall be $1200\ \mathrm{A}$ and the maximum time delay shall be $1\ \mathrm{s}$ for ground fault currents equal to or greater than $3000\ \mathrm{A}$.
> 3) The ampere rating of the circuits referred to in Subrule 1) shall be considered to be
> 	<span>&emsp;</span>a) the rating of the largest fuse that can be installed in a fusible disconnecting device;
> 	<span>&emsp;</span>b) the highest trip setting for which the actual overcurrent device installed in a circuit breaker is rated or can be adjusted; or
> 	<span>&emsp;</span>c) the ampacity of the main conductor feeding the devices located at points marked with an asterisk in Item 2 of [[CEC d.3|Diagram 3]], in the case where no main disconnecting device is provided.
> 4) This protection shall be provided by
> 	<span>&emsp;</span>a) an overcurrent device that incorporates ground fault protection;
> 	<span>&emsp;</span>b) a ground fault tripping system consisting of a sensor(s), relay, and auxiliary tripping mechanism; or
> 	<span>&emsp;</span>c) other means.
> 5) The sensor(s) referred to in Subrule 4) shall be
> 	<span>&emsp;</span>a) sensors that vectorially totalize the currents in all conductors of the circuit, including the grounded circuit conductor, where one is provided, but excluding any current flowing in the ground fault return current path;
> 	<span>&emsp;</span>b) sensors that sense ground fault current flowing from the fault to the supply end of the system through the ground return path; or
> 	<span>&emsp;</span>c) a combination of these two types of sensors
> 6) Sensors referred to in Subrule 5) a) shall be permitted to be installed at any point between the supply transformer and the downstream side of the disconnecting means marked with an asterisk in [[CEC d.3|Diagram 3]], but if located downstream from this disconnecting means, the sensors shall be placed as close as practicable to its load terminals.
> 7) Sensors referred to in Subrule 5) b) shall be located on each connection between neutral and ground; however, where the neutral is grounded both at the supply transformer and at the switching centre, the sensor at the transformer shall not be required, provided that the maximum pickup setting of the ground fault relay does not exceed $1000\ \mathrm{A}$.
> 8) In ground fault schemes where two or more protective devices in series are used for ground fault coordination, the upstream protective device settings shall be permitted to exceed those specified in Subrule 2) where necessary to obtain the desired coordination, provided that the final downstream ground fault protective device in each circuit required to be protected conforms to the requirements of Subrule 2).
# 14-104 Rating of overcurrent devices
> 1) The rating or setting of overcurrent devices shall not exceed the allowable ampacity of the conductors that they protect, except
>	<span>&emsp;</span>a) where a [[Fuse|fuse]] or [[Circuit Breaker|circuit breaker]] having a rating or setting of the same value as the ampacity of the [[Conductor|conductor]] is not available, and the maximum calculated or known load is in accordance with the Rules of [[CEC s.8|Section 8]], the ratings or settings given in [[CEC t.13|Table 13]] shall be permitted to be used within the maximum value of 800 A;
>	<span>&emsp;</span>b) in the case of equipment wire, flexible cord in sizes Nos. 16, 18, and 20 AWG copper, and tinsel cord, which are considered protected by $15\ \mathrm{A}$ or $20\ \mathrm{A}$ overcurrent devices; or
>	<span>&emsp;</span>c) as provided for by other Rules of this Code.

That is, *if the calculated ampacity of the circuit does not have a 1:1 corresponding circuit breaker, we can use [[CEC t.13|Table 13]] to determine an appropriate [[Overcurrent Device|overcurrent device]].*
![[CEC t.13]]

The "others" in c) would apply to things like motors (see [[CEC s.28]]) or welders (see [[CEC s.42]]). 
## 2)
> Except as provided for by Subrule 1) c), the rating of overcurrent protection shall not exceed
> 	a) $15\ \mathrm{A}$ for No. 14 AWG copper conductors;
> 	a) $20\ \mathrm{A}$ for No. 12 AWG copper conductors;
> 	a) $30\ \mathrm{A}$ for No. 10 AWG copper conductors;
> 	a) $15\ \mathrm{A}$ for No. 12 AWG aluminum conductors; and
> 	a) $25\ \mathrm{A}$ for No. 10 AWG aluminum conductors;
# 14-402 Disconnecting means required for fused circuits
> Circuits protected by fuses shall be equipped with disconnecting means, integral with or adjacent to the fuseholders, whereby all live parts for mounting fuses can be readily and safely made dead; however, such disconnecting means shall be permitted to be omitted in any one of the following cases:
> 	a) instrument and control circuits on switchboards where the voltage does not exceed 250 V;
> 	b) primary circuits of voltage transformers having a primary voltage of 750 V or less, on switchboards; and
> 	c) a circuit having only one ungrounded conductor where a plug fuse is used.
# 14-404 Control devices ahead of overcurrent devices
> Control devices used in combination with overcurrent devices or overload devices for the control of circuits of apparatus shall be connected so that the overcurrent or overload devices will be dead when the control device is in the open position, except where this is impracticable.
# 14-406 Location of control devices
## 1)
> Control devices, with the exception of isolating switches, shall be readily accessible.
## 2)
> Remotely controlled devices shall be considered to be readily accessible if the means of controlling them are readily accessible.
# 14-408 Indication of control device positions
> Manually operable control devices shall indicate the ON and OFF positions, unless the application of the devices makes this requirement unnecessary.
# 14-410 Enclosure of control devices
> Control devices, unless they are located or guarded in a way that renders them inaccessible to unauthorized persons and prevents fire hazards, shall have all current-carrying parts in enclosures of metal or other fire-resisting material.
# 14-412 Grouping of control devices
> Control devices controlling feeders and branch circuits shall be grouped where practicable.
# 14-414 Connection to different circuits
## 1)
> Where electrical equipment is supplied by two or more different transformers or other different sources of voltage, then
> 	a) a single disconnecting means that will effectively isolate all ungrounded conductors supplying the equipment shall be provided integral with or adjacent to the equipment; or
> 	b) each supply circuit shall be provided with a disconnecting means integral with or adjacent to the equipment, and the disconnecting means shall be grouped together.
# 14-416 Control devices used only for switching
> Except as permitted by other Rules in this Code, control devices that perform only switching functions shall disconnect all ungrounded conductors of the controlled circuit when in the OFF position.
# 14-600 Protection of receptacles
> Receptacles shall not be connected to a branch circuit having overcurrent protection rated or set at more than the ampere rating of the receptacle, except as permitted by other Sections of this Code.
# 14-602 Additional control devices not necessary
> Portable appliances need not be equipped with additional control devices where the appliances are
> 	a) rated at not more than $1500\ \mathrm{W}$; and
> 	b) provided with cord connectors, attachment plugs, or other means by which they can be disconnected readily from the circuits.
# 14-604 Outlet control from more than one point
> Where switches are used to control an outlet or outlets from more than one point, the switches shall be connected so that all switching is done only in the ungrounded circuit conductor.
# 14-606 Panelboard overcurrent protection
## 1)
> Except for panelboards where more than $90\%$ of the overcurrent devices supply feeders or motor branch circuits, every panelboard shall be protected on the supply side by overcurrent devices having a rating not greater than that of the panelboard.
## 2)
> The overcurrent protection required by Subrule 1) shall be permitted to be in the primary of a transformer supplying the panelboard, provided that the panelboard rating in amperes is not less than the overcurrent rating in amperes multiplied by the ratio of the primary to the secondary voltage.

In other words, say we have a $100\ \mathrm{A}$ panel fed by a $600-208$ transformer ($a=2.885$). The o/c device on the primary side must be $35\ \mathrm{A}$.
$$
I_{\mathrm{OC-Panel}}=I_{\mathrm{OC-Pri}}\ \cdot a
$$
# 14-608 Remote control circuits
> Remote control circuits of remotely controlled apparatus shall be arranged so that they can be conveniently disconnected from their source of supply at the controller, but as an alternative the disconnecting of the apparatus from the supply circuit shall be permitted to be arranged so that it also disconnects the remote control circuit from the supply circuit.