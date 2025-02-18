---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/photogate-review-bot-race/"}
---


#  Photogate review and bot race

## Links and useful resources 

- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)

 
- ***[[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|Project index: differential-steering-bot]]*** 
- [ ] #hw (engr) Work through the problems under **Homework** at this link: [ginosterous engineering](https://school.ginosterous.com/projects/school-fall-2024/engineering/lessons/photogate-review-bot-race) [[2025-02-18\|2025-02-18]]
- [x] #hw (science) Read [Ancient black holes](https://www.snexplores.org/article/ancient-black-holes-dark-matter) and summarize it in one sentence. [[2025-02-17\|2025-02-17]]

## Concept summary and connections


- Checking over the photogate designs 
- replacing broken servo on gr7's bot 
- Attempt to drive the bots! 

## Lesson Content

We're doing final assembly on the line-follower bots today, and I want to get them driving. I suspect we're going to find some issues with the caster wheel on the front (too much steering resistance for the amount of traction we have with the drive wheels), but we will have to try it out to see what happens. We may have another option for the front support, we need to check in our box of goodies.

I also want to finally get a good look at the photo gates and start them on the 3D printer. If all is well, it would be good to get them operational before next week.

### Differential Steering Math

Our main lesson today is going to be understanding the math of differential steering. When our bot makes a turn, what's the turn radius? What's the center of the turn? How the heck do we even figure that out?

You already have all of the math you need to be able to answer those questions! At least, as long as you remember your radians...

Here are some warmup questions:

- How far does a wheel travel as it rolls? Assume you know the diameter of the wheel and the angle of turn.
- If two wheels are rolling at different speeds but they're stuck to the same axle, what will happen?
- Say you have a *really long* axle that sticks out far past the wheels on both sides, and you attach it to a post so that the wheels have to travel in a circle. How would you figure out the speed of rotation for each wheel?
- Now say that you *programmed* each wheel to have exactly that speed of rotation, then remove the post. What will happen?

When you get through those answers, you'll have the key to differential steering. 

## Homework

Let's explore a bit about how differential steering works. Answer the questions for the robot described below (assume there is never any wheel slippage):

- Drive wheel diameter: 10 cm
- Distance between drive wheels: 15 cm
- Max angular velocity of wheels: 360$\degree$ per second

1. How far will the robot move if the wheels rotate one revolution forward?
2. What is the robot's top speed?
3. If the right wheel is moving at full speed, but the left wheel is stopped, describe the robot's motion.
4. What is the angular velocity of the *robot* (not the wheels) in problem 3?
5. Now say that the right wheel is moving at full speed, but the left is moving at half that speed. Describe the robot's motion.
6. What is the radius of the turn that the robot is making in problem 5?
7. What is the angular velocity of the robot in problem 5?

