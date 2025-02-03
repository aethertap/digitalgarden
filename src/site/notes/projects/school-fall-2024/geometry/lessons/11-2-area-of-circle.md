---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/geometry/lessons/11-2-area-of-circle/"}
---


#  Area of Circles

## Links and useful resources 

- [[projects/school-fall-2024/geometry/geometry-gr10\|gr10's Geometry >>>START HERE<<<]]
- [AoPS Online Textbook](https://artofproblemsolving.com/ebooks/intro-geometry-ebook/c0toc)
- [AoPS Alcumus](https://artofproblemsolving.com/teacher/students)
- [Big Ideas Geometry textbook](https://bim.easyaccessmaterials.com/?level=12)
- [GeoGebra Online Geometry Constuction Tool](https://www.geogebra.org/geometry?lang=en/)
- [[two-column-templates.pdf|Two-column math templates]]
- [[proofs-unit-presentation.pdf|Proofs unit slides from mathgiraffe.com]]
- [[proofs-unit-printables.pdf|Proofs unit printables for two-column proofs]]

You know why the bumpkin can't do geometry? It's because *everybody knows* $\pi$ are *round*, not $\pi r^2$

## Concept summary and connections


- calculating the area of a circle 
- calculating the area of a sector of a circle 

## Lesson and worked examples

- Area of a circle: $\pi r^2$

Remember the area of a polygon: $\frac{1}{2} ap$, where $a=\text{apothem}$ and $p=\text{perimeter}$. Think about a circle... What if the circle was really a polygon with thousands of sides? What would it's apothem be? It would be the radius of the circle! What is its perimeter? It's $2\pi r$... so if we just use the formula for the area of a polygon, but fudge things around a bit in a way that seems kinda legit, we do this:

$$
\begin{align}
\frac{1}{2}ap &= \frac{1}{2}r(2\pi r) \\
&=\pi r^2
\end{align}
$$
That is definitely not a proof, BUT it is nice for the intuition!

### Area of circular sectors

A sector is a pie-slice of a circle. Let's start from the area of a circle: 

$\text{area}=\pi r^2$ 

A circle is just a circular section with an included angle of $2\pi$... Keep that in mind for the next part.

What would the area of a half-circle be? Well, hopefully it would be half of the area, which woud be $\frac{1}{2}\pi r^2$. And, what would the angle be? Well, it would be $\pi$. Likewise, the area of a 90-degree sector should be $\frac{1}{4}$ of the area of the whole circle, or $\frac{1}{4}\pi r^2$, with an included angle of $\frac{\pi}{2}$.

What can we deduce here? Let's write each of those things out, changing the $\pi$ part out for the included angle:

$$
\begin{align}
\text{area of a circle}(\theta=2\pi ) &= \pi r^2 &= \frac{1}{2}\theta r^2 \\
\text{area of semicircle}(\theta=\pi) &= \frac{1}{2}\pi r^2 &= \frac{1}{2}\theta r^2 \\
\text{area of a quarter circle} \left( \theta=\frac{\pi}{2} \right) &= \frac{1}{4} \pi r^2 &= \frac{1}{2}\theta r^2
\end{align}
$$
I detect a pattern here... for any included angle of a circular sector, the area is just half the angle in radians times the square of the radius!

### Area enclosed by a chord

A chord connects two points on the edge of a circle. What is the area between the chord and the circle? 

The easiest way to solve this is to find the area of the sector, then subtract the area of the triangle formed by the same points. The triangle will always be isosceles, and you'll be able to find the angle using either the arc length cut by the chord, the length of the chord itself, or the formula for area and circumference of the circular sector.

### Using area to solve problems

Just like we do with triangles and polygons, we can use the *area* of the circular sector to assert things about its radius and its circumference. Whenever we have a problem that has related areas, we can immediately say things about the radius of each part! Likewise, we can do the same thing given *any* of the three properties.

Be on the lookout for ways to change problems involving radius, circumference, or area of circles or sectors into problems involving the other pieces. Sometimes this will give you a big simplification!

## Media resources

- [Youtube search for "calculating the area of a circle"](https://www.youtube.com/results?search_query=calculating%20the%20area%20of%20a%20circle) 
- [Youtube search for "calculating the area of a sector of a circle"](https://www.youtube.com/results?search_query=calculating%20the%20area%20of%20a%20sector%20of%20a%20circle) 

## Guided practice


- [ ] If you had a rope wrapped tightly all the way around the Earth, how much more rope would you need to add in order to have a one-inch gap between them all the way around?  
- [ ] If paper weighs 90 grams per square meter, how much would a ring weigh that was made by cutting a 12 cm circle out of the center of a 40 cm disc?  


## Homework


- [x] #hw (geom-gr10) 11.2 Area  (p. 290) (gr10) [[2025-02-03\|2025-02-03]]


