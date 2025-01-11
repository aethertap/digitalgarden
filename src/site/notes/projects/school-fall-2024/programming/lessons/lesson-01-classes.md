---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/lesson-01-classes/","tags":["gardenEntry"]}
---


# Classes in Object-oriented programming

## In-class discussion

- A class is a *kind of thing* - they don't actually exist until you make an *instance*
- Classes can also be *variations of other classes* 
    - Inheritance - I'm a cat, but also an animal
    - Do everything the *superclass* does, but maybe with a few changes and some extra features
    - Child class has the parent class inside like a nesting doll
- In programming, a class makes a new type.
    - You know types from other variables: they are things like *int* and *string*
    - You can't ever just have *an int* - you always have a particular *int* like 7.
    - The same thing applies to classes, when you create one, you have an *object*, whose type is the *class* it came from
- An *object* or *instance of a class* can act like itself or any of its ancestor classes, because it has all of them embedded into itself
- This lets you do things like have an array of Pet, where each item is actually a Dog,Cat,Bird, or other pet object. None of them are actually instances of just *Pet*, but all of them know how to do Pet stuff!

## Practice

- Design a class hierarchy for pets
    - All pets are animals
    - Some pets are mammals, some reptiles, some avian
    - What things can each particular type of pet do that others may not?
    - What can *all animals* do?
    - What can *all birds* do?
- Design a class hierarchy for vehicles
    - Cars, trucks, trains, bicycles, planes, spaceships, cargo ships
    - What is the same, and what is different?
    - How much stuff can you fit into the super class for each category?

- [x] #hw (programming) (g7) Design a class hierarchy with at least three levels and 10 classes for demolition derby vehicles [[2024-10-16\|2024-10-16]]
- [x] #hw (programming) (g10) Design a class hierarchy with at least three levels and 10 classes for pets [[2024-10-16\|2024-10-16]]

## Resources

- [Difference between objects and classes in 8 minutes](https://www.youtube.com/watch?v=BM9tPve8T1o)
- [Typescript classes](https://www.typescriptlang.org/docs/handbook/2/classes.html)
- 

