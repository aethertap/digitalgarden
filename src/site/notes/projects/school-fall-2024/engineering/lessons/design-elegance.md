---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/design-elegance/"}
---


#  Design Elegance

## Links and useful resources 

- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)

### Lesson-specific resource links

- [Sunbeam Radiant Control Toaster](https://www.youtube.com/watch?v=1OfxlSG6q5Y) 
- ***[[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|differential-steering-bot]]*** 

- Using subtle effects - thermal expansion of nichrome wire 
- Design elegance: 
    - Everything that happens is part of the solution. Use all of the side effects from what's already there to solve the problem, instead of introducing special cases and parts.
    - Limited or zero special-case handling.
    - Minimal design - since all of our goals are met by harnessing all of the side-effects, we don't need extra systems in place.
- In the quest for elegance: 
    - Ask yourself, "How can I USE this effect?" instead of, "How can I DEAL WITH this effect?"
    - When you're designing your way around something, try to think of a way you could put it to work in order to solve *another* problem instead of just adding a patch to avoid it.

### Parametric designs, and Separation of Concerns (again...)

We're designing with OnShape, which is a CAD tool that allows us to change our parts just by changing the dimensions we used for constraints. That's called *parametric* design, because it uses *parameters* to control the final shape. Having parametric design lets us make parts that are easy to configure, but only if we make the constraints well.

So, what kind of constraints are the right kind? 

- They should respect the geometry - if symmetry or overall size is important, constrain it *directly* rather than relying on it to work out as a result of other constraints
- Dimension what's *important to the function* - this means that hole patterns for mating parts need to be self-contained within the pattern, and then *placed* on the mating part using a simple positional constraint. Don't dimension every hole independenly of the others if they all depend on each other
- Keep independent things separate - Just like you *do* want to have holes in a pattern laid out relative to each other, you *don't* want to make positions of separate pieces tangled up with each other. If you're mounting two circuit boards to a panel, make each hole pattern a stand-alone pattern, then position *both* of them relative to the geometry of the plate independently of each other

Basically, you want to capture dependencies that matter, and not introduce any new ones that aren't actually required for the function of the part! This is an art, and it takes practice. It is well worth the effort though, and it leads to a way of thinking that is closely related to the [[projects/school-fall-2024/programming/lessons/classy-tanks\|Separation of Concerns]] that we use in code design. Don't tangle things together unless it represents a real-life situation.

## Homework

- [ ] #hw (engr) Finish robot chassis redesign, make sure you include a way to attach additional sensor modules [[2025-03-11\|2025-03-11]]
