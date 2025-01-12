---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/programming-projects/types-and-comparisons/"}
---


# Assignment 2: types and stuff
## How to do this

1. Go into your homework directory and run the command: `git clone https://github.com/aethertap/typescript-template hw2`
2. Enter the `hw2` directory and type `npm i`
3. Type `npm run br`
    1. If it prints a bunch of stuff then ends up with "It works." you're good to go.
    2. If there are problems, let me know.
4. The starting point for your program will be in `src/app.ts`, but you can add other files and import them as needed. For now, `app.ts` is probably all you'll need.

### Questions


1. What would the equivalent code, using a while loop, be for the example
```typescript
	for(let i = 0; i < 10; i = i + 1) {
		console.log("i is ", i);
	}
```

2. What is the numeric value of the expression 3 < 4 ?

3. Under what conditions will this code print "water"?
```typescript
	if(T < 32) {
		console.log("ice");
	} else if(T < 212) {
		console.log("water");
	} else {
    	console.log("steam");
    }

```

4. What would this code print?
```typescript 
	int x = 3;
	if(x) {
		console.log("yes");
	} else {
    	console.log("no");
    }
```

5. (trick question) What would this code print?

```typescript
	int i;

	for(i = 0; i < 3; i = i + 1) {
		console.log("a");
		console.log("b");
	}

	console.log("c");
```

6. Write a function `is_binary(n:number):boolean` that checks to see whether every digit of the argument is either `1` or `0`.
