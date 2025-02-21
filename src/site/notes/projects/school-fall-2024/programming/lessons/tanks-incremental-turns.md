---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/tanks-incremental-turns/"}
---


#  Incremental changes, loop updates

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


### Lesson-specific resource links

- https://en.wikipedia.org/wiki/Proportional_control 
- https://x-engineer.org/proportional-controller/ 

- ***[[projects/school-fall-2024/programming/programming-projects/tank-battle-game\|Project index: tank-battle-game]]*** 
## Concept summary and lesson


- How to control a turn that takes more than one iteration to complete 
- Proportional control 
- How to control a linear move that takes more than one turn to complete 

## Examples/demo

We want to write code that can make our tanks turn to face a specific angle, but the turns take way longer than one call of our function to complete. What do we do?? We have to change our thinking about how the turn works, and consider it from the angle, "what can I do right now to get closer to my goal?"

The answer to *that* question, of course, is, "turn a little bit." 

### How to turn a little bit

It's pretty easy to make your tank turn a little bit each iteration: just set the controls so that it turns! Sadly, that's not the hard part. The hard part is actually two hard parts: Deciding which direction to turn, and knowing when to stop. Let's take a look at the first problem first.

### What direction should I turn?

This seems pretty easy, but there's a wrinkle that's actually kind of subtle to overcome: angles have a *discontinuity* at zero. There are two representations for the angle at that point: either 0, or *any number times* $2\pi$. That causes a problem for code that just subtracts the starting point from the ending point and goes that way, because to get from $\frac{3\pi}{4}$ down to 0, the simple code will make you turn $0-\frac{3\pi}{4}=-\frac{3\pi}{4}$ (the entire 270$\degree$) angle rather than going the other direction, which is only  $90\degree$.

So, we're going to have to adjust the angles somehow. We want to end up with our orientation matching the target angle, so the best thing to do is to adjust our *starting* angle (instead of the *target* angle, which may seem more natural). We need to have a way to detect that this adjustment is needed, so what does that look like?

If you think about turns for a bit, you'll see that there should never be a need to turn by more than $180\degree$, or $\pi$. So if you subtract *target* - *current* and get an angle larger than that, you need to make the adjustment.
```typescript
if(Math.abs(target_angle - current_angle) > 2 * Math.PI) {
    // make some kind of adjustment to the angles
}
```

Okay, so we know *when* to do it, but *how* do we adjust the angle? What's the actual problem here? The problem is that we're using positive or negative angles to represent different directions of turn, but because we have that $2\pi$ discontinuity, the *closest* turn isn't always the right *sign*. Switching the order of the subtration doesn't work either, because the difference is still the same size! What we need to do is realize that there are actually two different turns we're representing here, clockwise and counterclockwise. A clockwise turn makes the angle *larger*, while a counterclockwise turn makes it *smaller* (until it wraps around of course). So, we could just calculate the angle for each kind of turn and pick the smallest one. Let's make a function that computes the clockwise turn angle between two directions. 

