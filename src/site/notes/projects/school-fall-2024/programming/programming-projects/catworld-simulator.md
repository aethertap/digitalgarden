---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/programming-projects/catworld-simulator/"}
---


# CatWorld cat simulator

This is a program that we will use to explore state machines. We will implement a simple cat, which has a few states that it can be in, and a small set of stimuli that it transitions on.

## Cat States

The cat will need to have a few states:

- Content
- Hungry
- Scared
- HungryScared
- Dead

You will receive these different events:

- Pet
- Feed
- Kick
- Tick

Petting a cat removes its scared feelings.
Feeding a cat removes its hunger.
Kicking a cat makes it scared.
If a cat hasn't been feed in 10 seconds or longer, it becomes hungry.
Kicking a cat that is already Scared makes it Dead.
Dead cats stay dead no matter what you do!

Implement a state machine that obeys those rules and has the states listed above. Note that a cat can be both hungry and scared at the same time!

git clone https://github.com/aethertap/catworld catworld2

- [x] #hw implement the state transitions for the cat simulator [[2024-11-05\|2024-11-05]]