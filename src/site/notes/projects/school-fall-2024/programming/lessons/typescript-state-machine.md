---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/typescript-state-machine/"}
---


#  State Machines in Typescript

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


## State machines in TypeScript

- ***[[projects/school-fall-2024/programming/programming-projects/tank-battle-game\|Project index: tank-battle-game]]*** 

Typescript class definitions are similar to c++, but there are a few significant differences:
- In typescript, instead of declaring a function `virtual`, it's called `abstract` and they aren't *quite* the same thing.
    - in c++, a `virtual` function is one that can be redefined by a subclass, and a `pure virtual` function (one that has `=0` after it) **must** be defined by a subclass
    - in typescript, all functions can be redefined by a subclass, and you use `abstract` to mark a function as being what you'd call `pure virtual` in c++.
- In typescript, method functions have to be defined in the class declaration itself. In c++, you have to put the function definitions into a separate file to prevent multiple definition errors.
- The type syntax is different, naturally
- You never have to worry about calling `delete` on anything in typescript, because it's a *garbage-collected* language: the system that runs your program takes care of cleaning up memory that you're no longer using.

With that in mind, let's make a typescript state machine today!

Here's a sketch of what it looks like with classes:

```typescript

// Just like in our differential steering robot state machine, the robot itself is
// the state machine. It passes the control structure to the different states so
// that they can control the movement and firing of the gun, and whatever other
// things the robot needs to do. If we end up with a lot of information in the
// Robot class (like keeping track of our position and plan), then we'll pass that
// into the states along with the API so that they're all working from the same
// data.

class Robot {
    constructor(init_state:string = "init") {
        this.current_state = init_state;
        this.states = {
            "init": new Init(),
        };
    }
    
    update(dt:number, api:TankAPI) {
        let new_state = this.states[current_state].update(dt,api);
        this.switchTo(new_state,api);
    }

    // When we switch to a new state, the new state might *also* want to switch in
    // order to make an epsilon transition. This is where that happens in a recursive
    // call to switchTo. switchTo looks for the special state name "no-change" to
    // indicate that it should do nothing, so don't name any of your states
    // "no-change"!

    swichTo(new_state_name: string,api:TankAPI) {
        if(new_state_name == "no-change") { 
        // if the state wants to stay active, 
        //this is the "new state" it should return.
           return;
        }
        this.states[this.current_state].leave(api); // leave the state we were in
        this.current_state = new_state_name; // update the state name
        let epsilon = this.states[new_state_name].enter(api); // enter the new state
        this.switchTo(epsilon,api); // implement the epsilon transition if there is one.
    }
    
    current_state: string
    states: {[key:string], State}
}

// State is an "abstract" class, meaning that it's declared so that you can never
// actually instantiate one. Instead, you have to make subclasses of it, and then
// you can instantiate *them*. This is just here to describe what *all* States can
// do.
// 
// 
// When you write these states, think of them as being the behaviors of your tank.
// Whenever it's in a particular state, it's *doing something particular to that
// state*. You might end up with more than one state machine! You could easily have
// one for driving and a separate one for fire-control, and maybe even a third for
// plan-setting. They all use the Robot as a place to store their information, and
// that's what lets them work together.

class State {
    // this is called for every input event or frame of the simulation.
    abstract update(dt:number, api: TankAPI):string;

    
    // The enter function can cause a state transition too, so that we can have
    // "epsilon" transitions. by default, it tells the state machine NOT to change
    // states immediately.
    enter(api: TankAPI):string {
        return "no-change";
    }
    
    leave(api: TankAPI) {
    }
}

// This is just an example of an Init state, yours will probably be very different.
// In this case, the Init state just makes sure the tank isn't moving and then
// returns. You'll likely want to have this state be the default "drive around
// hunting" state, or make an epsilon transition to that state by returning its
// name from the `enter` method.

class Init extends State {
    update(dt:number, api:TankAPI):string {
        // nothing to see here... For now, this class doesn't have anywhere to go,
        // so this function doesn't do anything. All we need to do is return the
        // "no-change" value to let the state machine know that it should keep
        // being in the Init state:
        return "no-change";
    }
    // When we enter the Init state, we should make sure to set all of the controls
    // of our tank to be stopped.
    enter(api: TankAPI) : string {
        let controls = api.getControls();
        controls.left_speed = 0;
        controls.right_speed = 0;
        controls.radar_turn = 0;
        controls.gun_turn = 0;
        controls.fire_gun = 0;
        api.setControls(controls);
        return "no-change";
    }

    // Nothing in particular to do when we leave, so we don't even have to write
    // that function! It has a default definition in the State class, so we'll just
    // skip it here.
}
```

You can also do a `switch`-style state machine in typescript, and it looks very similar to the one from [[projects/school-fall-2024/engineering/lessons/implementing-state-machines-cpp\|implementing-state-machines-cpp]], except that you can just use strings for the state names and skip the part about making the enum if you want. The same tradeoffs apply here as in c++.

## Quizzing your understanding

- What is the purpose of the `State` class in this setup? Why is it even there?
- When do you think you might want to have *more than one state machine* controlling your tank?
- When I say, "Each state is a behavior," what does that mean? Give some examples of "behaviors" that make sense here.

## Homework

- [ ] #hw (programming) Implement your driving in a square  navigation as a state machine in typescript. [Example code here](https://school.ginosterous.com/projects/school-fall-2024/programming/lessons/typescript-state-machine) [[2025-03-24\|2025-03-24]]