First off, we need to make sure that our target and starting angles are between 0 and $2\pi$, so if the target angle is negative add $2\pi$ until it's positive. We'll want to do this whether we're turning left or right; it's called normalizing our data (making it "normal" in the sense that we know its bounds and any weird values are adjusted so they don't break our algorithm).

If I want to turn clockwise, that means the target angle has to be larger than the starting angle. Since I want to make my adjustments to the starting angle, I can subtract $2\pi$ from it to make sure the target angle is the larger of the two. This will make my starting angle, negative, so when I subtract it from the target angle, I'll end up with a *positive* turn, which is clockwise. 

Now we can do the counterclockwise turn version in a similar way. In this case, we want to turn in order to make our angle *smaller*, so that means the starting angle needs to be *larger* than the ending angle. If it isn't already, we can just add $2\pi$ and it will be. Now when we subtract the end from the start, we'll have a *positive* number and we'll be making a *counterclockwise* turn.

```typescript
function clockwise_turn(from_angle:number, to_angle:number):number {
    if(to_angle > from_angle) {
        from_angle += 2*Math.PI;
    }
    return to_angle - from_angle;
}
```

```typescript
function counterclockwise_turn(from_angle:number, to_angle:number):number {
    if(to_angle < from_angle) {
        from_angle -= 2*Math.PI;
    }
    return to_angle - from_angle;
}
```

Now we can just call each of those functions and pick the smallest magnitude of turn:

```typescript
function turn_toward(from_angle: number, to_angle:number) {
    let ccw = counterclockwise_turn(from_angle,to_angle); // get the angle for a right turn
    let turn = clockwise_turn(from_angle,to_angle); // default to the left turn angle
    if(Math.abs(ccw) < Math.abs(turn)) { // switch to the right turn if it's better
        turn = ccw;
    }
    // now do our turning control
}
```

### But, when do you stop?

Stopping at the right moment is another challenge. The problem is that our max turning speed is pretty fast, so we're likely to overshoot and end up turning too far if we just do the "turn at full speed until our angle is close enough" strategy. We need to be a bit smarter.

The real problem is only on the *last step* of our turn! That's the place where we are likely to turn too far - otherwise, we can go max speed and be just fine. So how do you know when you're on the last step? You have to *predict where you're going to end up* and check to see if it's too far. If it is, you scale back your speed so that you just exactly finish the turn in the time allotted.

Predicting where you'll end up means you have to know your turning rate (angular velocity) as well as the amount of time you'll have before the next iteration where you can stop. Fortunately, we have a `delta_t` variable handy, and we can figure out our turning rate from the tank's max track speed and wheelbase (using our differential steering math from earlier).  

So, the code that knows when to stop turning looks like this:

```typescript
let max_turn_speed = track_speed/(wheel_base/2); // assume tracks going in opposite directions to turn in place
if(turn < delta_t * max_turn_speed) {
    // We want to have a turn that gets us exactly to the right place, so we 
    // set the speed to be that number of radians per second. One delta_t spent at this
    // speed should turn us by exactly the amount of angle we need!
    max_turn_speed = turn/delta_t; 
}
```

## How about straight-line driving?

This is going to be part of your homework, but it is *very* similar to the section above about knowing when to stop. You can cruise along at max speed right up until your next move at that speed would take you too far, then scale it back so you end up in the right place. Fortunately for us, our tanks don't currently have any inertia to worry about, so they can stop in zero distance!

## But, what about inertia?

Inertia and slipping are real-world things that we definitely have to deal with in robotics code, but they're also really complicated and difficult to predict. In order to handle this problem, there's an entire discipline called *Control System Engineering* that creates algorithms that *adapt to errors in order to correct them* rather than making perfect predictive movements. 

The control system we'll be starting out with is the simplest one: proportional control. The basic idea of this is that your control input (the speed setting, or how much change you can make) is proportional to how far you are from the target. If you're a long way off, you should move faster. If you're right next to it, you should make smaller changes.

In the tanks, this would amount to using our error as a multiplier to figure out our speed (whether it's turning or moving, the process is the same). A big error means a big speed is fine, but a small error should slow us down. The only thing that proportional control adds to that idea is that we need some kind of scale factor to use along with the error. The scale factor is just a number that kind of wraps up all of the little details of our system - how powerful the control is, how sluggish the response is, etc. etc. We don't have to compute the scale factor, instead we find it by "tuning" our controller until it gives us the best performance. That process just means that we run lots of trials and adjust this extra multiplier up and down until we find a sweet spot where it works the best.

This kind of control has problems: it's very slow to converge on the right value, it can end up oscillating around the target, and it doesn't deal with things like persisten errors (imagine a ship being blown off course by a wind, there would be a constant error that the proportional control wouldn't handle well). These extra problems are handled by adding more components to our control signal (the Integral and Derivative, to be specific), but we'll get to those later.


## Media resources

- [Youtube search for "How to control a turn that takes more than one iteration to complete"](https://www.youtube.com/results?search_query=How%20to%20control%20a%20turn%20that%20takes%20more%20than%20one%20iteration%20to%20complete) 
- [Youtube search for "Proportional control"](https://www.youtube.com/results?search_query=Proportional%20control) 
- [Youtube search for "How to control a linear move that takes more than one turn to complete"](https://www.youtube.com/results?search_query=How%20to%20control%20a%20linear%20move%20that%20takes%20more%20than%20one%20turn%20to%20complete) 


## Exercises

- [ ] #hw (programming) Write a function in your tank code that drives your tank forward by a specific distance. You'll need to use some of that vector math  for this! [[2025-02-24\|2025-02-24]]
- [ ] #hw (lang) Write a one-sentence explanation about proportional control that answers **what**, **how**, and **why** that's based on the sentence kernel "it controls movement." Outline your sentence first with your answers to the three questions, then write a well-structured sentence that includes your answers. [[2025-02-24\|2025-02-24]]

