---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/physics/lessons/buoyancy-and-archimedes/"}
---


#  Buoyancy and Archimedes' Principle

## Links and useful resources 

- [[projects/school-fall-2024/physics/physics-2024#How Things Work Outline\|START HERE: Physics 2024 class outline]]
- [Physics classroom online interactive tools](https://www.physicsclassroom.com/Lesson-Plans/Algebra-Based-Physics)
- [OpenSTAX high school physics](https://openstax.org/books/physics/pages/1-introduction)
- [NotebookLM physics notebook](https://notebooklm.google.com/notebook/94fe29f5-cebb-4621-9e03-d20110b7a978)
- [Physics projects](https://www.sciencebuddies.org/science-fair-projects/science-projects/physics/high-school)
- [AP Physics 1 Dan Fullerton videos](https://www.youtube.com/playlist?list=PLd2HWlWc-MsysWuL9ksneEM8cl5bk3bHH)



### Lightning Round Questions

- What shape do Kepler's laws specify for planetary orbits? 
- What is the formula for calculating work? 
- Why is the idea of a *spring constant* important for weighing things? 
- How do you make a new instance of a class in typescript? 
- Draw a circuit that uses a *pull-up* resistor to determine whether a switch is closed or open. 
- What is the ideal gas law? 



## Concept summary and connections


- Archimedes' Principle 
- Water pressure and depth 
- Pascal's principle: a change in pressure of an enclosed incompressible fluid is conveyed undiminished to every part of the fluid and to the surfaces of its container. 
- Pressure potential energy 
- steady-state flow 
- streamlines 
- Bernoulli's equation 


Archimedes' principle: An object that displaces a fluid will experience a *buoyant force* equal to the **weight** of the displaced fluid.
- Weight implies that this is in a gravitational field (or other directional acceleration)
- buoyant force means a force that pushes the object upward against the acceleration of gravity
- The force *always* exists, though it may not be enough to cause the object to actually *float*!

### Pascal's Principle

When an incompressible fluid is pressurized inside a vessel, that pressure is immediately transferred through the fluid and to all of the containing surfaces of the vessel. There is no directionality or variation to it. You could also say that an externally applied pressure is exerted everywhere throughout the liquid. Note that this is different from the *pressure gradient* caused by gravity!

### Pressure gradients

When you have a fluid with some depth, the stuff on the bottom has to hold the weight of everything above it. In fact, at every level, the fluid *at that level* is holding up the weight of all of the fluid *above that level*. Since fluids exert force through pressure, that means that the pressure in a fluid *increases gradually with depth*.

The **shape** of the container makes **absolutely no difference** to this! Wide parts, narrow parts, tubes that follow winding paths, none of that matters, because of Pascal's principle. The pressure at a given level of depth is the same no matter what , as long as the fluid is connected.

### Pressure, work, and energy

We talked about force as it relates to work and energy, and pressure has some similar traits:

$$
\text{work} = \text{pressure} \times \text{volume}
$$
In this equation, you're doing work equal to the *volume of fluid you've moved* times the pressure you're working against. Likewise, a moving volume of fluid at a given pressure can **do work**.

This is how hydroelectric dams work: They create a pressure gradient by making a deep pool of water, then they extract *work* from that pressure at the bottom of the pool by allowing it to jet out through a turbine. The *pressure potential energy* does work, and is converted in to *electrical energy* by the turbine.

### Flow

When fluid moves, it's called *flow*. When the flow is continuous and steady, and moves through a stationary environment, it's called **steady-state flow**. When you watch steady-state flow, you can't detect the passage of time - it looks exactly the same as if the fluid was still. Remember: a fluid is a uniform substance, so we aren't talking about bubbles and twigs in a stream, and if the flow is steady-state, there are no eddies or turbulent spots to reveal what's happening!

If you were to somehow mark a particle of fluid and trace its path as it flows, you would be making a **streamline** (the path taken by a tiny portio nof fluid in the flow).

In steady state flow, **a drop's ordered energy remains constant as it travels along its streamline**. Since all drops in a fluid are identical, the ordered energy per drop along a streamline is *constant*.

**Ordered energy** can take three forms for a drop of fluid: Kinetic energy, pressure potential energy, and gravitational potential energy. We'll ignore gravitational for now, and just look at pipes that are all at the same level. The total ordered energy is thus:

$$
\begin{align}

\text{ordered energy} &= \text{pressure potential energy} + \text{kinetic energy} \\
&= \text{pressure}\cdot\text{volume} + \frac{1}{2} \text{density}\cdot\text{volume}\cdot\text{speed}^2
\end{align}
$$

Dividing both sides by volume gives **Bernoulli's Equation**:

$$
\frac{\text{ordered energy}}{\text{volume}} = \text{pressure} + \frac{1}{2} \text{density}\cdot\text{speed}^2
$$
This value is ***constant along a streamline***, and it **assumes there are no friction-like effects** that would remove energy from the system.


## Media resources

- [Youtube search for "Archimedes' Principle"](https://www.youtube.com/results?search_query=Archimedes'%20Principle) 
- [Youtube search for "Water pressure and depth"](https://www.youtube.com/results?search_query=Water%20pressure%20and%20depth) 
- [Youtube search for "Pressure potential energy"](https://www.youtube.com/results?search_query=Pressure%20potential%20energy) 
- [Youtube search for "steady-state flow"](https://www.youtube.com/results?search_query=steady-state%20flow) 
- [Youtube search for "streamlines"](https://www.youtube.com/results?search_query=streamlines) 
- [Youtube search for "Bernoulli's equation"](https://www.youtube.com/results?search_query=Bernoulli's%20equation) 

## Guided practice


## Homework



- [ ] #hw (physics) Why do bottles for carbonated drinks always have small caps? [[2025-03-07\|2025-03-07]]
