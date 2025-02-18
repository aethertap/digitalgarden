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

To get started on this, we're just going to make a key builder that has two stages. First, use your `digram_frequencies` function to pick the top two digrams from both the corpus and the cryptogram. We're working with short text here, so the hope is that at least these ones will be pretty good.

Use those two digrams to insert the first three or four mappings (there may be duplicate letters!) into the key, assuming that they correspond to each other. Later, we'll add some searching to this process, but for now we're just going to assume the first guess is right (how's that for confidence?).

After you have those inserted, use the `letter_frequencies` to fill in the rest of the mappings. Remember that you can't have two things that map to the same result, and you can't have one letter that maps to two different results! You'll need to keep track of which mappings already exist and filter them out of the running while you choose what to use next.

```typescript
let key = new Map();
let cipher_digram_freq = digram_frequencies(ciphertext);
let corpus_digram_freq = digram_frequencies(corpus);
// pick the biggest two from each
let cipher_mondo_digrams = map2hist(cipher_digram_freq) // this makes our sorted array
    .slice(0,2); // and this takes the first two elements out of it
let corpus_mondo_digrams = map2hist(corpus_digram_freq) // make the sorted array
    .slice(0,2); // get the first two elements
// We have the top two digrams from the ciphertext and the corpus now. They'll look something like
//   [["th",17],["es",15]] for the corpus, and [["xp", 5], ["qw", 3]] for the ciphertext.
//   Now you need to make a map that has entries like this in it: {'x'=>'t','p'=>'h','q'=>'e', 'w'=>'s'}.
//   We took each letter from the top digrams in the cryptogram and mapped it to the corresponding letter 
//   from the corpus. Here's one of them for example:
key.set(cipher_mondo_digrams[0][0], corpus_mondo_digrams[0][0]);
// Watch out! English has lots of double-letter digrams in it (like 'tt', 'ee', 'll'). For now, try 
//   to avoid using those in this part. They will be very handy later on though!
// Now, get the single letter frequencies (your job)
// Filter out the ones that are already defined
// Insert the rest of the single letter frequencies in order of best frequency match.
```

## Media resources

- [Youtube search for "digram matching for the most common letter pairs"](https://www.youtube.com/results?search_query=digram%20matching%20for%20the%20most%20common%20letter%20pairs) 
- [Youtube search for "picking out word fragments"](https://www.youtube.com/results?search_query=picking%20out%20word%20fragments) 


## Exercises

- [ ] #hw (programming) Write a function that uses *digram* frequency to find the most common letter pairs (maybe the top 5 sets) and assign those to their places, then use single letter frequencies to fill in the rest. [[2025-02-17\|2025-02-17]]
