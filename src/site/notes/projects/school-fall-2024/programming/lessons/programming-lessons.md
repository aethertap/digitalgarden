---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/programming-lessons/","tags":["gardenEntry"]}
---



# Programming Lessons

## [[2024-09-17\|2024-09-17]] - Classes and OOP

- Classes are bundles of data with functions attached
- The goal is to hide the insides from the rest of the world
    - simplifies big projects by keeping code and data close together
    - Prevents spaghetti code
    - Makes updates easier
    - "object-oriented design"
    - This is called **encapsulation**
- Classes can *inherit* other class' features (this is called **inheritance**
    - `class Person`
    - `class Kid extends Person`
    - You get all of the *functions* of the parent class, but the *data* is usually hidden for safety
    - You can *override* functions from the parent with your own version, and you can *call* the parent's version if you want to do that plus some more
    - Sometimes a parent class leaves a "fill-in-the-blank" function that you *have to implement* in order to extend it.
    - Some classes don't have any data, and don't implement any of their own functions. In that case, it's called an *interface* because all it does is make a promise.
        - Any class that implements my interface will do all of these things
        - You can put anything in a variable that holds an interface type as long as it implements the interface. 
        - This is called **polymorphism**
- Programming that's based on encapsulatoin, inheritance, and polymorphism with classes is called *Object-oriented* because it uses *objects* as the main idea to organize code.
    - c++
    - typescript
    - java
    - gdscript
    - python
- There are other paradigms: *functional*, *imperative*, *constraint-logic*, and other weird ones.
    - Most modern languages are *multi-paradigm*, which means you can use ideas from more than one of these


## Setting up a typescript project

Basically, just adapt this `package.json` file, then type `npm i`:

```json
{
  "name": "",
  "type": "module",
  "version": "1.0.0",
  "description": "",
  "scripts": {
    "build": "npm run build-code && npm run build-bundle",
    "build-code": "tsc",
    "build-bundle": "esbuild build/main.js --sourcemap --bundle --outfile=dist/main.cjs --platform=node --format=cjs",
    "run": "node dist/main.cjs",
    "br": "npm run build && npm run run",
    "test": "jest"
  },
  "author": "Erik Lee",
  "license": "MIT",
  "homepage": "",
  "devDependencies": {
    "@babel/preset-env": "^7.25.4",
    "@babel/preset-typescript": "^7.24.7",
    "@jest/globals": "^29.7.0",
    "@types/node": "^22.5.4",
    "esbuild": "^0.23.1",
    "jest": "^29.7.0",
    "typescript": "^5.6.2"
  },
  "dependencies": {
    "source-map-support": "^0.5.21"
  }
}
```

## Unit testing with jest

`jest` is a javascript test framework that makes it easy to test small parts of your code. You have to install it along with babel:

```bash
npm i --save-dev @jest/globals
npm i --save-dev @babel/preset-env
npm i --save-dev @babel/preset-typescript
```


Here's how it works:

```typescript
// first you have to import the functions you'll need
import {test,expect} from '@jest/globals';

// Now you make tests
// first call test("a description of your test", () => {a function that does the testing})

test("Make sure true things are still true", () => {
    // expect is a function that takes a value and returns a test object. The test
    // object has a ton of methods that check different things about the value, like
    // equality to other values, truthiness, definedness, etc. So you call expect on 
    // the value, then tell it how to check to see if it's what you wanted.
    expect(true===true).toBeTruthy();
})
```

