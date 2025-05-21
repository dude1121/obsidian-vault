---
tags:
  - instrumentation
---
A **rotary encoder** is a device that can measure the analog position and/or speed of a rotating device such as a motor or potentiometer into a analog or digital output signal.
# Types
## Optical encoder
An optical encoder makes use of an [[Optical Sensor|optical sensor]] and a plate with a series of slits. As the shaft of a motor rotates, the plate rotates too, constantly interrupting the optical beam at a given frequency according to the speed of rotation.
![[optical-encoder.jpg]]
The resolution of an optical encoder can be increased by adding more channels to the encoder. This allows a much more accurate measurement than using only a few channels. For example, an encoder with 4 rows of slits, each offset to give unique values for the encoder, can give a precise position of the rotor even at rest. This is called an *absolute encoder*.

More encoder lines however means more maintenance and a higher cost. In other encoders, fewer channels are used meaning the position is not as accurate, but these encoders are cheaper and often more reliable. These are called *incremental encoders*. 
## Hall effect encoder
A [[Hall Effect Sensor|Hall effect sensor]] can also be used as a rotary encoder. In this case, the hall effect sensor can be used to detect when a magnetic north or south pole is near the sensor. A digital hall effect sensor will then output a digital signal depending on if there is a magnetic field present or not. 
![[hall-effect-rotary.png]]