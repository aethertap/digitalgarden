---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/classy-tanks/"}
---


#  Classy Tanks

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


### Lesson-specific resource links

- [Separation of Concerns](https://en.wikipedia.org/wiki/Separation_of_concerns) 
- [Principle of least Privilege](https://en.wikipedia.org/wiki/Principle_of_least_privilege) 
- [Encapsulation](https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)) 

- ***[[projects/school-fall-2024/programming/programming-projects/tank-battle-game\|Project index: tank-battle-game]]*** 
## Concept summary and lesson


- structuring code for maintainability 
- API - the "surface" of your code 
- Principle of least privilege 
- Separation of concerns 

Yesterday in engineering, we finally got our robots to drive around and sense the line! We had two stages of work there though - first, you wrote code that wrangled low-level bits of the Arduino library to **just make it work**. Then, we switched to using our IRSensor classes. The IRSensor class is designed to *encapsulate* the complexity of the IR obstacle sensors we're using, turning their *avoidance* behavior into a *detection* behavior by inverting the sense of the output. 

By default, the sensors output LOW when nothing is detected, and HIGH when an obstacle is found. This makes sense if you're using them to avoid running into stuff. However, we're using them to see whether we're on a black line or not, and the sensor reports LOW when it's on the line and HIGH when it's off. That is very confusing when you're working on code that depends on it, and it leads to lots of errors. Our class *encapsulates* the sensor and provides a different interface that makes sense for line-following. It keeps track of the last sensor reading, and it maps the HIGH or LOW into two different functions: `obstacle_detected` and `on_line`. Now, we can use the sensor for both purposes, and we have functions that will *just tell us what we want to know*. They hide the complexity of working with the sensor behind a very simple, very small API.

This is both the *principle of least privilege* and the *separation of concerns* at work. 

- The principle of least privilege requires that you give users of your code as little power as possible to mess things up. In security, that means you limit their access to files, services, and other stuff to just the **bare essentials** that are absolutely required for the work being done. In this case, we're hiding the pin assignments, digitalWrite and digitalRead call structure, and the state of the sensor behind a *bare essential* interface that protects the rest of our code from user mistakes.
- *Separation of concerns* means that you divide your code into pieces that each focus as fully as possible on one limited *concern*. The concern in this case is determining whether we're on a line or not, and the `IRSensor` class handles that *and nothing else*. Anything that wants to know the state of "on-line-ness" has to ask the sensor, and the sensor doesn't do any extra stuff like making sandwiches or browsing funny cat videos.

### Maintainability

This is all done for one main reason: *maintainability* of code. Your brain works by keeping a few things at a time (usually 4-6) in working memory, and using its knowledge of relationships to figure things out about how those things work together. Becoming an expert in something **doesn't** mean that you can hold more in working memory, it means that the 4-6 things in your working memory *have a lot more information attached*. In other words, you have a mental data structure that holds a lot more stuff in just the right place so that you can actually think about it effectively because it's not taking up a whole memory slot.

Separation of concerns is basically a direct mapping of working memory limitations onto code. By wrapping up the IRSensor complexity into a class, we now can just think "what should my sensor do here" instead of "what should I write to pin 13, then how long do I need to delay to make sure it's enabled before I read from pin 12 and invert the bit because I'm looking for a line instead of an obstacle reflection...". The concept we get to work with matches the function it's meant to perform, and once that code is correct we probably won't ever have to dig into it again! It's just a simple concept now: Ask the sensor if we're on the line, and it will tell us yes or no.

So how does that help code maintenance? At this point, functions that *use* the sensor can put the *entire sensor* into a single working memory spot in your brain, and you can reason about the function overall without cluttering up your mind with pin assignments and stuff. So, if a bug is found, you're able to actually think about the function and fix it, rather than single-stepping through the byzantine labyrinth of low-level bit wrangling code.

How to principle of least privilege relate to this? We know that *nothing else in our code is allowed to mess with sensor stuff*! So if there's a problem with the sensor, it should be *in that particular piece of code*, not in some unrelated file somewhere else. We also know that the sensor should *not effect anything outside of its domain*, so we can rule it out for causing other problems. The reality is less strong than that, because we don't actually have a way to *prevent* other code from wrangling the pins and bits directly. However, if we are strict with ourselves and require all of our code to obey these principles, we defend ourselves from a lot of **very** difficult bugs.

The more you can apply these ideas to your code, the more complexity you'll be able to manage, and the less time you'll spend fixing extremely confusing problems. Spend extra time thinking about how you can write code that is *strict* about separation of concerns and principle of least privilege. It will pay off!

## Updates to the Tank API

Some changes:

- The code module you are making is now expected to have one function named `setup` that gets exported.
- The `setup` function is supposed to return an object that has an `update` method, which takes the `TankAPI` parameter (this is exactly like the `loop` function from before).
- The object should fully encapsulate all of the stuff it needs to work, because we'll be making **multiple copies** and they all need to play nicely. **No global variables please**

### Making closures and function pointers in typescript

Javascript and typescript have a litle bit of weirdness about the `this` object (big surprise, right?). `this` doesn't necessarily always refer to the class instance, it can also refer to the *function object itself*. So, when you create a closure inside a member method, your `this` pointer might change in mysterious ways, and everything will explode into flaming wreckage for no apparent reason. Here's how you can work around it: use the `bind` method, and make an alias for `this` that isn't a keyword.

### The `bind` method

You can tell a function what to use for the `this` pointer by *binding* it (this is **javascript** code, not typescript:

```javascript
function foo(n) {
    this.n = n;
}

let yada = { n:0 };
let foothis = foo.bind(yada);
foothis(100); // call the version with this bound to yada
console.log("yada.n = ", yada.n);

// prints out yada.n = 100
```

If you want to be able to pass a member method from your class around as a function that other code can call, just `bind` it:

```typescript
class Bar {
   donk(n:number) {
       this.n = n;
    }
    n:number
}
let b = new Bar();
callThisFunctionLater(Bar.donk.bind(b));
```

### Aliasing `this`

If you're in a member method and you want to return a closure that will need to have a way to talk back to your class, you should make an *alias* of `this` and use it in the closure. Otherwise, the closure will likely have its *own `this` pointer* and your code will not work!

```typescript
class Gar {
    some_member_method():()=>void {
        let self = this; // keep a copy of the 'this' pointer that I actually want
        return () => {
           self.do_a_method();
        }
    }
}
```

## Media resources

- [Youtube search for "structuring code for maintainability"](https://www.youtube.com/results?search_query=structuring%20code%20for%20maintainability) 
- [Youtube search for "API - the "surface" of your code"](https://www.youtube.com/results?search_query=API%20-%20the%20%22surface%22%20of%20your%20code) 
- [Youtube search for "Principle of least privilege"](https://www.youtube.com/results?search_query=Principle%20of%20least%20privilege) 
- [Youtube search for "Separation of concerns"](https://www.youtube.com/results?search_query=Separation%20of%20concerns) 

## Exercises

- [ ] #hw (programming) Do the code tasks under **Exercises** in our lesson at [classy-tanks](https://school.ginosterous.com/projects/school-fall-2024/programming/lessons/classy-tanks) [[2025-03-03\|2025-03-03]]

1. Wrap your current tank code up inside a class, so that each function is a method and all of the global variables are data members. 
2. Rename the `loop` function to be called `update` in the new class you made.
3. Make your setup function do nothing more than *create a tank instance and return it*.
