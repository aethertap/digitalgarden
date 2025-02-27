---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/robots-turning-on-the-sensors/"}
---


#  Turning on the Sensors

## Links and useful resources 

- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)

 
- ***[[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|Project index: differential-steering-bot]]*** 

## Concept summary and connections


- Multiplexing in space and time (avoiding interference with the sensors) 

## Lesson Content

We need to get our bots to open their eyes, so to speak. We're going to run into some complications right away though (big surprise, right!?). The issue is that we want to have a bunch of active sensors sitting very close to each other, and it's very likely that they're going to interfere with each other if they're on at the same time. When light hits a surface in the real world, it *scatters* in a wide spray. That scattered IR light will most likely travel from the two sensors that see white into the one that's supposed to see black, making it think it's seeing white as well. This is now an engineering problem!

### Multiplexing

The root of the issue here is that we have to share something between a lot of selfish devices. Each one wants to be the only one, but that's not an option. Our job is to figure out how to make them share!

There are two main ways we usually do this: *space* multiplexing and *time* multiplexing. Space multiplexing is where you arrange things so that they can do their jobs without being so close together that they mess with each other. In communications, they do this with frequency assignments - each channel gets a frequency that's different enough from the others that they don't have cross-talk. In our bot, this would mean either spreading the sensors apart, or making them each require less room. Since spreading them apart isn't going to work because of our needs for detecting a line, how could we make them take less room?

- Put shrouds around them - the most obvious answer is to put a shroud around each sensor to try to contain its scattered light and block the light from other ones. This will probably work, but it's a fragile solution. Why? What kinds of things could go wrong?
- Use focusing optics - the setup on the sensors right now takes light from a pretty wide angle. If we could put lenses in front of them to focus the light, it would probably reduce the problem quite a bit. However, IR optics are not easy! Glass is not transparent to infrared light!
- Turn the brightness and sensitivity down on each sensor, so it's less likely to trigger on indirect light. This *might* work, depending on how big the problem actually is. It's the easiest to implement, so it's probably worth trying first.

Okay, so our options for space multiplexing so far don't seem great. What about time multiplexing? How does that work? 

In time multiplexing, you only give control of the space to one thing at a time, and you make them take turns. The idea is that you can make the turns fast enough that you don't risk any errors from having sensors disabled at times. If that's true, then time multiplexing is a good option. How could we do this?
- Write a function that only turns one sensor on at a time, and it gives it a *very short* window for sensing (maybe, 1 millisecond). It then immediately goes to the next sensor to check, and so-on.
- You could also try just turning off the middle sensor and keeping the outer sensors lit to see if they are far enough apart to avoid interference. You'd then be switching between middle and outer-two, so instead of three cycles between sensor checks, you'd only have two.

This solution will probably be more reliable than the shrouds. Why is that? 

Let's get these bots driving around on some lines! It's about time!

## Media resources

- [Youtube search for "Multiplexing in space and time"](https://www.youtube.com/results?search_query=Multiplexing%20in%20space%20and%20time) 

## Practice

- [ ] #hw (lang) Think about how you would make a shroud for the IR sensor to prevent scattered light interference. Use an ACE response format to explain why shrouds would be hard to use in real-life.
- [ ] #hw (engr) Write a function to scan through your sensors so that only one is on at a time. Experiment with the timing to see how fast you can go.  [[2025-02-27\|2025-02-27]]
