---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/cad-with-onshape/","tags":["gardenEntry"]}
---


# Learning CAD with onshape

- [x] Get an [onshape education account](https://onshape.com)
- [x] Start the [Introduction to CAD course](https://learn.onshape.com/learning-paths/introduction-to-cad)
- [ ] We have a udemy course: [the complete guide to ptc Onshape](https://www.udemy.com/course/the-complete-guide-to-ptc-onshape-cad/learn/)


## Concepts to learn

### Separation of concerns

When you design parts, they always have some areas that are tightly interdependent, and between those areas the restrictions are looser. For example, you might be making a panel that has mounting holes for buttons and various circuit boards. Each button or board has a hole pattern that has to be correct, so the holes that are part of the pattern depend on each other in a tight, precise way. However, it doesn't make nearly as much difference *where on the panel* you put the hole pattern. 

Your design should mirror that - think of the hole pattern as a stamp, and make the dimensions that define the pattern so that you could easily place the stamp anywhere you want. Once the hole pattern is set up like that, give it a reference point and then use *just that point* to place the hole pattern onto the larger part. That way you can move it around without breaking the pattern itself.

### Choosing reference features

When you place a feature (like a hole pattern), you generally have a concept in your head of where it should go that's based on the overall geometry. Examples would be things like "the axle hole goes through the center of the wheel" or "the centerline of the raised square is on the centerline of the overall widget." Make your constraints so that they tell the drawing how to put itself together in the same way that you think of it.

If you put the axle hole so that it's concentric with the wheel, then it will always be in the center where it should be, even if you change the diameter of the wheel. If you instead put the axle hole 2 inches from the edge on a 4 inch wheel, it'll work just fine as long as the wheel size doesn't change, but then if you adjust the wheel your entire design breaks. Think carefully about what's important to the geometry of your parts and try to make your drawing so that it enforces the important stuff.

Constraints are like police, you give them the rules and they make sure the rules are followed. If you pick good rules, your part can be pretty easy to work with. If your rules are all mixed together and tangled, and don't actually reflect the true geometry, then your part will be extremely hard to edit.

### Ease of assembly

Always think ahead to how you will put the final assembly together. Imagine the steps, including things like how you can actually hold on, where the screwdriver will go, how the wrench might reach the bolt head, and what will happen if you accidentally let go of the spring while it's compressed. It's very easy to design something that's physically impossible to assemble, and sometimes the need to *reach a screw* will require you to make large, annoying changes to your design. Be at peace with that, because there is no way to avoid it.

### Error tolerance

Nothing is ever perfect. When you are designing parts that need to fit together, think about how you can give them some wiggle room to allow for things like holes that are slightly out of position or a little bigger or smaller than they should be, or surfaces that aren't perfectly flat. Doing this is called "tolerancing," and it is absolutely vital to making good parts. There are lots of tricks people have developed:

- widen through-holes for bolted together pieces
- make some features as slots instead of exact mates, so that parts can slide a bit past each other
- allow for shims or spacer screws to make fine adjustments
- Always think of everything you draw as having a *range* of sizes, and make sure that your part will work as long as the design is anywhere in that range.


## Projects

Each project will be given as a specification, and in order to meet requirements it must be 3D printed or CNC machined and come out within tolerance.

### Drive wheel

Create a wheel that is 2 inches in diameter, 3/4 inch thick, and has a four-hole bolt pattern to attach it to a hub. The bolts should be 1/2 inch from the center, and will be #6 flat-head machine screws. The visual design of the wheel is up to you!

### Idler wheel

Create a wheel that visually matches the drive wheel, but is designed to have a 1/4" ID ball bearing installed. The wheel must allow the bearing to be securely installed both within the wheel and onto a threaded shaft. This will become the steered wheel assembly for a car.

### Direct-drive hub

Create a hub that attaches to the wheel with four #6 flat-head machine screws. The hub should have a hexagonal hole for a #6 nut to fit into for each screw in order to make assembly easier. The hub will be attached to a drive shaft that is 0.0625" diameter. It should have a hole for a #8 set-screw to be installed that will bind the hub to the drive shaft. The collar that attaches to the drive shaft must be strong enough to support the impacts of a robot moving over uneven terrain!

## Udemy Onshape course

- [x] #hw (cad) [Udemy onshape](https://www.udemy.com/course/the-complete-guide-to-ptc-onshape-cad/learn) videos 11, 12, 19, 20 [[2024-09-27\|2024-09-27]]
- [x] #hw (cad) [Udemy onshape](https://www.udemy.com/course/the-complete-guide-to-ptc-onshape-cad/learn) videos 21, 26, 27, 28 [[2024-10-03\|2024-10-03]]
- [x] #hw (cad) [Udemy onshape](https://www.udemy.com/course/the-complete-guide-to-ptc-onshape-cad/learn) videos 33, 34, 35, 36 [[2024-10-10\|2024-10-10]]
- [x] #hw (cad) [Udemy onshape](https://www.udemy.com/course/the-complete-guide-to-ptc-onshape-cad/learn) videos 37, 38, 44, 45 [[2024-10-17\|2024-10-17]]
- [x] #hw (cad) Model the continuous rotation servo with a basic wheel [[2024-10-17\|2024-10-17]]
- [ ] #hw (cad) [Udemy onshape](https://www.udemy.com/course/the-complete-guide-to-ptc-onshape-cad/learn) video 46 (project) 

