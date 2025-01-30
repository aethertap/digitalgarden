---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/physics/lessons/motion-in-2d/"}
---


#  Motion in Two Dimensions

## Links and useful resources 

- [[projects/school-fall-2024/physics/physics-2024#How Things Work Outline\|START HERE: Physics 2024 class outline]]
- [Physics classroom online interactive tools](https://www.physicsclassroom.com/Lesson-Plans/Algebra-Based-Physics)
- [OpenSTAX high school physics](https://openstax.org/books/physics/pages/1-introduction)
- [NotebookLM physics notebook](https://notebooklm.google.com/notebook/94fe29f5-cebb-4621-9e03-d20110b7a978)
- [Physics projects](https://www.sciencebuddies.org/science-fair-projects/science-projects/physics/high-school)
- [AP Physics 1 Dan Fullerton videos](https://www.youtube.com/playlist?list=PLd2HWlWc-MsysWuL9ksneEM8cl5bk3bHH)

### Lightning Round Questions

- Draw a circuit that uses a *pull-up* resistor to determine whether a switch is closed or open. 
- A circuit has +5v input, then a 1k$\Omega$ resistor, then a $9k \Omega$ resistor, then ground. What is the voltage between the resistors? 
- What is a *control* in an experiment? Why is it important? 
- Which phase of matter can easily have its *volume* changed? 
- Which phases of matter can easily change *shape*? 

- gr7: [lightning:: ]
- gr10: [lightning:: ]

## News..... FROM SPACE

- [asteroid with 1:83 chance of hitting earth in 2032](https://www.space.com/180-foot-asteroid-1-in-83-chance-hitting-Earth-2032)
- [Asteroid Bennu has 14 of 20 amino acids crucial for life formation](https://www.space.com/the-universe/asteroids/nasa-finds-key-molecules-for-life-in-osiris-rex-asteroid-samples-heres-what-that-means)

## Review

- Motion diagrams: Draw a motion diagram for an arrow shot horizontally from a bow, from the instant it leaves the bow to the instant it touches the ground.
    - Remember to draw the dot spacing increasing as acceleration from gravity increases the vertical component!
    - Remember to draw the velocity vectors *between the dots*
    - Remember to draw the acceleration vectors *at the dots*
- Sine and Cosine, rise and run. Review how to find horizontal and vertical components of vectors using angles and trig functions.

## Concept summary and connections


- position vector 
- instantaneous velocity 
- kinematic equations 
- average acceleration 
- average velocity 

Bodies in motion remain in motion, and bodies at rest stay in bed unless their mothers call them to get up.

A neutron walked into a bar and asked, "How much for a gin and tonic?" The bartender smiled wryly and replied, "For you, no charge."

## Lesson content with examples

We've used vectors to show the velocity of an object by drawing a [[projects/school-fall-2024/physics/motion-diagram\|motion-diagram]]. The velocity is just the *change in position per unit time* though, so what would the position look like if it was drawn as a vector? The answer is that it's just the vector that starts at the origin and goes to the object. If you have two position vectors like that, and you subtract one from the other, you'll get a velocity vector!

So now we can see *why* the velocity vectors work the way they do in a motion diagram: They're just the result of subtracting an old position vector from the one that follows it.

We also know that we can get *acceleration* vectors by subtracting the previous velocity from the current velocity.

### Kinematic Equations

From our experience diagramming, we learned a few things:
- Velocity is just the change in position over time
- Acceleration is just the change in velocity over time.

Those statements look very similar, don't they? in fact, we can keep going with even more properties of motion (*jerk* is the next one, and it describes how the acceleration changes...)

Those things can be turned into equations with a bit of thought. We're going to need a way to represent the idea of *the change in* something in these equations, so here comes some notation: $\Delta$, the Greek letter Delta, is generally used in physics to mean "the change in." So we'd write $\Delta x$ to mean "the change in x" over whatever time we're working on. 

If we measure position at two times ($t_{1}$ and $t_{2}$), we could call them $\vec{x_{1}}$ and $\vec{x_{2}}$. If we are going to compute the average velocity using those measurements, we'd do it like this: $\frac{\vec{x_{2}}-\vec{x_{1}}}{t_{2}-t_{1}}$. Notice that we subtracted the ***old*** value from the ***new*** value! That's important, and I guarantee you'll get it backwards a few times because we're so used to doing things in ascending order. If you do it backwards, your velocity will be backwards! Watch out! We physicists are lazy creatures though, and we don't like to write more than necessary. So we're going to write $\frac{\vec{x_{2}}-\vec{x_{1}}}{t_{2}-t_{1}}$ as $\frac{\Delta x}{\Delta t}$. Whenever you see that, it always means we're computing the *change in* something.

Now we have a convenient way to write an equation for velocity: $\vec{v} = \frac{\Delta \vec{x}}{\Delta t}$ 

We can do something similar for acceleration, which is just the change in velocity: $\vec{a} = \frac{\Delta \vec{v}}{\Delta t}$ 

### Velocity and position

If you know the velocity and a starting position, you can figure out where the object will be after a time. Remember the *rate equation:* $d=rt$, which says that distance travelled is equal to the speed (rate) of motion multiplied by the amount time it was moving. That's our first kinematic equation, as long as we remember we're dealing with vectors here and we need to keep track of where we started. We'll use $\vec{x}$ to represent our position vector, which means $\vec{x_{0}}$ is our starting position: 

$\vec{x} = \Delta t \vec{v} + \vec{x_{0}}$

In other words, multiply our velocity by the amount of time passed, then add it to where we started, and we'll get our new position.

### Velocity and acceleration

Acceleration is to velocity what velocity is to position - if you apply acceleration for a while, you get a change in your velocity. So we can use the rate equation *again*, since what we have is the *rate of change* of velocity. We'll use $\vec{v}$ for our current velocity, and $\vec{v_{0}}$ for our starting velocity (before the acceleration that we're dealing with  happened:

$\vec{v} = \Delta t \vec{a} + \vec{v_{0}}$

In other words, multiply the acceleration by the amount of time it was applied, then add that velocity *change* to the velocity we *started with*, and you'll get our new velocity.

### Position and acceleration

Here's the hard one. If you have *just* the acceleration, you can use it to see how far you've travelled. The trick here is to realize that we're adding up all of the little changes to velocity that happened over some period of time ($\Delta t$), but then we *still have to multiply it by the time* because our position change is a velocity times time! When we get to calculus this will be easier to understand, but for now remember that you multiply acceleration by time to get velocity, and then you mutiply velocity by time to get position, so you can squint your eyes and see how you'd use *time squared* to go straight from acceleration to position. 

Our first crack at this would look like this then: $\vec{x} = \frac{1}{2}\vec{a}\Delta t^2 + \vec{x_{0}}$. Wait, you say, why the half? Remember that we were calculating the *average* velocity above, and over this time interval, we'd add up the starting and final velocities then divide by two to get the average. That's not the real reason, but it's related so keep that intuitive idea.

Now, that equation is fine as long as we aren't already moving when the whole business gets started. But what if we are already coasting along before the acceleration hits? Can we still figure out where we'll end up? Yes! The thing to remember is that these vector quantities can all be added together, so if we had some velocity before we started, we can just multiply it by the *same $\Delta t$* and add it to the equation:

$\vec{x} = \frac{1}{2}\vec{a}\Delta t^2 + \vec{v_{0}}\Delta t + \vec{x_{0}}$

And there you have it, the path from acceleration to position.
## Media resources

- [Youtube search for "position vector"](https://www.youtube.com/results?search_query=position%20vector) 
- [Youtube search for "instantaneous velocity"](https://www.youtube.com/results?search_query=instantaneous%20velocity) 
- [Youtube search for "kinematic equations"](https://www.youtube.com/results?search_query=kinematic%20equations) 
- [Youtube search for "average acceleration"](https://www.youtube.com/results?search_query=average%20acceleration) 
- [Youtube search for "average velocity"](https://www.youtube.com/results?search_query=average%20velocity) 

## Guided practice

- [ ] Do several "find the acceleration vector" problems with motion diagram dots in groups of three (two velocity vectors)
- [ ] Draw some position graphs: When is the particle moving "forward"? When is it moving "backward"? When is it at rest?
- [ ] Draw some *velocity* graphs: When is the particle moving forward, backward, and at rest?
- [ ] Draw some *acceleration* graphs: When is it moving forward, backward, and at rest? (**can you tell???**)
- [ ] What is $\Delta \vec{x}$ if $\vec{x_{1}}=2\hat{\imath}+3\hat{\jmath}$ and $\vec{x_{2}}=-\hat{\imath}-\hat{\jmath}$.
- [ ] If those were positions measured a times $t_{1}=2$ and $t_{2}=4$, what was the average velocity during that period?
- [ ] Say the next measurement was a time $t_{3}=6$ and the position was $\vec{x_{2}}=-2\hat{\imath}-2\hat{\jmath}$. What was the average velocity from $t_{2}$ to $t_{3}$?
- [ ] What was the average acceleration from $t_{2}$ to $t_{3}$?
- [ ] Spaceship drifting north through the galaxy at 680 m/s. Pilot rotates to 25$\degree$ north of east, then accelerates at 75$m/s^2$. Plot the trajectory for the first 20 seconds.  (Physics for Scientists and Engineers, p. 85 example 4.3)
- [ ] For that example, what is the x-component of the acceleration? What is the y-component?  
- [ ] Is the spaceship's speed in the "north" direction increasing or decreasing because of the acceleration?

- [ ] #hw (physics) [Do the "Apprentice level" exercise at this link](https://www.physicsclassroom.com/Concept-Builders/Kinematics/Which-One-Doesnt-Belong/Concept-Builder) [[2025-02-03\|2025-02-03]]

## Homework

- [ ] #hw (physics)  [Do the problems on our school page under the Homework heading](https://school.ginosterous.com/projects/school-fall-2024/physics/lessons/motion-in-2d) [[2025-01-31\|2025-01-31]] 

1. For this qustion, read all parts before you start. Draw a [[projects/school-fall-2024/physics/pictorial-representation\|pictorial-representation]], with *all* variables present on the diagram, and write the equations you will use to answer the questions
    1. A rocket sled ignites and moves to the right with an acceleration of 30 $\frac{m}{s^2}$ for 5 seconds (where the engine stops). How fast is it moving when the engine stops?
    2. How far did the sled go before the engine turned off?
    3. If the sled now starts coasting with friction so that it decelerates at 5 $\frac{m}{s^2}$ until it stops, how long will it take to stop? How much farther did it go before it stopped?
    4. How far did the sled travel from start to finish?
2. ![phys-4.1.jpg](/img/user/projects/school-fall-2024/physics/lessons/_resources/phys-4.1.jpg)
3. ![phys-4.5.jpg](/img/user/projects/school-fall-2024/physics/lessons/_resources/phys-4.5.jpg)

