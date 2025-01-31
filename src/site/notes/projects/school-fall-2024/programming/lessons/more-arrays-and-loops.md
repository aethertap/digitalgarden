---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/more-arrays-and-loops/"}
---


#  More with arrays and loops

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


### Lesson-specific resource links

- [English language letter frequencies](https://www3.nd.edu/~busiforc/handouts/cryptography/letterfrequencies.html) 

- ***[[projects/school-fall-2024/programming/lessons/algorithm-bubble-sort\|Project index: algorithm-bubble-sort]]*** 
## Concept summary and lesson


- using maps to count things 
- histograms 
- letter frequencies in English 
- Solving cryptograms! 
- filtering and mapping to clean up your data 

## Examples/demo

We're going to build up some code that will help you solve future cryptogram problems, and maybe find your Christmas presents a bit more quickly. The first step in that process is to analyze the text to see how often each letter shows up (this is called the *frequency* of the letter). The easiest way to do that is to run through the string and increment an appropriate counter each time a letter is seen.

Our first crack at it might be to make a separate variable for every letter:

```typescript
function letter_frequency(text:string) {
    let a_freq = 0;
    let b_freq = 0;
    //... for the remaining letters...
    for(let character of string) {
        if(character === 'a') {
            a_freq += 1;
        } else if (character === 'b') {
            b_freq += 1;
        }
        // ... 24 more if cases
        else {
            console.log(`Skipping letter ${character}`);
        }
    }
}
```

That would work! But, how do we actually *use* its output? It can't return 26 things... maybe we put them in an array? But then which letter should go in which slot? I guess we could put them in the slot corresponding to their place in the alphabet:

```typescript
function letter_frequency(text:string):number[] {
    let a_freq = 0;
    let b_freq = 0;
    //... for the remaining letters...
    for(let character of string) {
        if(character === 'a') {
            a_freq += 1;
        } else if (character === 'b') {
            b_freq += 1;
        }
        // ... 24 more if cases
        else {
            console.log(`Skipping letter ${character}`);
        }
    }
    return [a_freq,b_freq,c_freq,/*... 23 more ... */];
}
```

Okay, we did it! That function would work. *But*... it's very gross. We have the set of things we can see **hard-coded** into the source, which means that anything that isn't part of the 26 letters of English alphabet just gets dropped. It's also only checking for lowercase letters, and if we want to change our minds later to allow things like numbers and spaces, we'll have to change not only the `letter_frequency` function, but also *everything that uses it* **AND** we need to decide exactly how to lay out the array we're returning so that all of our code knows what each slot represents. It would be so much better if we could just *include* that information as part of the return value.

### Using maps (objects)

[Typescript/javascript Map type documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)

It turns out, there is a data structure that's tailor-made for this job: the *map* (or *hashtable*, *hashmap*, *object*,... it has many names). This is a thing that keeps track of *pairs* of things: a name (called the *key*), and an associated value. You make a map (or object in typescript parlance) using the curly braces: `{}`.

Maps let you add keys and values for anything you like, so this is an ideal way to organize our program:

```typescript
function letter_frequency(text:string):Map<string,number> {
    let frequencies = new Map();
    //... for the remaining letters...
    for(let character of string) {
        // HA! this part is your homework...
    }
    return frequencies;
}
```

The body of the function is left as an exercise for the reader.... BUT it's really easy!

### Cleaning up data

One of the things you'll run into with this is that you have to filter out a lot of stuff you don't care about (things like punctuation, spaces, capitalized variants of letters, etc.). There are some nice shortcuts you can use with the `map` and `filter` functions that are part of the `Array` type.

Since we're working with strings, you'll have to use the `split` function to turn the string into an array of characters, like this: `let my_array = my_string.split('');`. If you want to put it back into a string, you can call `join` on the result: `let clean_string = my_array.join('');`.

Once you do that, you can do cool stuff:

```typescript
/// convert the string to all lowercase letters, and get rid of anything that isn't 
/// actually a letter (spaces, punctuation, numbers...)
function cleanup_string(text:string) : string {
    let my_array = string.split('');
    let cleaned_up = my_array.map((c)=>c.toLowerCase()).filter((c)=>c.match(/[a-z]/));
    return cleaned_up.join('');
}
```

## Media resources

- [Youtube search for "using maps to count things"](https://www.youtube.com/results?search_query=using%20maps%20to%20count%20things) 
- [Youtube search for "histograms"](https://www.youtube.com/results?search_query=histograms) 
- [Youtube search for "letter frequencies in English"](https://www.youtube.com/results?search_query=letter%20frequencies%20in%20English) 
- [Youtube search for "Solving cryptograms!"](https://www.youtube.com/results?search_query=Solving%20cryptograms!) 
- [Youtube search for "filtering and mapping to clean up your data"](https://www.youtube.com/results?search_query=filtering%20and%20mapping%20to%20clean%20up%20your%20data) 

## Exercises

- [ ] #hw (programming) Write a function that counts the instances of each character in the string argument, and returns a *Map* object of the results. Each key in the map should be a letter from the text, and the corresponding value should be the number of times that letter appeared in the text. The lesson page for this class is [here](https://school.ginosterous.com/projects/school-fall-2024/programming/lessons/more-arrays-and-loops) [[2025-02-03\|2025-02-03]]
