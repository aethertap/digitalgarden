---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/multiple-photogates-interrupts/"}
---


#  Multiple Photogates and Interrupts

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


### Lesson-specific resource links

- [Arduino attachInterrupt](https://docs.arduino.cc/language-reference/en/functions/external-interrupts/attachInterrupt/) 
- [Detailed notes about arduino interrupts](http://gammon.com.au/interrupts) 

- ***[[projects/school-fall-2024/engineering/engineering-projects/photo-gate-project\|Our engineering project to build a photo gate]]*** 


### Warmup fun stuff (rollback networking for multiplayer games)

- [Rollback networking](https://en.wikipedia.org/wiki/GGPO#Design) for multiplayer game programming
- [Using rollback networking in bevy](https://johanhelsing.studio/posts/extreme-bevy)
- [Old sample code of rollback networking in Godot](https://github.com/ValorZard/Godot-Rollback-Netcode---Example)

## Concept summary and lesson


- interrupts 
- interrupt service routines on arduino 
- non-blocking event loops 
- volatile variables in c 

## Examples/demo

So far, we've been doing something called "polling" for our changes. Polling means that you ask the same question over and over again, and react when it changes. Polling is simple and straightforward and usually good enough in a project like this, but in this case, we will eventually have *several* photogates all connected to the same arduino. The problem that could arise is that it might take too long to get through all of our inputs each time we go through the loop, and that could give us some timing inaccuracies.

In reality, we'd be *just fine* in this case, but this is school, where we practice things, so... let's do it both ways!

In the polling method, we'll go through each of our gates in order on every loop iteration and note which ones have been blocked or not at any given time.

In the interrupt method, we'll *make a new interrupt handler* for every possible gate pin, and have it update a variable for us that we can look for in the loop function. *Then* in the loop function we'll report times and stuff.

Why would we want to do the extra work for interrupts? Mainly, because they'll almost always end up being more accurate. The arduino has hardware that's watching for changes on the pins in question, and when it sees one it is *very quick* to report it. Imagine in the polling version, if we *just finished* checking a pin and then it switched states. We'd have to wait until the rest of our pins were checked, then wait for the stuff all around the loop function to finish, then for our function to get called again and our code to read the pin again. That time sometimes adds up to a significant delay! 

With the interrupt version, the code that's currently running gets stopped immediately in order to let the interrupt service routine (ISR) handle the interrupt.


## Media resources

- [Youtube search for "interrupts"](https://www.youtube.com/results?search_query=interrupts) 
- [Youtube search for "interrupt service routines on arduino"](https://www.youtube.com/results?search_query=interrupt%20service%20routines%20on%20arduino) 
- [Youtube search for "non-blocking event loops"](https://www.youtube.com/results?search_query=non-blocking%20event%20loops) 
- [Youtube search for "volatile variables in c"](https://www.youtube.com/results?search_query=volatile%20variables%20in%20c) 


## Exercises

- [ ]  #hw (programming) Change your implementation of the photogate so that it uses an interrupt to signal a beam break. How will you keep track of which gate caused the interrupt? [[2025-01-24\|2025-01-24]]
