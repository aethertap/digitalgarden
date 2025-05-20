---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/pursuit-algorithm/"}
---


#  Chasing down a tank

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


- ***[[projects/school-fall-2024/programming/programming-projects/tank-battle-game\|Project index: tank-battle-game]]*** 
## Concept summary and lesson


- How can you pick the best path to intercept a moving target? 
- Proportional navigation: Try to control steering to make the line-of-sight angle constant, so you're on an "intercept triangle"

### Proportional Navigation

Here's the main idea in a nutshell: You want your tank to be on one side of a triangle, and the enemy tank to be on another side. Since triangles come to points, that guarantees you'll intercept them if you can keep going long enough.

You know if you're on a triangle by watching the angle between the direction you're heading and the target. If the angle isn't changing, you're on an intercept triangle. If the angle is changing, then you should steer in the direction of the change.

The proportional part is a tuning parameter you can use to decide how much you turn when the angle is changing - bigger numbers mean sharper turns.

## Media resources

[Shot leading without trigonometry](https://www.youtube.com/watch?v=MpUUsDDE1sI)
[Proportional navigation law](https://www.youtube.com/watch?v=cXDyyQrfY5M)

## Homework

- [x] #hw (programming) Implement a chase mode for your tanks, so that your tank will try to chase down an enemy. [[2025-04-16\|2025-04-16]]
