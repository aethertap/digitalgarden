---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/sensor-driven-navigation/"}
---


#  Sensor-driven navigation

## Links and useful resources 

- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)

 
- ***[[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|Project index: differential-steering-bot]]*** 

## Concept summary and connections


- Using a sensor to control your motion 
- Observe-orient-decide-act (OODA) - the basic control loop 

## Lesson Content

We're going to start getting our bots to be controlled by their sensor packages. The first step is to make sure the senros actually work! So, today we're going to make sure that everything is fully wired together, and then we're going to write code to try to sense the status of our line sensors and tell us what it finds.

The bot should end up driving in a circle of about three feet diameter, and it should have two LEDs:
- A red LED that stays lit whenever *none* of the sensors detect the line
- A green LED that stays lit whenever *any* of the sensors detect the line.

We're not worried about following the line yet, just about **noticing** it.

There are two ways we could do this project: Hardware, and software.

The hardware approach would put an OR-gate on the output bits of all three of our sensors, and send the result to the green LED. A NOT-gate on the same output would work to control the red one. This would be a great way to solve the problem, but it doesn't let us know whether our **code** is working properly!

The software approach would use a few lines of arduino code to decide when to turn each of the LEDs on based on the data it's getting from the sensors. This is what we're going to do today, although if you're feeling ambitious you could *also* implement the hardware version in order to have a nice visual debugging tool. Remember that the sensors already have an LED that lights up when they get a reflection though, so we could get the same data by looking to see which sensors are on or off.


## Practice


- [x] #hw (engr) Add a pair of output LEDs to your bot, one green and one red. The red is on when the line is not detected, and the green is on when any sensor detects the line.  [[2025-03-04\|2025-03-04]]
- [x] #hw (engr) Write the code to control the output LEDs  [[2025-03-04\|2025-03-04]]
