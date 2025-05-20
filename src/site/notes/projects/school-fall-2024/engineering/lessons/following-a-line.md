---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/following-a-line/"}
---


#  Following the Line

## Links and useful resources 

- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)

 
- ***[[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|Project index: differential-steering-bot]]*** 

## Follow the line

Our basic line-following process looks like this:

- If the middle sensor sees the line, go straight
- If the left sensor sees the line, spin in place to the left until the middle sensor sees it
- If the right sensor sees the line, spin in place to the right until the middle sensor sees it

This works, but it's very inefficient in terms of motion speed. How could we do better?

- As long as one side sensor is detecting the line, we're not that far off. Maybe we can just *veer* to that side while still moving forward. 
    - Adjust the inside wheel speed down, or the outside wheel speed up, and continue
    - If we lose the line entirely, it's time to spin toward the last side that saw it.
- 
## Media resources

- [Youtube search for "Checking sensors, adjustability"](https://www.youtube.com/results?search_query=Checking%20sensors,%20adjustability) 
- [Youtube search for "Options for control"](https://www.youtube.com/results?search_query=Options%20for%20control) 



## Homework


- [x] #hw (engr) Time your bot as it goes around the track a few times and record the data.  [[2025-04-22\|2025-04-22]]
- [x] #hw (engr) Make some adjustments in your code to see if you can make it either more reliable (if it has a hard time staying on the line) or faster. Repeat the time trials to see if it helped.  [[2025-04-22\|2025-04-22]]
