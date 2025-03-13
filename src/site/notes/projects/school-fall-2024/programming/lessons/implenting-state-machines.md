---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/implenting-state-machines/"}
---


#  On the implementation of state machines

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


### Relevant projects

- [[projects/school-fall-2024/programming/programming-projects/tank-battle-game\|Project index: tank-battle-game]]
- [[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|differential-steering-bot]]

## Concept summary and lesson

- Class hierarchies 
- typescript vs c++ 
- Headers and declarations vs implementations 
- The c++ preprocessor 
- Incremental updates 

## Examples/demo

Today we're going to pair-program our way through a couple of simple state machine implementations, one in typescript and one in c++. We'll see how the two are similar and how they are different, and we'll talk about some tradeoffs for implementing state machines. 

There are two main approaches to making a state machine, and they each have strengths and weaknesses: 
- The giant switch statement
- The class hierarchy

### The Giant Switch Statement

The most straightforward way to make a state machine is to just have a simple switch statement that does something specific for each different state:

```c++
switch(state) {
case STATE_1: 
    do_state1_stuff();
    break;
case STATE_2:
    do_state2_stuff();
    break;
//...
default:
    do_default_stuff();
    break;
}
```

This approach has some nice features! Don't discount it because it's so simple. Here's what it's good for:

- Getting a working state machine done **quickly**. These are very quick to write, and they're easy to debug becasue everything is in the same place.
- Implementing a *small* state machine in the most readable way. When your state machine doesn't have dozens or hundreds of states, this is a good option. It's small, it's very fast (running and easy to write), and it's pretty simple to maintain.
- No overhead - Using classes and virtual functions makes your code *just a tiny bit slower* because of something called *dynamic dispatch*. The switch statement avoids that.
    - This is generally not an important reason to do this, because you probably have other things in the code that cause thousands of times more slowdown than this!

This approach is weak when:
- There are more than a handful of states to juggle
- You have to do things on entry and on leaving of each state. In this approach, you have to make *extra states* representing the enter and leave for each of the other states
    - Example: for a `Drive` state, you'd need to add `EnterDrive` and `LeaveDrive` **as separate states** with their own transitions.
- The states themselves have different data attached to them. You have to store all of that stuff somewhere, and it ends up being in a giant structure usually

### The class hierarchy

In this version of the state machine, we make `class`es for:
- The state machine itself
- The state base class, which describes the *interface* that every state has to have
- Each of the individual states.

The state machine keeps track of the currently-active state, and it has the list of possible states that could be active. The active state is always an *instance* of the `State` base class, and it always has functions that you can call to `enter`, `update`, and `leave`. The state machine also has a way to let the active state tell it to switch to a *different* state. This might be a return value from the `update` function, or it might be a message sent, or the state machine can just pass a reference to itself into the state's update function so the state can tell it when something has to happen. The third option is the most frequently used, but it has some problems with strict languages like `rust`.

There is an example of a c++ state machine in the [[projects/school-fall-2024/engineering/lessons/line-following\|Line Following]] lesson.

The class hierarchy approach is good for more complex state machines, where having all of the state code in a single file is just not practical. In this case, splitting it up into state classes makes the code a lot easier to understand, and it gives you some extra powers:
- `enter` and `leave` are easy to implement. In the switch version, you have to make *separate states* for the enter and leave phases of each state that requires them.
### How do you choose?

When you're comfortable with the class hierarchy version of this, it's probably best to just default to that one. Most of the time, the number of states in your state machine will be way larger than you expected at the start! 

## Media resources

- [Youtube search for "Class hierarchies"](https://www.youtube.com/results?search_query=Class%20hierarchies) 
- [Youtube search for "typescript vs c++"](https://www.youtube.com/results?search_query=typescript%20vs%20c++) 
- [Youtube search for "Headers and declarations vs implementations"](https://www.youtube.com/results?search_query=Headers%20and%20declarations%20vs%20implementations) 
- [Youtube search for "The c++ preprocessor"](https://www.youtube.com/results?search_query=The%20c++%20preprocessor) 
- [Youtube search for "Incremental updates"](https://www.youtube.com/results?search_query=Incremental%20updates) 


## Homework

