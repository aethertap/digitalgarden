---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/physics/lessons/water-distribution/"}
---


#  Water Distribution

## Links and useful resources 

- [[projects/school-fall-2024/physics/physics-2024#How Things Work Outline\|START HERE: Physics 2024 class outline]]
- [Physics classroom online interactive tools](https://www.physicsclassroom.com/Lesson-Plans/Algebra-Based-Physics)
- [OpenSTAX high school physics](https://openstax.org/books/physics/pages/1-introduction)
- [NotebookLM physics notebook](https://notebooklm.google.com/notebook/94fe29f5-cebb-4621-9e03-d20110b7a978)
- [Physics projects](https://www.sciencebuddies.org/science-fair-projects/science-projects/physics/high-school)
- [AP Physics 1 Dan Fullerton videos](https://www.youtube.com/playlist?list=PLd2HWlWc-MsysWuL9ksneEM8cl5bk3bHH)



### Lightning Round Questions

- What is the formula for the momentum of a moving mass? 
- What was the issue at stake in the opium wars between China and Britain? 
- What is the formula for the sum of *exterior angles* for any convex polygon? 
- How much gravitational potential energy does a 10 kg mass have if it is 20 meters above the ground? 
- What is the buoyant force on a 10cm x 10cm x 10cm block of aluminum when it is under water? 
- What is the SI unit meaning of "a Pascal"? 

gr7: [lightning:: ]
gr10: [lightning:: ]

## Demonstration


## Liquid pressure and distribution

- plumbing and water pressure 
- pressure vs depth in a fluid 
- streamlines 
- Bernoulli's principle 
- pumps 
- All liquids are *incompressible* 

Liquids under pressure obey energy laws just like other matter. We can compute the kinetic energy, work, momentum, and other properties of liquid in the same way (using mass and velocity, etc), or we can take advantage of the way liquid's mass and volume are interchangeable to get a different, more useful formula.

In a liquid, the *pressure* that the liquid is under is a new form of potential energy that we haven't worked with yet. Pressure is what causes liquids to move through pipes and other spaces, so it clearly can do *work* on the fluid. The *amount of work* it can do could be calculated by the force and mass, but if you work through it, you find that all you need is the *pressure and volume* (the mass and force term are wrapped up in those because the pressure is over *area* and the mass *depends on the volume*).

In a liquid, the amount of work done in moving it is equal to $\text{pressure}\cdot\text{volume}$. Using the idea of work and energy being convertible back and forth, we can define the idea of **pressure potential energy** as being the same as the work done in moving liquid. However, *this concept is only valid for steadily moving liquid!* You can't pump up a container of liquid to a high pressure and expect to get work from it, because **liquids are incompressible and cannot store energy as pressure** (with a gas, this scheme would actually work).

### Bernoulli's principle

A fluid moving in *steady state flow* has three kinds of **ordered energy**: kinetic, pressure potential, and gravitational potential. Bernoulli's principle tells us that these three things ***add up to a constant for every streamline in steady-state flow***:

$$
\begin{align}

\frac{\text{ordered energy}}{\text{volume}} &= \frac{1}{2}\text{density}\cdot\text{velocity}^2 + \text{pressure} + \text{density}\cdot\text{accel}_{\text{grav}}\cdot\text{height} \\
\text{constant} &=\frac{1}{2}\text{density}\cdot\text{velocity}^2 + \text{pressure} + \text{density}\cdot\text{accel}_{\text{grav}}\cdot\text{height} 
\end{align}
$$

Using that, we can figure out how fast the liquid is moving through any part of a system, and how much pressure it's under. Since the water in a streamline has to have constant ordered energy, *increasing the velocity drops the pressure!* 

### Converting between energy forms in a liquid

Pumping water through a system of pipes of various diameters has some interesting consequences:
- The **same volume of water** has to flow through **every part of the system** in a given time.
- That means the velocity of the water depends on the diameter of the pipe: Skinny pipes mean fast,low-pressure water.

### But, how high?

So you have pressurized water in a pipe, and you spray it out of a good nozzle that converts its pressure potential energy into the maximum amount of kinetic energy. How high will it go?

Assuming that our pump is at the same height as our nozzle, so we're not losing or gaining anything from gravity, then the full pressure potential turns into kinetic energy. We know that the kinetic energy is equal to $\frac{1}{2}\text{density}\cdot\text{velocity}^2$, so we need to know the density of our liquid. Once we have that, we can solve for the velocity (remember that the pressure potential energy is known because we know all about our pump):

$$
\begin{align}
E_{pressure} &= \frac{1}{2}\rho v^2 \\
\frac{2E_{\text{pressure}}}{\rho } &= v^2 \\
\sqrt{ \frac{2E_{\text{pressure}}}{\rho } } &= v
\end{align}
$$

But, how big should the nozzle be? Well, we know what our target velocity is, and we know what pressure we need. Now we need to know **how much water the pump can supply at that pressure**, in other words, **how much work can the pump do over a given time?** (remember: $\text{work}=\text{pressure}\cdot\text{volume}$). Pumps usually have a *power* rating: work per time, or $\text{pressure}\cdot \frac{\text{volume}}{\text{time}}$

As long as we make sure our nozzle is small enough that the amount of liquid passing through it per second at the max speed is less than the max power of the pump, we'll get full height from our spray.


### How about a gravity sprayer?

Let's say you have a big lake of water way up high, and a pipe running down to some place where you want a fountain. How big can your nozzle be to get full spray height, like with the pump? Well, gravity-fed pressure is special: you don't need a nozzle! The acceleration due to gravity can move *any amount of water at full pressure*, so all you need to do is point the pipe upward and you've got the max height possible!


## Media resources

- [Youtube search for "plumbing and water pressure"](https://www.youtube.com/results?search_query=plumbing%20and%20water%20pressure) 
- [Youtube search for "pressure vs depth in a fluid"](https://www.youtube.com/results?search_query=pressure%20vs%20depth%20in%20a%20fluid) 
- [Youtube search for "streamlines"](https://www.youtube.com/results?search_query=streamlines) 
- [Youtube search for "Bernoulli's principle"](https://www.youtube.com/results?search_query=Bernoulli's%20principle) 
- [Youtube search for "pumps"](https://www.youtube.com/results?search_query=pumps) 
- [Youtube search for "All liquids are *incompressible*"](https://www.youtube.com/results?search_query=All%20liquids%20are%20*incompressible*) 

## Guided practice


- [ ] What is the pressure, in PSI and Pa, at the bottom of the deepest part of the ocean?  
- [ ] If you put a pipe into the ocean so that it went from the bottom all the way to the surface, would the high-pressure water down below cause water to shoot out of the top of the pipe? Why or why not?
- [ ] What would happen if everyone in a city had all of their faucets open, then closed them at the same instant?  
- [ ] How does the water pressure in our pipes stay consistent without having to run the pump continuously?  
- [ ] How high could water be sprayed if you had the right nozzle, and 1,000,000 Pa of water pressure?

## Homework

- [ ] #hw (physics) Do problems 5.7-5.11 [[2025-03-10\|2025-03-10]]
- [ ] #hw (physics) Read and take notes on section 5.2 of *How Things Work* [[2025-03-10\|2025-03-10]]
