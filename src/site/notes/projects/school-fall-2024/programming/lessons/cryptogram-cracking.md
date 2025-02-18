---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/cryptogram-cracking/"}
---


#  Cryptogram Cracking

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


- ***[[projects/school-fall-2024/programming/lessons/histogram-matching\|Project index: histogram-matching]]*** 
## Concept summary and lesson


- letter frequency analysis 
- bigram frequency analysis 

So far, we have made a bunch of functions that can give us *histograms* of the frequencies of the letters in pieces of text. However, there's a problem: It's hard to compare one histogram to another! Our corpus of text that we use for a model probably has thousands of characters in it, while the cryptogram probably only has dozens. That means the *actual numbers* in the two things are going to be nothing alike! One is going to be orders of magnitude larger than the other, and that makes it hard to line things up.

In order to make our lives easier, we're going to convert the histogram into a *probability distribution*. A probability distribution is just a collection of all possibilities, each of which has a certain chance of happening. Notice that I said **all possibilities** and **chance of happening**. That means that every number in a probability distribution is less than or equal to 1, **and** they all add up to 1.

Turning a histogram into a PDF (probability distribution function) is easy - just add up all of the terms in the histogram, then divide each one by the total. If you do that, you'll have a whole collection of fractions with a common denominator, all of which add up to exactly one!

This process is called *normalizing* the data - we scale it up or down so that we can make better comparisons. 

### Updating our crypto cracker

Now, instead of just aligning our character arrays by frequency, we're going to try to find the *best match* for each character mapping. We'll still want to start with sorted arrays, but instead of just picking the next element from the corpus each time, we'll keep our current ciphertext letter active until we find the corpus letter with the *closest* probability, and use that one as our substitution.

This is still not going to solve the cryptogram! However, it will get us a lot closer. This also 


## Media resources

- [Youtube search for "letter frequency analysis"](https://www.youtube.com/results?search_query=letter%20frequency%20analysis) 
- [Youtube search for "bigram frequency analysis"](https://www.youtube.com/results?search_query=bigram%20frequency%20analysis) 


## Exercises

- [x] #hw (programming) Write a function that turns your frequency histogram map into a probability distribution function [[2025-02-14\|2025-02-14]]
- [x] #hw (programming) Add comments for each function in your crypto library that explain what it's for, what it returns, and what each argument should be. The purpose of the comments is to make it easier for **you to use your own code** so make them descriptive! [[2025-02-14\|2025-02-14]]

