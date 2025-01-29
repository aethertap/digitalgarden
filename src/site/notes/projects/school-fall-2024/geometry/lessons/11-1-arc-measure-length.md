---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/geometry/lessons/11-1-arc-measure-length/"}
---


#  Arc Measure and Arc Length

## Links and useful resources 

- [[projects/school-fall-2024/geometry/geometry-gr10\|gr10's Geometry >>>START HERE<<<]]
- [AoPS Online Textbook](https://artofproblemsolving.com/ebooks/intro-geometry-ebook/c0toc)
- [AoPS Alcumus](https://artofproblemsolving.com/teacher/students)
- [Big Ideas Geometry textbook](https://bim.easyaccessmaterials.com/?level=12)
- [GeoGebra Online Geometry Constuction Tool](https://www.geogebra.org/geometry?lang=en/)
- [[two-column-templates.pdf|Two-column math templates]]
- [[proofs-unit-presentation.pdf|Proofs unit slides from mathgiraffe.com]]
- [[proofs-unit-printables.pdf|Proofs unit printables for two-column proofs]]


### Lesson-specific resource links


- [Angles: Degrees and Radians intuition](https://betterexplained.com/articles/intuitive-guide-to-angles-degrees-and-radians/) 
-  


## Concept summary and connections


- arc length 
- circumference 
- radian 
- $\text{circumference} = \pi d = 2 \pi r$ 

## Lesson and worked examples

At last, circles! And arcs! Here's where things get interesting.

Circles and arcs are obviously important in our world, so it's good to know how to measure them. For circles, there's really only one thing that matters: the radius. From that, you can figure out the circumference, area, and anything else you might want to know. That's because of the definition of a circle:

*A circle is the locus of all points in the plane that are equidistant from a single point*. Later, we'll see a very similar definition for a sphere in 3D.

Since the definition just mentions the distance from a point, it stands to reason that the distance would fully define the shape of the circle.

What might we want to know about a circle? Two things: it's *circumference* is the distance you'd travel by following it around the edge until you ended back up where you started. It's the same concept as perimeter for a polygon. If you carefully measure many, many circles, you'll find that there's a simple relationship between the circle's radius and its circumference:

$c = 2\pi r$

But what is $\pi$? Well, it's the ratio of the circumference of a circle to its diameter... so, yeah, it's a *circular definition* hahaha. However, the interesting thing is that $\pi$ is the same for ***ALL CIRCLES***, no matter what the radius is! So, once we actually manage to measure it, we can just *remember* it and keep using it forever. 

The **value** of $\pi$ is approximately $3.14159$. It is an **irrational** number though, which means that its decimal expansion never repeats and it can't be written as a fraction, no matter how hard you try.  That being said, if you want a quick-and-dirty approximation to $\pi$ that's a fraction, you can use $\frac{22}{7}$, which is correct through the hundredths place.

### Using $\pi$

Measuring angles: if you take a circle of radius 1, then $\pi$ is the length of a 180 degree arc. $\frac{\pi}{2}$ is a 90$\degree$ arc, and you can find a corresponding fraction of $\pi$ that subtends an arc of any angle you choose. It turns out that it's really convenient to use this kind of measure for angles, because of the fact that $\pi$ is the ratio of two lengths. When you divide a length by a length, you end up with a pure number (**it has NO unit!**). That means that it doesn't have any effect on physics properties, it just acts as a scaling factor.

These fractions of the arc length of a half-circle are called ***radians***. A 180 degree angle is equivalent to $\pi$ radians, and a 360$\degree$ angle is $2\pi$ radians. Any angle can be converted to radians by multiplying by $\frac{\pi}{180}$, and an angle in radians can be converted to degress by multiplying by $\frac{180}{\pi}$. 

### Measuring arc length

If $\pi r$ is the arc length of a half circle of radius r, then you can see how multiplying the angle in radians by the radius could give you the arc length of *any arc*. This is very useful for calculations like determining the distance a robot has moved using the change in its wheel angles.

To measure the length of an arc that subtends angle $\theta$, simply find $r \theta$. 

## Media resources

- [Youtube search for "arc length"](https://www.youtube.com/results?search_query=arc%20length) 
- [Youtube search for "circumference"](https://www.youtube.com/results?search_query=circumference) 
- [Youtube search for "radian"](https://www.youtube.com/results?search_query=radian) 
- [Youtube search for "$c = \pi d = 2 \pi r$"](https://www.youtube.com/results?search_query=$c%20=%20%5Cpi%20d%20=%202%20%5Cpi%20r$) 

## Guided practice


- [ ] What is the radius of a circle with circumference 17?  
- [ ] Your robot has wheels that are 8 cm in diameter. How much should your servo rotate the wheels in order to drive 62 cm forward?
- [ ] The same robot has a wheel separation of 10 cm. If the wheels turn in opposite directions, how far should they rotate in order to turn the robot's body by 90 degrees?

## Homework

- [ ] #hw (geom-gr10) 11.1 Arc Measure, Arc Length, and Circumference  (p. 284) [[2025-01-31\|2025-01-31]]

