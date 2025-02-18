---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/programming-projects/dealing-wtih-relative-turn-angles/"}
---


# Relative turn angles

Game engines tend to deal with left and right turns rather than absolute angles (so they say your orientation is between -180 and 180). It wouldn't actually matter if they went 0 to 360, because the underlying problem of a big discontinuity would still be there. This is very annoying to deal with when you're writing orientation code.

So, how can you make it less painful? The central problem comes in trying to interpolate between values that cross the discontinuity where 180 = -180, because any kind of numerical interpolation will not see those as adjacent values, and you'll end up spinning around the long way rather than taking the "natural" sub-180-degree turn.

Straight forward is defined as 0, left is 90, right is -90. If you're between -90 and -180, but you wanted to be at 90, then the natural thing is to subtract the start from the finish and interpolate through that range. However, -100 (target) minus 90 (start) is -190, and that's *more than 180 degrees* so you're going the wrong way! You should never need to turn by more than 180 degrees (otherwise, you should have turned the other direction).

To solve the problem, you have to make sure your current angle and target angle are measured from zero in the same direction (clockwise or counter clockwise; negative or positive angle, etc). If they are, then your current angle is the one that's off the mark and it will need to be adjusted so that interpolation can run smoothly. 

The thing that's actually hapening here is this:
- **The current and target angles have incompatible representations**. One of them is a **clockwise** rotation, and the other is **counterclockwise**.
- In order to interpolate between them, they have to be the **same kind of rotation**
- Changing the representation of the **current angle** means that you'll always end up with your *final current angle in the right representation* (after the turn is complete, current angle will be equal to the desired target angle instead of the opposite representation of it).

Here's how to do the turn:

1. Subtract $target-current$. If that answer has a magnitude greater than 180, then just interpolating the turn from current to target will take the long way around, so you need to flip the sign of the *starting* angle.
2. To flip the sign: 
    1. If starting angle is positive, subtract 360
    2. If starting angle is negative, add 360
3. The equivalent mathy way is do $\text{new target} = \text{target} -\text{sign}(\text{target})*360$

The reason you should adjust the current angle instead of the target is that you want to end up with your angle being *equal to the target value, as specified*. Otherwise, you can end up accumulating a huge angular value because you're adding 360 every time without ever correcting it back down. Changing the representation of the current angle so that it matches the target angle avoids that problem.

Examples:

Target angle: 90
current angle: -120
target - current: $-120 - 90 = -210$ 
The turn is too large, and current angle is negative, so I add 360: $-120+360=240$ . Now I can interpolate naturally from 240 to 90 (a -150 degree turn)

Target angle: -90
current angle: 110
target - current: $-90-110 = -200$ 
The turn is too large, and current angle is positive, so I subtract 360: 110-360=-250$. Now I can go smoothly from -250 to -90 (a *positive* 160-degree turn)

