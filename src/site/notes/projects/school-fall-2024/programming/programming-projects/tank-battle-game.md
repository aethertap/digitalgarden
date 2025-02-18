---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/programming-projects/tank-battle-game/"}
---

[[projects/school-fall-2024/programming/programming-projects/tank-battle-resources\|tank-battle-resources]]
# Tank Battle Game

Okay, time to start our big project for the year now. We're going to work on a tank-battle game, where two players each get a small army of autonomous tanks, and they battle each other in an arena to see which one has better tactics.

We're going to use 
- [matter.js](https://brm.io/matter-js/) physics library to start with
- [quickjs](https://github.com/sebastianwessel/quickjs) javascript sandboxing runtime.
- maybe add the [p5.js](https://p5js.org/) rendering library if we need it

## Game concept

The ultimate end-state game will be a real-time 4X strategy in which your autonomous tank army tries to assert control over a large territory by forcing enemies out of it. The larger the territory, the more stuff you get in order to keep expanding and defending your borders.

The programmable tanks are the base mechanic. Each player gets to have a code base that controls the tanks, and a library of sensors and effectors to interact with the world. The tech tree will have improvements in all aspects, achievable by dominating a large enough territory to dedicate the required resources to research for the required amount of time.

## Tank control

Tanks are controlled by scripts written in typescript that are loaded as a Function (for now). A better alternative is in the SES hardened javascript package ([here's a link to the documentation, such as it is](https://github.com/endojs/endo/blob/master/packages/ses/docs/guide.md)). The tank update script is given two data structures - one that represents the control signals (including the currently-set signals from the last run), and one that has sensor data. The tank's code does its work, then returns an updated control structure.

The controls are simple:
- Left-side track speed
- Right-side track speed
- Gun turn deg per sec
- radar turn deg per sec

### Future modules

Tanks in the future will have many more modules that can be earned through powerups and tech tree advancements. Each of those will have some combination of extra controls and sensors that the code can access. They'll all be accessible by name, which ultimately will be something the user can define.


# Development Stages

## Tank on screen

- [x] Goal: Get one tank to draw itself on the screen
- [x] Goal: Get the tank to move around under control of the code
- Goal: Basic graphics that don't look terrible
- Goal: Deterministic replay
    - Need to make a fixed time step
    - Need to control the random number generator
- Goal: Modular controls and sensors
    - There is a Control and a Sensor base class
    - They each have direct access to the physics of the game world and the tank's body
    - Each sensor is updated just *before* the code runs for that iteration
    - Each control is updated just after the code runs for that iteration
    - Instances of these are responsible for building and parsing the controls and sensors portions of the update messages

## Hardened JS

The current best-looking option for running untrusted code is to use [hardened JS](https://hardenedjs.org). It *looks* like you can make a thing called a `Compartment` that gives you a functional JS environment that can do all of the normal things, but can't do anything to the outside world that you don't explicitly grant it permission to do.

So, if I want to use the import eval method described [here](https://2ality.com/2019/10/eval-via-import.html), I think all I have to do is create a container and harden it, then use that to do the eval.

- **Importing the ses module *creates* the function `lockdown`**. 
- ***Calling lockdown*** mutates the global environment and adds the `Compartment` constructor.

In order to use this, I need to make sure all of my scripts are loaded, then call `lockdown()` somewhere. After that call is made, there will be a `Compartment` constructor available.

Somehow, this works with the LSP in nvim, but I have no idea how.

### Scripting

- For some reason, I can't use import("some data url") from within any typescript file, or any file that was bundled by esbuild. I have to put the function outside of all of that and attach it to the global window object
- I can't even **call** the function without jumping through hoops, referencing it by window['load_script'] rather than just using its name.
- Need to resolve this somehow... but it's currently working for non-hardened scripting.

## Code editor on screen

- [x] use the [typescript sandbox](https://www.typescriptlang.org/dev/sandbox/) to give a decent code editor to work with.
- Connect the code edits to the tank's running code.

## Multiple tanks on-screen

- Goal: multiple tanks driving on the screen at the same time
- Goal: Collisions work with physical simulation of effects
## Tanks with turrets

- Goal: The turret has a graphical representation that can point in the right direction
- Requirement: The turret is a child of the tank, so it inherits the tank's rotation
- 
## Tanks can shoot

## Tanks have radar

## Energy and damage

## Keeping score

## Game UI

## Larger maps with different terrain types

## Transition to 2.5D graphics

## Enter a tank and play first-person in 3D

