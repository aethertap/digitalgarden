---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/histogram-matching/"}
---


#  Histogram matching (sorta)

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


- ***[[projects/school-fall-2024/programming/lessons/digraph-analysis\|Project index: digraph-analysis]]*** 
## Concept summary and lesson


- Mapping one histogram to another 
- Test-decriptions 

The next thing we're going to do is create a simple function that uses our frequencies functions to make a "decent guess" at the key for decrypting a simple substitution cipher.

The decryption key we're going to make is another `Map` instance, but this time it's going to map letters to other letters. When we're done, we should be able to use `cipher_key_map.get(ciphertext_letter)` and it should return to us a *likely* plaintext letter. It won't be *exactly* right! This is a messy science, and we're going to add more features to our tools as we proceed with this big project, so when you get garbled text out of it, *that's okay*!

We're going to get the letter frequencies of regular English text (called the *model* here), and of our encrypted text (called the *ciphertext* here). Then we're going to sort them, so that the most frequently-used letters in each piece of text come first. Finally, we're going to pair them up, so that we have a `Map` with the `keys` being letters from our encrypted message, and the `values` being the most likely letter they should be transformed into.

Later, we'll make this interactive so that you can use it to *figure out* the right key string, but for now it's just going to give us its best first guess.

Here's how it needs to work:

- It should be a function that takes two strings as arguments. 
    - The first string is a *model* of text that should be similar to the decrypted version of our message
    - The second string is the *encrypted text*, or *ciphertext*
- Compute the `letter_frequencies` for each string and keep the results handy
- Turn each map into an array of letters, sorted by their *frequency* in the map
- Make a *new* map by running down the lengths of those two arrays and making the *ciphertext* array the key, and the *plaintext* array the value.
- Return the new Map.

### Sorting arrays in javascript

Javascript array sorting is notorious for being janky. In order to make sure we're getting the result we want, we need to make a special helper function that will convert our `Map` into an `Array` of `[string,number]` pairs. Then, we'll sort the array with a comparison function that only looks at the numbers.

First, get the pairs out of the map like this:

```typescript 
let letter_freq_pairs = Array.from(mymap.entries())
```

Next, we have to sort them. To do that, we can use the `Array.sort` method ([Array.sort documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)):

```typescript
Array.from(letter_freq_pairs)
    .sort((a,b)=>b[1]-a[1])
```

We pass the sort function our own special function to do the comparison *our way* (instead of turning them into strings and comparing the numbers as if they were words...). `sort` expects to give you two arguments (`a` and `b`), and it wants you to return:

- 0 if they are equal
- $<0$ if `a` should come before `b`
- $>0$ if `a` should come *after* `b`

By subtracting with `b-a`, we're getting the list sorted from greatest to least. Also, notice that we're only comparing the *count* part of the key/value pair we got from the map! That means we're sorting the *pairs*, but we're only looking at the *frequency* to make our ordering.

### Zip functions

It turns out that combining two arrays into an array of pairs (or something else similar) is a pretty common thing to want to do. We have a special name for a function that does that: `zip`. 

Take a look at this code and see if you can figure out how it works:

```typescript
function zip(a:number[], b:number[]):number[][] {
    return a.map((key,index) => [key, b[index]])
}
```

How could you use this function in our code project for today?

### Reducing one type to another

We got a list of pairs, but that's not really what we wanted. It would be nice if we could get a `Map`...

Here's another function you might find useful, try to figure out what it does:
- Here's the [Map.set method documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/set)
- Here's the [Array.reduce method documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)

```typescript
function make_map(pairs:string[][]):Map<string,string> {
    return pairs.reduce((mymap,pair) =>
            mymap.set(pair[0],pair[1]), 
        new Map())
}
    
```

## Media resources

- [Youtube search for "Mapping one histogram to another"](https://www.youtube.com/results?search_query=Mapping%20one%20histogram%20to%20another) 
- [Youtube search for "Test-decriptions"](https://www.youtube.com/results?search_query=Test-decriptions) 

## Exercises

- [ ] #hw (programming) Write a function that takes two strings as arguments. It should find the letter frequencies for each, then sort them in descending order, and finally return a Map that maps letters from the ciphertext into letters from the plaintext model. [[2025-02-10\|2025-02-10]]
