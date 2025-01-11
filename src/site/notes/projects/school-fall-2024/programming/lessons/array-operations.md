---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/array-operations/","tags":["gardenEntry"]}
---


# Week 3: Arrays
## How to do this

1. Go into your homework directory and run the command: `git clone https://github.com/aethertap/typescript-template hw3`
2. Enter the `hw3` directory and type `npm i`
3. Type `npm run br`
    1. If it prints a bunch of stuff then ends up with "It works." you're good to go.
    2. If there are problems, let me know.
4. The starting point for your program will be in `src/app.ts`, but you can add other files and import them as needed. For now, `app.ts` is probably all you'll need.

### Questions

1. How many elements does the array `let a:number[]=[1,2,3,4,5];` contain? What is the index of the first element? The last?
2. This piece of code is supposed to make an array of five numbers that count from 1 to 5. What's wrong with it? What does it *actually* do?
    ```typescript
	let a:number[] = [];
	for(i = 1; i <= 5; i = i + 1) {
		a[i] = i;
	}
```
3. Write a function `function sum_series(n:number):number` that takes a number as an argument and returns the sum of all of the integers from 1 up to the number. You can use any clever tricks you may know to do this.
