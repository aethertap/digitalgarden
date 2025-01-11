---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/programming-projects/triangle-of-stars/"}
---


# Week 1: Basics and for loops



## How to do this

1. Go into your homework directory and run the command: `git clone https://github.com/aethertap/typescript-template hw1`
2. Enter the `hw1` directory and type `npm i`
3. Type `npm run br`
    1. If it prints a bunch of stuff then ends up with "It works." you're good to go.
    2. If there are problems, let me know.
4. The starting point for your program will be in `src/app.ts`, but you can add other files and import them as needed. For now, `app.ts` is probably all you'll need.

### Notes

- Remember to `export` your functions so that they can be called in the tests
- Remember that a new line can only be inserted in a string by using the `\n` character (that is a BACKslash, not the one by the question mark!)

### Questions

1. What do these loops print?

```typescript
for(let i = 0; i < 10; i = i + 2) {
	console.log(i);
}
for(let i = 100; i >= 0; i = i - 7) {
	console.log(i);
}
for(let i = 1; i <= 10; i = i + 1) {
	console.log(i);
}
for(let i = 2; i < 100; i = i * 2) {
	console.log(i);
}
```

2. Write a function called `squares` to print the numbers from 1 to 10 and their squares:

```
	1	1
	2	4
	3	9
	...
	10	100
```

3. Write a function called `star_triangle` that generates a string that looks like the star triangle below, and returns it to the caller. The function should take one argument, which is the number of lines that the triangle should include (so star_triangle(3) would return a triangle with 1 star, 2 stars, and finally 3 stars).

```
	*
	**
	***
	****
	*****
	******
	*******
	********
	*********
	**********
```

Don't use ten printf statements; use two nested loops instead. You'll have to use braces around the body of the outer loop if it contains multiple statements:
```typescript 
	for(let i = 1; i <= 10; i = i + 1) {
		/* multiple statements */
		/* can go in here */
	}
```
(Hint: a string you hand to printf does not have to contain the newline character \n.)