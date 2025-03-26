---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/engineering-kanban/"}
---


## Project Ideas

- [ ] Tethered balloon wildfire observer platform. It would float up hundreds of feet into the air, then use a simple computer vision setup to look for fires and report their location back to the ground wirelessly.
- [ ] AI assisted tool-path generation for CAM. If an open source AI model could be created that would generate a tool path for machining an object given a 3d model of it.
- [ ] Make an autonomous vehicle simulation using the [CARLA simulator](https://carla.org/)


## Engineering Skills

- [ ] Watch this [motors video](https://www.youtube.com/watch?v=-PCuDnpgiew) with the kids
- [ ] #hw (robotics) Make a test track for your robot with sheets of paper and black electrical tape. The bots are big, so the track will need to be very large (it should probably be laid out all over the floor of the workshop).
- [ ] #hw (robotics) Analyze what the biggest speed bottleneck is for your robot. What could you change about its behavior to make it follow the track faster? Write a technical report of 200-500 words that describes the problems you identified and proposes a step you can take to improve performance. It must be specific, measurable, and achievable in a reasonable amount of time.
- [ ] #hw (robotics) Implement your proposed speedup changes.


## Bot features

- [ ] #hw Drive the bots around on a simple oval track, two straight sections, two semicircles. Debug and optimize the line-following code [[2025-04-01\|2025-04-01]]
- [ ] #hw Oval track time trials, two laps in each direction around the track, 30 minutes to work on code, then repeat. Winner picks dinner! [[2025-04-03\|2025-04-03]]
- [ ] #hw Introducing a 6-axis IMU - [MPU6050](https://components101.com/sensors/mpu6050-module) [HowtoMech tutorial](https://howtomechatronics.com/tutorials/arduino/arduino-and-mpu6050-accelerometer-and-gyroscope-tutorial/) Prototype a circuit that reads data from the mpu6050 and displays it to the serial port [[2025-04-08\|2025-04-08]]
- [ ] #hw Create a class to interface with the mpu6050. You'll need to look at the [I2C serial interconnect protocol tutorial](https://learn.sparkfun.com/tutorials/i2c/all) to see how to use it [[2025-04-10\|2025-04-10]]
- [ ] #hw Use the IMU to implement an `angle` function that measures the current orientation and returns it as an angle. [[2025-04-15\|2025-04-15]]
- [ ] #hw Use the IMU to implement `move_by` and `turn_by`, which each take a number and either move that far or turn by that amount.  [[2025-04-22\|2025-04-22]]
- [ ] #hw Use the `turn_by` and `move_by` to implement `drive_to`, which takes an x, y coordinate relative to the current position at angle 0 (set when bot started) and drives there. [[2025-04-24\|2025-04-24]]
- [ ] #hw Add an [[ultrasonic-range-sensor\|ultrasonic-range-sensor]] to your bot.


## Quick tasks

- [x] #teacher Add [the engineer guy's youtube channel](https://www.youtube.com/@engineerguyvideo/playlists) to the engineering curriculum [[2025-02-05\|2025-02-05]]


## In-progress

- [ ] [[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|differential-steering-bot]]: Connect the IR obstacle sensors to the board and add them to the control loop. Write code to test each sensor one at a time to avoid interference.
- [x] #hw Final assembly of v2 [[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|differential-steering-bot]], and test the state machine implementation with all parts active. [[2025-03-27\|2025-03-27]]


## Complete

**Complete**
- [x] Fix the caster wheel mount so that the screws don't interfere with the turning of the caster.
- [x] [[projects/school-fall-2024/engineering/engineering-projects/photo-gate-project\|photo-gate-project]] to build a set of photo gates for our physics lessons.
- [x] #hw (robotics) Create `pivot_left` and `pivot_right` methods for the `Robot` class that will cause it to turn in place to the left or right.
- [x] #hw (robotics) Install IR sensors and do remaning bot assembly [[2024-12-10\|2024-12-10]]
- [x] #hw (robotics) Create a Robot class with a drive_forward method that turns both servos in a way that will make your bot move forward.
- [x] Make the photogate code use analogRead instead of digitalRead so that we can make it a bit more sensitive, since the phototransistor has a much higher internal resistance than I expected.
- [x] #hw (robotics) Design a very simple 3d printable chassis platform shape for a simple differential-steering robot [[2024-09-12\|2024-09-12]]
- [x] #hw (robotics) Measure battery voltage to make sure it's within safe limits for arduino, then connect battery to arduino via dpst switch [[2024-12-10\|2024-12-10]]
- [x] #hw (robotics) Write code for your robot that can tell the difference between white and black for an IR sensor. It should print a line to the serial port that states what it senses. You will probably need to adjust the sensitivity on the IR sensor board (there's a tiny screw on a potentiometer). [[2024-12-11\|2024-12-11]]
- [x] #hw (robotics) Measure and model a micro-servo so that it can be mounted to the chassis [[2024-09-17\|2024-09-17]]
- [x] #hw (robotics) Design mounting system for micro-servo on the chassis and 3d print a physical model [[2024-09-25\|2024-09-25]]
- [x] #hw (robotics) Charge LiPO battery packs [[2024-12-09\|2024-12-09]]
- [x] #hw (robotics) Add mounts for an arduino [[2024-09-30\|2024-09-30]]
- [x] #hw (robotics) LiPo battery pack to the chassis design [[2024-10-08\|2024-10-08]]
- [x] #hw (robotics) Search online to find a design or tutorial for line-follower robots using arduino. Put the link and a description in a file in obsidian. [[2024-09-24\|2024-09-24]]
- [x] #hw (robotics) Hook up one of the continuous rotation servos to your arduino uno and experiment with it using the Servo library [[2024-11-01\|2024-11-01]]
- [x] modeling a real-world object in CAD
- [x] Designing an interface to attach two things to each other
- [x] Making an assembly in CAD
- [x] Considering manufacturability (what if it can't be 3d printed)
- [x] #teacher [[how-servos-work\|how-servos-work]] reminder, with programming assignment [[2024-11-01\|2024-11-01]],
- [x] #hw Research how line-follower robots work [[2024-10-01\|2024-10-01]]
- [x] #hw Model the IR sensor board [[2024-10-03\|2024-10-03]]
- [x] #hw (robotics) Connect IR sensor to arduino and write code to detect when something is in front of it. [[2024-11-15\|2024-11-15]]
- [x] #hw (robotics) Design mount for sensors on chassis [[2024-11-15\|2024-11-15]]
- [x] #hw (robotics) Build robot physical structure




