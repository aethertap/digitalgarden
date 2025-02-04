---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot/"}
---


# Differential-steering robot chassis

We are building a pair of line-following robots starting from scratch. The goal will be to have a bot that can detect a one-inch black line on a white background, and drive in a way so that it follows the line around a complex path through the workshop.

- The bot's wheels will be driven by continuous-rotation servos
- The line sensor is an IR obstacle detector board (or multiple)
- The chassis will be 3d-printed based on your own design

## Designs

- [gr7's chassis](https://cad.onshape.com/documents/d9c6e6e8b980254d1cd213e0/w/5bf74cf46dc59c707ecd62c0/e/2fe41bc957e6303d07efb8ef)
- [gr10's chassis](https://cad.onshape.com/documents/30dc5867e25152986bf0a4b8/w/b12c80e52f3bda255da12ea5/e/56d1fe69c20e71e1dd45dcc0)

## gr7's design

![gr7-assembled-robot-sm.jpg](/img/user/projects/school-fall-2024/engineering/engineering-projects/_resources/gr7-assembled-robot-sm.jpg)

- Large wheels
- Flat, open platform
- Dual-lug mount for servo attachment
- Movable mounting plates for IR sensors to allow vertical adjustment

### Issues so far

- Lug on left wheel broke when bot fell off table
- Caster wheel rotation is limited by protruding screw shafts, need to reverse the screws
- Size of bot may make accurate maneuver difficult, because the IR sensors are a long distance from the pivot point.

## gr10's design

- Large wheels
- Box-like enclosure
- Through-hole mount for servos
- Slotted attachment for IR sensors to allow vertical adjustment

### Issues so far

- Redesign required on wheel attachment due to impossibility of assembly initially (no way to reach the screws)
- Through-hole mounts for servos are difficult to 3D print due to large bridging requirements over top of hole, had to make big adjustment to account for that
- Several problems due to poor bed adhesion on the printer, cause isn't certain but flipping PEI plate has resolved it for now.

## Next steps

- [[2025-02-04\|2025-02-04]] Assemble bots, wire and connect battery, and test the drive method.
- Add methods for turning
- Evaluate servo design, determine whether we need to switch to L298 motor drive board with gear motors.
    - Do we need to use a power transistor to drive the servos? Arduino has pretty small current limit...
- Add methods for sensing line marker
- Add method for steering to follow line
