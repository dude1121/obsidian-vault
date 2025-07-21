---
tags:
  - electrical-engineering
  - control-systems
---
A **Control System** is a model that consists of *subsystems* and *processes* assembled for the purpose of obtaining a desired *output* with desired *performance*, given a specified *input*. 
![[control-system.png]]
Above is the simplest possible control system, with a single input that represents the desired output. Control systems are typically built for four main reasons:
1. Power amplification
2. Remote control
3. Convenience of input form
4. Compensation for disturbances

For example, a radar antenna requires a large amount of [[Power|power]] from its low-power input knob to its output rotation. A control system can produce the needed power amplification, or [[Gain|gain]]. A robot arm can be used to pick up material in an environment harmful to humans, thus requiring a *remote control* system. A thermostat converts the input position of a knob into an output of heat, thus making position a convenient input form. 

Finally, a system may need to be adjusted during operation. For example, consider an antenna that is focused in one direction. If the wind pushes the antenna astray, or if there is noise present in the system, the system needs to be able to detect these changes and correct the antenna's position.
# System configurations
A control system can be said to have two major configurations: *open loop* and *closed loop*.
## Open loop system
![[open-loop-system.png]]
Above is a generic open loop system. It begins with a subsystem called the *Input [[Transducer|transducer]]*, which converts the form of the input to that used by the *controller*. The controller drives a *process* or *plant*. The input to the system is sometimes called the *reference* whereas the output is the *controlled variable*. Other signals such as *disturbances* are shown added to the controller and process outputs via *summing junctions*.

Open loop systems are unable to compensate for any disturbances and are simply commanded by the input. There is no feedback to allow the system to correct for errors that may arise during operation. 
## Closed loop system
![[closed-loop-system.png]]
Above is a generic closed loop system. It has all the components of an open loop system (i.e. transducers, controllers, plants, etc.) but also contains an *output transducer* or *sensor* that measures the output and converts it into the form used by the controller. 

The first summing junction adds the signal from the input to the signal from the output, which arrives via the *feedback path*, the return path from the output to the summing junction. In the example above, this output signal is subtracted from the input signal. The result is typically called the *actuating signal*. However, in systems where both the input and output transducers have unity gain, the actuating signal's value corresponds to the actual difference between the input and output. This difference is called the *error*. 

If there is any difference between the output signal and the intended response, then the system drives the plant via the actuating signal. If there is no difference, the plant is not driven, since the output signal already matches the expected response.

Closed loop systems are therefore much more accurate than open loop designs. They are less sensitive to noise, disturbances, and changes in the environment.  Transient response and steady-state error can be controlled more conveniently and with greater flexibility in closed-loop systems, often by a simple adjustment of gain (amplification) in the loop and sometimes by redesigning the controller. This redesign is called *compensating* the system and the resulting hardware is called a *compensator*. 

Closed loop systems are however by their very nature, more expensive and complex than open loop systems. Engineering control systems therefore requires considering the trade-off between the simplicity and low-cost of open-loop systems versus the accuracy and higher cost of closed-loop systems.