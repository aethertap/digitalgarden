---
{"dg-publish":true,"permalink":"/projects/school-25-26/engineering/lessons/engr-01-what-is-cnc/","title":"What is CNC?"}
---


# What is CNC?

- Computer Numeric Control
- A machine that has some number of actuators that move things around or operate tools
- Each actuator is called an "axis", and the machine's complexity can be summarized by the number of axes it has (3-axis mill, 5-axis mill, 6-axis arm)
- The tools can be a huge assortment of things:
    - Pens
    - laser
    - plasma torch
    - rotating cutter
    - plastic extruder
    - air pump
    - Anything that is turned on or adjusted while the machine operates
- The basic idea is this: Instead of positioning an controlling a tool manually, build a machine that can do it precisely then write a program to actually make the movements and operations happen


## Programming CNC machinery

- Most CNC machines are programmed using a low-level language called g-code. [[projects/school-25-26/engineering/intro-to-cnc\|intro-to-cnc]]
- Homing
    - When the machine is powered on, it generally doesn't know what the state of its various axes are.
    - Homing involves moving each axis until a known position is found and then setting that as "home"
    - All motions the machine does are now relative to that home position
    - Sometimes this is a fixed location, sometimes you set this as the user. Depending on the g-code you're running, there may be a location on the part that you're using has home because it's easy to find with precision. 
        - Using part-based home is especially useful for multi-setup operations, where you have to stop the machine and reposition the part. With an absolute home, it would be much harder to get the part mounted in exactly the right place. Part-based homing lets you move the tool head to the right spot and say "start from here."
- This is a lot like assembly language for a CPU - it tells the machine to do an extremely limited operation with well-known, exact requirements
    - Most of the operations are single-axis motions
    - operations can include more complex pre-programmed sequences, like homing

