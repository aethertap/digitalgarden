---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/physics/lessons/gravitation-and-relativity/"}
---


#  Gravity and Relativity

## Links and useful resources 

- [[projects/school-fall-2024/physics/physics-2024#How Things Work Outline\|START HERE: Physics 2024 class outline]]
- [Physics classroom online interactive tools](https://www.physicsclassroom.com/Lesson-Plans/Algebra-Based-Physics)
- [OpenSTAX high school physics](https://openstax.org/books/physics/pages/1-introduction)
- [NotebookLM physics notebook](https://notebooklm.google.com/notebook/94fe29f5-cebb-4621-9e03-d20110b7a978)
- [Physics projects](https://www.sciencebuddies.org/science-fair-projects/science-projects/physics/high-school)
- [AP Physics 1 Dan Fullerton videos](https://www.youtube.com/playlist?list=PLd2HWlWc-MsysWuL9ksneEM8cl5bk3bHH)



### Lightning Round Questions

- What are models, and why are they used in science? 
- What are the basic steps of scientific inquiry? 
- What is a *bias*? 
- What is PWM and what are some common uses for it? 
- Draw a circuit that uses a *pull-up* resistor to determine whether a switch is closed or open. 

gr7: [lightning:: 1]

## Lesson content with examples

- Universal gravitation and the gravitational constant 
- Relativity, time, and mass 
- Kepler's Laws 

### Universal gravitation

All masses in the universe exert an attractive force on all other masses. The force is proportional to the masses involved, and inversely proportional to the squared distance between them.

$$
f_{gravity} = \frac{{G\cdot m_{1}\cdot m_{2}}}{r^2}
$$


You can think of gravity as a field, or a bunch of lines that shoot out of the center of a mass in all directions. As the lines move through space, they spread farther and farther apart, so fewer of them will pass through an object that's far away than would pass through it if it was close. To understand the $r^2$ term, think of those lines as making dots on a balloon, and as you inflate the balloon, the dot moves outward from the center and gets farther from the other ones. The surface area of the balloon is proportional to $r^2$, which is why the gravitation attraction depends on that term!

The other thing in that formula is this mysterious constant $G$ - the gravitational constant. This is another one of those tuning parameters for our universe; it has to be within a very, **very** narrow bound or nothing in the universe can exist! The value of this constant is currently estimated to be $6.6743\times {10}^{-11}\frac{Nm^2}{kg^2}$.

### Relativity

It turns out that Newton's laws aren't *quite* right when you get going really fast. In fact, they are hopelessly inaccurate when the speed gets high enough. Fortunately, in our normal lives we never encounter situations where that matters, so we can use them without hesitation. However, if you start working with orbits and space travel, relativity becomes very important.

There is a speed limit in the universe: Nothing can ever exceed the speed of light. PERIOD. NOTHING.

We'll do some more digging into this at a later time, but for now, let's finally pull back the curtain and see where the famous $E=mc^2$ equation that everyone uses as a symbl of "being smart"  actually came from.

Albert Einstein did a serious of thought experiments, based on one simple idea: The speed of light is the same for all observers. If you're flying away from the sun at half the speed of light, the light from the sun will still be coming toward you *at the speed of light*... Think about what that might mean, and if you do a good enough job, you'll rediscover relativity.

In physics, we always refer to the speed of light as *c*. 

Ultimately, he landed on a slight adjustment to Newton's laws, which we can write as equations for momentum and energy:

First, momentum: 
$$
p = \frac{mv}{\sqrt{ 1-\frac{v^2}{c^2} }}
$$

It's the same as before, except that the denomimator has a term that involves our velocity and the speed of light. The closer we get to the speed of light, the smaller the value $1 - \frac{v^2}{c^2}$ will become. Since that's in the denominator, that means that our momentum will grow rapidly toward infinity as we get very close to $c$! 

Now, energy:
$$
E_{relativistic} =  \frac{mc^2}{\sqrt{ 1-\frac{v^2}{c^2} }}
$$

We have the same situation with the term in the denominator - the closer our velocity gets to $c$, the more rapidly our energy grows. But, what happens when our velocity is *zero*? We get $E=mc^2$! That's called the *rest energy* of the mass involved, and it means that *mass and energy are interchangeable*! They can be converted into each other, and when it happens the amount of energy is absolutely astonishing.

The only way *I'm* aware of that this happens is during matter/antimatter annihilation, which we have only observed on the scale of a few atoms at a time. The energy released is incredible though - annihilating 100 grams of antimatter would be equivalent in energy to detonating a 4.3 Megaton nuclear weapon!

## Media resources

- [Youtube search for "Universal gravitation and the gravitational constant"](https://www.youtube.com/results?search_query=Universal%20gravitation%20and%20the%20gravitational%20constant) 
- [Youtube search for "Relativity, time, and mass"](https://www.youtube.com/results?search_query=Relativity,%20time,%20and%20mass) 
- [Youtube search for "Kepler's Laws"](https://www.youtube.com/results?search_query=Kepler's%20Laws) 

[Measuring the universal gravitational constant](https://www.youtube.com/watch?v=eA--AOM0D-k&t=30s&pp=ygU0VW5pdmVyc2FsIGdyYXZpdGF0aW9uIGFuZCB0aGUgZ3Jhdml0YXRpb25hbCBjb25zdGFudA%3D%3D)
[Another gravitational constant experiment](https://www.youtube.com/watch?v=5YDXqdg0bBw&pp=ygU0VW5pdmVyc2FsIGdyYXZpdGF0aW9uIGFuZCB0aGUgZ3Jhdml0YXRpb25hbCBjb25zdGFudA%3D%3D)
[Orbital ellipses](https://www.youtube.com/watch?v=6qVfOLLQG4U&t=185s)
[Cavendish experiment (britannica)](https://www.britannica.com/science/Cavendish-experiment)

- [ ] #quiz What are *perihelion* and *aphelion* in orbital mechanics?
- [ ] #quiz What shape do Kepler's laws specify for planetary orbits?
- [ ] #quiz What is the Gravitational Constant? 
- [ ] #quiz What is the formula for the gravitational force of attraction between any two masses?

## Guided practice


- [ ] How high above the surface of Earth would you need to be in order for your weight to be half what it is at the surface?  
- [ ] How high above the surface of Earth do you need to be if you want to have a stable orbit that stays above the same spot on the surface all the time (geostationary orbit)?  
- [ ] If a 1-kg weight is zipping through space at $\frac{1}{2} c$, how much energy would it take to reach $\frac{3}{4}c$?   
