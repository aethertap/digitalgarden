---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/driving-toward-the-wall/"}
---


#  Driving toward the wall

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


- ***[[projects/school-fall-2024/programming/programming-projects/tank-battle-game\|Project index: tank-battle-game]]*** 
## Concept summary and lesson


- sensor-based control 

## Examples/demo

Just like our [[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|differential-steering-bot]], our tanks need to start using their sensors to control their movement. In this case, we have the Radar, which can tell us the direction and distance to a target (so far, the only target is the wall). This assignment is about using that sensor data to drive toward the first spot on the wall that your radar detects. There are a few parts to this:

- Keeping track of which *direction* you need to be moving - you should be moving toward the *actual spot on the wall that your radar detected*, not just anywhere on the wall
- Keeping track of how *far* you need to go. The idea is to stop before you hit the wall, so that your distance is as close as possible to 30 (again, in the direction the radar specified).

You can either just take note of the direction and distance and move directly there, or you can keep the radar aimed at its spot and just drive until you're the right distance away. You can decide which way to do it, or you could try both.



## Media resources

- [Youtube search for "sensor-based control"](https://www.youtube.com/results?search_query=sensor-based%20control) 


## Exercises

- [ ] #hw (programming) Update your tank code so that it uses a Tank class that gets created in the setup function. Then change the code so that it drives toward the first wall it sees on the radar, and stops when it's 30 units away. [[2025-03-03\|2025-03-03]]
