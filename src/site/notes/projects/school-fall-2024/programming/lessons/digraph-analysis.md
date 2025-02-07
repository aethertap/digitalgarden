---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/digraph-analysis/"}
---


#  Analyzing digram frequencies

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


- ***[[projects/school-fall-2024/programming/lessons/array-operations\|Project index: array-operations]]*** 
## Concept summary and lesson


- What is a digram / digraph / bigram? 
- frequencies of letter digrams in English text 
- Using maps to count digrams

## Examples/demo

Last time, we counted letters in a piece of text. That by itself is a pretty useful tool for breaking classical crypto, but we can do even better. It turns out that English has a much stronger pattern to it when you look at *pairs* of letters rather than single letters. If you look at this link: [digraph frequencies in English text](https://pi.math.cornell.edu/~mec/2003-2004/cryptography/subs/digraphs.html), you'll see an interesting thing: they only gave frequencies for the **22 most common** digrams, even though there are $26^2=676$ possible pairs. That's because they are ***very*** unevenly distributed!

That's good news for us as codebreakers, because it lets us rule out a lot of potential solutions based on how unlikely the digrams are. Say you've found 10 possible single-letter simple substitution cipher keys that give believable letter frequencies. That means that you can use any of them to "decipher" the message, but only one of them will actually be correct. You could then take a look at what the *digram frequencies* of each would give you, and you'll probably be able to rule out almost all of the bad ones immediately! That's because digrams are a lot more sparse than single letters, and the weird ones are often actually *impossible* to find in correct english text. 

So today we're going to write a function that will give us the count of all digrams in a piece of text. It's going to work 

## Media resources

- [Youtube search for "What is a digram?"](https://www.youtube.com/results?search_query=What%20is%20a%20digram?) 
- [Youtube search for "frequencies of letter digrams in English text"](https://www.youtube.com/results?search_query=frequencies%20of%20letter%20digrams%20in%20English%20text) 
- [Youtube search for "Using maps to count digrams"](https://www.youtube.com/results?search_query=Using%20maps%20to%20count%20digrams) 


## Exercises

- [x] #hw (programming) Add another function to your growing codebreaking library that works like the `letter_frequencies` function, but instead of counting individual letters it counts *pairs* of letters that show up next to each other. It should return a Map with keys for the digram, and values that hold the number of times the digram was seen in the sample. [[2025-02-05\|2025-02-05]]
