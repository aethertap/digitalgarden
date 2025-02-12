---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/cryptograms-using-digrams/"}
---


#  Using Digrams to help crack cryptograms

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


- ***[[projects/school-fall-2024/programming/programming-projects/crypto-cracker-workbench\|Project index: crypto-cracker-workbench]]*** 

- digram matching for the most common letter pairs 
- picking out word fragments 
- heuristic search

## Using our digram analyzer

So, we've got the single-letter frequency matcher working, but it's still giving us garbage! Sometimes there are some hints of words in there, but mostly it's just gibberish. Today we're going to use the digrams to try to improve this situation.

The nice thing about digrams is that there are WAY MORE of them! That means that the number of valid pairs is kind of small compared to the number of all possible pairs, and that lets us do a couple of nice tricks:

- First, we can preload our crypto key map with the most likely letters according to the digrams. That means things like th, he, it, is, ss, ll, tt that show up all over the place will fill in several of our letters with really good possibilities.
- Second, there are a lot of pairings that just *don't ever happen* - stuff like xq and wv. It turns out that the digram frequencies give us a lot more usable info than the single letter frequencies, but they don't generally cover all of the cases.

So, our end-game cracking tool is going to work on this problem a letter at a time. First, we use digrams to pick out pairs of letters that are very likely to be correct. Then, we start trying out single-letters to fill in the gaps, using a few tests for each letter to make sure it fits with the map we have so far.

Ultimately we're going to be making something that performs a *search* through the possible crypto keys, trying to find the one that makes output that looks like english text. Each step along the way, we'll have a key that represents our best guess so far, and we'll have a *score* for each key that's based on how good we think it is so far. We'll always work on the key that has the best score, and by doing that we can avoid even checking *almost all of the keys*. That's a good thing, because there are $26!$ possibilities! Our program would never finish if we had to look at each one...

This kind of algorithm is called *heuristic search*. A "heuristic" is kind of a quick way to gauge the quality of something, and a search just means we're looking through a lot of stuff to find what we want. The heuristic here is our answer to the question, "How likely is it that these substitutions could output real english?" We'll make a function that answers that question with a number, and we'll use that number to decide which key we should try next.

Every step of the way, we have a lot of choices for how we could assign a letter substitution. Our job will be to pick the ones that are likely to be the best and pursue them, but we don't want to forget our other options in case our guess wasn't very good. That's where the "search" part comes in. We're going to make all of our possible key maps "get in line," and then we'll take one off the front of the line, update it, and put it back in line, over and over again, until we have a good key. If we keep the line sorted by score, then we should be able to find a good key!

### What we're doing today

Today's project is just to build the two-step letter substituter. We want to get the top few entries from our digram analysis and use those to start our solution, then we want to fill in the gaps using the single letter frequencies. That means we'll have to check to make sure we don't add any pairs that conflict, which means that we should *remove the ones we already assigned* (from both the cryptogam and the corpus) before we call the key builder function.

We're going to add a couple of new functions to do this:

```typescript
function add_key_letter(key:Map<string,string>, map_from:string, map_to:string, from_array:any[], to_array:any[]):Map<string,string>{}

```

## Media resources

- [Youtube search for "digram matching for the most common letter pairs"](https://www.youtube.com/results?search_query=digram%20matching%20for%20the%20most%20common%20letter%20pairs) 
- [Youtube search for "picking out word fragments"](https://www.youtube.com/results?search_query=picking%20out%20word%20fragments) 


## Exercises

- [ ] #hw (programming) Write a function that uses *digram* frequency to find the most common letter pairs (maybe the top 5 sets) and assign those to their places, then use single letter frequencies to fill in the rest. [[2025-02-17\|2025-02-17]]
