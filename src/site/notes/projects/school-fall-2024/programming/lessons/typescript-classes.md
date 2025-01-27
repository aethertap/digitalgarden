---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/typescript-classes/"}
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

## Typescript syntax

The `class` keyword is used to create a new class in typescript. It'll look like this:

```typescript
class Cat extends Animal {
    breed: string
    constructor(kingdom:string,phylum:string,class_:string,order:string,family:string,genus:string,species:string,breed:string) {
        super(kingdom,phylum,class_,order,family,genus,species);
        this.breed = breed;
    }

    meow():string {
       return "MRowl"
    }
}
```

Remember *Kids Playing Chess On Freeways Get Squashed*? (Kingdom, phylum, class, order, family, genus, species...)

Anyway, there are a few things in this class to notice.
- `extends` tells the class that a `Cat` is a *kind of* `Animal`. This means that the cat gets to have all of the features of the Animal class, and it can override them or add new ones as you wish.
- `constructor` is a special function that gets called whenever you make a new cat, which looks like `let my_cat = new Cat("animal",...)` (extra args left as an exercise for the reader...)
- *Member functions* or *Methods*, like `meow` in the example, don't need the `function` keyword. Just put the name of the function, its arg list, and the return type.
- *Member variables*, like `breed`, are declared inside the class but not inside a function. They don't need a `var` or `let` keyword. These become values that you can use anywhere inside the class' code. They're *part of the cat*, so any cat function can see them.

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

- [x] #hw (programming) (gr7) Design a class hierarchy with at least three levels and 10 classes for demolition derby vehicles [[2024-10-16\|2024-10-16]]
- [x] #hw (programming) (gr10) Design a class hierarchy with at least three levels and 10 classes for pets [[2024-10-16\|2024-10-16]]
- [x] #hw (programming) Design a class hierarchy of [Fey Creatures](https://2e.aonprd.com/Traits.aspx?ID=599). It should have at least 5 creatures, and at least two levels of categories. Remember: The creatures are going to be at the **bottom of the diagram**, and everything above is a way to *organize them*. How would you organize Fey creatures? Be creative! [[2025-01-24\|2025-01-24]]

## Resources

- [Difference between objects and classes in 8 minutes](https://www.youtube.com/watch?v=BM9tPve8T1o)
- [Typescript classes](https://www.typescriptlang.org/docs/handbook/2/classes.html)

