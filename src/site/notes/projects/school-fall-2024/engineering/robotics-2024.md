---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/robotics-2024/"}
---


# Full-stack robotics

This year we will be designing robots from the ground up, using CAD ([[projects/school-fall-2024/engineering/cad-with-onshape\|cad-with-onshape]]) to design 3d-printed mechanical components, arduino or ESP32 programming for behavior, and various sensor modules for sensing.

<h3><span>Scheduled classes</span></h3><div><ul class="dataview list-view-ul"><li><span>(Not Scheduled): <a data-tooltip-position="top" aria-label="projects/school-fall-2024/engineering/lessons/building-a-photogate.md" data-href="projects/school-fall-2024/engineering/lessons/building-a-photogate.md" href="projects/school-fall-2024/engineering/lessons/building-a-photogate.md" class="internal-link" target="_blank" rel="noopener nofollow">building-a-photogate</a></span></li><li><span>2025-01-07: <a data-tooltip-position="top" aria-label="projects/school-fall-2024/engineering/lessons/photo-gate-design.md" data-href="projects/school-fall-2024/engineering/lessons/photo-gate-design.md" href="projects/school-fall-2024/engineering/lessons/photo-gate-design.md" class="internal-link" target="_blank" rel="noopener nofollow">photo-gate-design</a></span></li><li><span>2025-01-14: <a data-tooltip-position="top" aria-label="projects/school-fall-2024/engineering/lessons/engineering-process.md" data-href="projects/school-fall-2024/engineering/lessons/engineering-process.md" href="projects/school-fall-2024/engineering/lessons/engineering-process.md" class="internal-link" target="_blank" rel="noopener nofollow">engineering-process</a></span></li><li><span>2025-01-16: <a data-tooltip-position="top" aria-label="projects/school-fall-2024/engineering/lessons/prototype-testing.md" data-href="projects/school-fall-2024/engineering/lessons/prototype-testing.md" href="projects/school-fall-2024/engineering/lessons/prototype-testing.md" class="internal-link" target="_blank" rel="noopener nofollow">prototype-testing</a></span></li><li><span>2025-01-21: <a data-tooltip-position="top" aria-label="projects/school-fall-2024/engineering/lessons/photogate-and-robot.md" data-href="projects/school-fall-2024/engineering/lessons/photogate-and-robot.md" href="projects/school-fall-2024/engineering/lessons/photogate-and-robot.md" class="internal-link" target="_blank" rel="noopener nofollow">photogate-and-robot</a></span></li><li><span>2025-01-21: <a data-tooltip-position="top" aria-label="projects/school-fall-2024/engineering/lessons/testing-photogate-prototype.md" data-href="projects/school-fall-2024/engineering/lessons/testing-photogate-prototype.md" href="projects/school-fall-2024/engineering/lessons/testing-photogate-prototype.md" class="internal-link" target="_blank" rel="noopener nofollow">testing-photogate-prototype</a></span></li><li><span>2025-01-23: <a data-tooltip-position="top" aria-label="projects/school-fall-2024/engineering/lessons/engr-project-time-1-23.md" data-href="projects/school-fall-2024/engineering/lessons/engr-project-time-1-23.md" href="projects/school-fall-2024/engineering/lessons/engr-project-time-1-23.md" class="internal-link" target="_blank" rel="noopener nofollow">engr-project-time-1-23</a></span></li></ul></div>
[[projects/school-fall-2024/lesson-index\|lesson-index]]

## Projects

### Basic Differential Chassis (Complete)

Design a basic differential-steering robot chassis. It must have mounting points for motors, battery pack, and control circuitry including an Arduino UNO or Nano.


- [ ] This is a cool RC car project that we might tackle in a year or two: [AWD 2-speed RC car](https://www.instructables.com/3D-Printed-Remote-Controlled-2-speed-AWD-Car/) #remind/yearly 

### Line follower (In-progress)

**Progress tracked on the** [[projects/school-fall-2024/engineering/engineering-kanban\|Project Kanban]]

Goals:
- Use optical sensors to detect the position of a line
    - [How to use the IR sensor board](https://www.instructables.com/How-to-Use-the-IR-Obstacle-Avoidance-Sensor-on-Ard/)
- Generate corrective steering signals
- drive robot to follow path
    - If path is composed of line segments and tangent circular arcs
    - If path is 90-degree corners connected with straight segments
    - If path is unconstrained, including turns sharper than 90 degrees
- Fastest bot wins

Teaching: 

- Working with optical sensors
    - Hardware interface Hi/Lo pin, potentiometer for tuning
    - Arduino code
    - Turn radius of the line, thickness of the line, and designing the array of light sensors
    - Movement with differential steering

### Robot vacuum demo (Future)

Goals:
- Use bot sensors and estimation to build a map of a place
- Explore the space in a controlled way
- Score for contest: coverage percent divided by time
- (potential) make a bot that can be powered by a drill battery (3d print the connection).


### Robotic arm (Future)

We will build a robotic arm, using something like one of the following as a project guide:

- [BCN3D Moveo](https://www.thingiverse.com/thing:1693444) [github page](https://github.com/BCN3D/BCN3D-Moveo)
- [modular arm with go-pro standardized connections](https://www.thingiverse.com/thing:4546364)
- [HtM SCARA arm](https://howtomechatronics.com/projects/scara-robot-how-to-build-your-own-arduino-based-robot/)
- [HtM Arduino Arm with smartphone control](https://howtomechatronics.com/tutorials/arduino/diy-arduino-robot-arm-with-smartphone-control/)
- [OS-Arm](https://github.com/DDeGonge/OS-ARM)
- The disney [[rolling-diaphragm-piston-robot\|rolling-diaphragm-piston-robot]] might be a fun thing to try also.
- [Bowden-tube cable guide motion system](https://www.youtube.com/watch?v=0hGy4AxUOnk)
- [Annin Robotics AR4 Mk3](https://www.anninrobotics.com/) is a 0.2mm repeatability 6-axis open source industrial arm. Has kits that would put it at about $2k to build
- [Arctos arm](https://arctosrobotics.com/) is an open 3D-printable arm, not accurate enough for real cnc work but pretty cool

### Build a Rolling diaphragm actuator

![moving-cap-rolling-diaphragm.png](/img/user/projects/school-fall-2024/engineering/moving-cap-rolling-diaphragm.png)
