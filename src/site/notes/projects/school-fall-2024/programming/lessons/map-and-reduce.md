---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/map-and-reduce/"}
---



[scheduled:: 2025-01-17] 

#  Map and Reduce

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


### Lesson-specific resource links

- [typescript array methods](https://www.c-sharpcorner.com/article/simplify-map-reduce-and-filter-in-typescript/) 

- ***[[projects/school-fall-2024/programming/lessons/array-operations\|Project index: array-operations]]*** 
## Concept summary and connections


- map and reduce in typescript 
- iterating over arrays 
- anonymous functions in typescript

## Examples

### Anonymous functions in typescript

An anonymous function is a piece of code that you can call like a function, but that doesn't have a name. We also call them "arrow functions" in typescript. They're very handy when used along with the map, reduce, and filter functions, because you can just give a quick result right in the function arguments. They are created like this:

`(name_of_an_arg, another_arg, some_arg_name) => do_somethign_with_the_args(name_of_an_arg, some_arg_name, another_arg)`
The important parts are: 
- A set of parentheses with argument names inside, just like a regular function declaration
- An "arrow": ` =>`
- An expression that generates a return value, ***OR*** a code block inside curly braces. 
    - if you use the curly braces, **you have to use the return keyword or it doesn't give you a return value!**
    - Without the curly braces, it treats the expression's result as the return value automatically (nice!)

### Map

What does `map` do? It lets you make a new array by calling a function on every element of another array:

`[1,2,3].map((x) => x*2)` gives `[2,4,6]` back! Pretty handy!

You can define a function to use it like this:

`let evensUpTo = (n)=>iota(n/2).map((x)=>x*2))`
`let oddsUpTo = (n)=>iota(n/2).map((x)=>x*2+1))`

### Reduce
Reduce lets you gobble up all of the values in an array. You make a function that takes two values and returns the combination, then give `reduce` a starting value, and it will call your function on the current result and the next new item from the array until it runs out of stuff. You can use it to do things like add up all the numbers in an array:

`let add=(a,b)=>a+b`
`[1,2,3].reduce(add, 0)` would call your function like this: `add(add(add(0,1),2),3)`, which would give `6` as the result.

### Filter
Filter lets you decide who lives and dies, in an array. You make a function that returns true or false, and filter calls it on every element in the array. The return value is a new array that only has elements that passed the test (your function returned true):

`[1,2,3,4,5,6].filter(is_even)` gives `[2,4,6]` if `is_even` can check whether a number is even...

## Media resources

- [Youtube search for "map and reduce in typescript"](https://www.youtube.com/results?search_query=map%20and%20reduce%20in%20typescript) 
- [Youtube search for "iterating over arrays"](https://www.youtube.com/results?search_query=iterating%20over%20arrays) 


## Exercises

- [ ] #hw (programming) Use iota and map to create an array of all of the squares up to the square of the argument provided. [[2025-01-20\|2025-01-20]]
