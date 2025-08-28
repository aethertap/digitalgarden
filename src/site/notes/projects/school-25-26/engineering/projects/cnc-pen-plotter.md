---
{"dg-publish":true,"permalink":"/projects/school-25-26/engineering/projects/cnc-pen-plotter/"}
---


# Basic CNC pen plotter

The goal of this project is to end up with a plotter than can draw accurate, repeatable images using a single marker, based on a vector file. This is a warm-up for building the [[projects/school-25-26/engineering/projects/root-4-cnc-router\|root-4-cnc-router]] project.

## Design

This should be a 2-axis rectangular machine with a cross-slide gantry that uses NEMA-17 stepper motors for the main axes. The pen should be able to lift and lower automatically, which can easily be accomplished with a servo or another small stepper.

We will use:
- Arduino Uno
- GRBL
- UGS (universal G-code Sender)
- Toothed-belt drive
- Extruded aluminum track with v-wheels for motion

Your design must
- [ ] securely mount the arduino and all other electronic components
- [ ] reliably move over at least a 12x12 inch area
- [ ] reliably raise and lower the pen
- [ ] Move correctly according to the signals from the GRBL controller.

Your design CAN:
- allow for a detachable tool mount on the cross slide (for future use as a laser or lightweight router)
- be significantly larger
- have whatever other features you think would be cool

