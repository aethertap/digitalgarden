---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/tank-bot-sensors/"}
---


#  Using sensors to control your tank

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


### Lesson-specific resource links

- https://dspace.mit.edu/bitstream/handle/1721.1/119149/16-412j-spring-2005/contents/projects/1aslam_blas_repo.pdf 
- https://medium.com/machinevision/implement-slam-from-scratch-b1fb599f40c8 
- https://medium.com/machinevision/overview-of-slam-50b7f49903b7

- ***[[projects/school-fall-2024/programming/programming-projects/tank-battle-game\|Project index: tank-battle-game]]*** 
## Concept summary and lesson


- Sensor-based control 
- SLAM - Simultaneous Localization and Mapping 
- What is localization? 
- How to build a map in a robot's brain 

## Examples/demo

Your tanks now have..... RADAR! RADAR is RAdio Distance And Range, by the way. Today, we're writing code that will let the tank use the radar to explore its environment.

When your tank gets started now, you'll have some new data in the `sensors` structure. At the moment, it only tells you when it finds a wall, and how far the wall is from you. Here's how it works:
- If there is no wall detected, `sensors.wall` is -1
- If a wall is detected, `sensors.wall` has *the distance to the wall, in the direction that the radar is currently pointing*. You'll have to use `sensors.radar_angle` to get that part.
- The radar angle is always relative to the direction the tank is pointed, so you'll want to add them together to see where the wall actually is.
- The radar *doesn't tell you which way the wall is oriented!* You have to figure that out using two or more points along the wall, which you can then subtract from each other to get a direction vector

This "radar" is actually pretty similar in its capabilities to your ultrasonic sensors, or a lidar sensor. For game reasons, the radar can differentiate friend from foe and also identify when it's bouncing off of terrain, but a real sensor wouldn't do that.

### Changes to the tank-battle game

- `Controls.turn_radar` is active, and accepts a positive or negative angular velocity. Positive indicates clockwise. The maximum turn speed is $2\pi\frac{ \text{radians}}{\text{second} }$
- `Controls.turn_gun` is active, similar to `turn_radar`. It's maximum speed is $\pi \frac{\text{radians}}{\text{second}}$ 
- The turret has a simple representation in the window now, so you can see which way it's pointing
- The radar sweep can be visible if you set `Controls.show_radar` to `true`
- You can output messages to the screen using `TankAPI.println`. Any numbers your give it will automatically be limited to three decimal places, and the output refreshes every frame
- You can pause, single-step, and resume the simulation, both by pressing a button on the page, and by calling `api.pause()` from within your code. This makes it a lot easier to see what's happening 

### Other sensors we can add

Since we have a tank with sensors now, we might consider having some other kinds of data about the world:

- Color sensor. Your tank gets a paint gun that can mark various colors on the ground, and it can sense the color of the ground beneath it.
- Field strength. Your tank can sense some kind of *field* that varies in strength. It could be a smell, an electric field, etc. 
- Message relay. You can send messages to other tanks in your team, maybe to coordinate actions?

### Other cool stuff that doesn't exist yet

- What if your tank had a limited number of beacons that it could fire from the gun? The beacon sticks to whatever it hits, and from that point on you always know the direction and distance to it.
- A limited boost to double your speed for a short time
- Shooting down other tanks' bullets
- A cargo spot, for games like capture the flag. The tank can pick something up and carry it around.


## Media resources

- [Youtube search for "Sensor-based control"](https://www.youtube.com/results?search_query=Sensor-based%20control) 
- [Youtube search for "SLAM - Simultaneous Localization and Mapping"](https://www.youtube.com/results?search_query=SLAM%20-%20Simultaneous%20Localization%20and%20Mapping) 
- [Youtube search for "What is localization?"](https://www.youtube.com/results?search_query=What%20is%20localization?) 
- [Youtube search for "How to build a map in a robot's brain"](https://www.youtube.com/results?search_query=How%20to%20build%20a%20map%20in%20a%20robot's%20brain) 


## Exercises

- [ ] #hw (programming) Make your tank drive around the arena using the radar to sense where the walls are. [[2025-02-26\|2025-02-26]]
