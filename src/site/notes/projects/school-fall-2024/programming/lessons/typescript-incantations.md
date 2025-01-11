---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/typescript-incantations/","tags":["gardenEntry"]}
---


# Typescript Incantations

These are the subtle murmurings you must make in order to use the features of typescript:

## Importing code from other modules

If you're trying to import code from other files in your project:

```typescript
// DON'T put the '.ts' extension on the path! It will not work!
import * as thestuff from './path/to/thestuff';
```

If you're importing something that you installed with `npm`:

```typescript
// If you have the readline package, it gets imported like this:
import * as readline from 'nodegui';
// If it's from another source, you sometimes need to specify the source:
import * as nodegui from '@nodegui/nodegui';
```

## Declaring a class

```typescript
class MyNewClass {
    my_data: number
    my_name: string
    constructor(data: number, a_name_to_use: string) {
        this.my_data = data
        this.my_name = a_name_to_use
    }
    some_func(cool_numbers: number[]): bool {
        // do something cool that returns a bool
    }
}

// if you want to extend a class
class Dog extends Animal{
    my_name: string
    constructor(has_feet: bool, name: string) {
        super(has_feet); // initialize the Animal base class
        this.my_name = name; //initialize myself
    }
}
```


## Declaring an interface

An interface is a promise you can make that says that any object that implements it can do some things. That lets you pass all kinds of different things around that have something in common, and use the common feature to get stuff done.

```typescript
interface Pet {
    name():string;
    // returns true if that was enough food...
    feed(food_amount: number): bool;
}

/// Now you can make a class that implements the interface
class Dog implements Pet {
    name():string {
        return this.my_name;
    }
    
}
```