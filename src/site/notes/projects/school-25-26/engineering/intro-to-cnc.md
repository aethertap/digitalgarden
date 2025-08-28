---
{"dg-publish":true,"permalink":"/projects/school-25-26/engineering/intro-to-cnc/"}
---


# Introduction to CNC 

Intro project: **[[projects/school-25-26/engineering/projects/cnc-pen-plotter\|CNC Pen Plotter]]** 

Computer Numerical Control - Machines that follow precise instructions to make parts.

## G-code

G-code is a set of very simple, specific instruction codes that tell the controller exactly when, how fast, and how far to move its various axes. GRBL is an open-source software package that interprets G-code and translates it into stepper signals.

[grbl](https://github.com/grbl/grbl?tab=readme-ov-file) - high performance g-code motion controller that can run on an arduino
[grblHAL](https://github.com/orgs/grblHAL/repositories) - GRBL g-code handling for more powerful 32-bit processors.

[Introduction to G-code](https://howtomechatronics.com/tutorials/g-code-explained-list-of-most-important-g-code-commands/)
[Using GRBL for a simple CNC machine](https://howtomechatronics.com/tutorials/how-to-setup-grbl-control-cnc-machine-with-arduino/)
- [ ] [OnStepX Telescope control software](https://github.com/hjd1964/OnStepX) - making a motorized telescope mount could be really cool #remind/monthly

## Lessons - 37 full weeks
Create `js= ((cjs)=> cjs.School.dynamic_class("micro","projects/school-25-26/engineering/projects","Microscope Camera Build"))(customJS)` 
1.  [[projects/school-25-26/engineering/projects/micro-01-microscope-camera-build\|micro-01-microscope-camera-build]]- project page [[projects/school-25-26/engineering/projects/microscope-camera\|microscope-camera]]
2.  [[projects/school-25-26/engineering/projects/micro-02-microscope-camera-build\|micro-02-microscope-camera-build]]- project page [[projects/school-25-26/engineering/projects/microscope-camera\|microscope-camera]]
3. [Design for 3D printing](https://blog.rahix.de/design-for-3d-printing/) [[projects/school-25-26/engineering/lessons/engr-02-design-for-3d-printing\|engr-02-design-for-3d-printing]]
4. [[engr-02-parts-library\|engr-02-parts-library]] - taking inventory and planning what we'll need for our CAD model
5. [[engr-03-analyze-designs\|engr-03-analyze-designs]] - Look at the laser engraver and the root-4 and PrintNC designs
6. `js= customJS.School.dynamic_class("router","projects/school-25-26/engineering/projects","CNC Router Build")` Building our CNC router
 
### Homework

1. [ ] #hw Write a g-code program that creates a capsule outline. The center-to-center distance must be 3.00 inches, and the radius of the ends must be 1.00 inch. 
2. [ ] #hw Connect a GRBL controller to a stepper driver and two steppers, and use it to make the motors do a series of basic operations (rotate different directions and speeds, as if moving X and Y axis)
3. [ ] #hw Design a barebones 2-axis frame with a moving cross-slide and two steppers that can be 3d printed on our ender3. This will become the [[projects/school-25-26/engineering/projects/cnc-pen-plotter\|cnc-pen-plotter]].
4. [ ] #hw Assemble the [[projects/school-25-26/engineering/projects/cnc-pen-plotter\|cnc-pen-plotter]] you designed
5. [ ] #hw Use the pen plotter to draw a cool picture

