---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/engineering-kanban/"}
---


## Planned Tasks

- [ ] #hw (robotics) Make a test track for your robot with sheets of paper and black electrical tape. The bots are big, so the track will need to be very large (it should probably be laid out all over the floor of the workshop).
- [ ] #hw (robotics) Analyze what the biggest speed bottleneck is for your robot. What could you change about its behavior to make it follow the track faster? Write a technical report of 200-500 words that describes the problems you identified and proposes a step you can take to improve performance. It must be specific, measurable,  and achievable in a reasonable amount of time.
- [ ] #hw (robotics) Implement your proposed speedup changes.


## On-deck (ready)

- [ ] #hw (robotics) Create `pivot_left` and `pivot_right` methods for the `Robot` class that will cause it to turn in place to the left or right.
- [ ] #hw (robotics) Write a `follow_line` function that always pivots toward the sensor that last sensed the line. If no sensor sees the line (or if the center sensor sees it), it should drive forward.
- [ ] #hw (robotics) Analyze your robot's mechanical structure to see where it's weak points are. How could those be strengthened without overcomplicating your bot's build? What kind of forces are present and what kind of mechanical advantage is amplifiying them?
- [ ] Watch this [motors video](https://www.youtube.com/watch?v=-PCuDnpgiew) with the kids


## Quick tasks



## In-progress

- [ ] [[projects/school-fall-2024/engineering/engineering-projects/photo-gate-project\|photo-gate-project]] to build a set of photo gates for our physics lessons.


## Complete

- [x] #hw (robotics) Install IR sensors and do remaning bot assembly [[2024-12-10\|2024-12-10]]
- [ ] #hw (robotics) Create a Robot class with a drive_forward method that turns both servos in a way that will make your bot move forward.
- [ ] Make the photogate code use analogRead instead of digitalRead so that we can make it a bit more sensitive, since the phototransistor has a much higher internal resistance than I expected.
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




