---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/printing-remaining-parts/"}
---


#  Printing the rest of the parts

## Links and useful resources 

- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)

 
- ***[[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|Project index: differential-steering-bot]]*** 

## Lesson

- Importance of full assembly drawings 
- Getting a feel for dimensions - how thick *is* 0.06 inches, really? 
- Limitations of the 3D printer 

We had some issues again with the models, although we've made a LOT of progress! So, what kind of things are still giving us trouble? Just a couple:
- We *really* have to make a ***full, complete assembly*** in CAD before we build.
- The 3D printer has some limitations that are easy to get into conflict with by accident when we trust the plausible-looking CAD drawings of difficult parts.

### The importance of full-assembly drawings

Making multi-part assemblies is not an easy job. There are dozens of things that can surprise you by running into each other, being impossible to assemble in real life, or being impossibly thin or oddly-shaped parts. One of the best ways to see these things before you build for real is to **build it virtually**. Our CAD system makes this really easy - you just import all of your parts, and pretend you're sitting there with them in your hands while you assemble it on the screen.

It's still easy to make something that can't be assembled in real life, but if you're careful about what you allow yourself to do, you can catch most of the problems. The good ol' school of hard knocks will teach you the rest as you have to redesign failed parts.

After you have the assembly made, you have to actually *move* all of the moving parts through their ranges of motion to make sure you don't have any unwanted collisions. For example, a caster wheel will fit just fine right next to another part, unless you actually have to *turn* the caster. At that point, you realize that it sticks out past the center line by a large amount, and your bot won't be able to steer because the caster gets stuck!

This is also the best way to make sure of things like overall level of the bot. The rear wheels and the caster are separated by several parts, so it's not trivial to see whether the bot will actually be level when sitting on the ground fully assembled. However, if you actually make the assembly drawing, you can just look and see. If it isn't it's also easy to measure exactly how much to change things in order to get it perfect.

Moral: *always make a full assembly drawing*, and use it to check the fit of everything!

### Limitations of the 3D printer

3D printers are pretty amazing tech, but they aren't infallible. The have trouble with some common scenarios:

- Overhangs
- Tall, skinny parts 
- Thin walls

We had several print failures on a caster mount due to a combination of a small overhang and a very thin sidewall. In theory, the printer should be able to do this, but in reality it just can't. So, when that happens, we have to let reality win and adapt our plans. Reality always wins. Every time. So just accept it and redesign!

Make notes to yourself about what kinds of things don't work so that you can catch them in the design phase next time, and you'll end up with some very valuable practical knowledge about making things.

## Homework


- [ ] (engr) Cut axle for gr7's caster. We will have to shim it with tape.  
- [ ] (engr) Print the remaining parts *first thing in the morning* so they are ready for us this afternoon.  
- [ ] (engr) State machine code review and final (hopefully) build.  
- [ ] #hw (engr) Assemble and program your bot. It should be ready for testing at the start of class.  [[2025-03-27\|2025-03-27]]
