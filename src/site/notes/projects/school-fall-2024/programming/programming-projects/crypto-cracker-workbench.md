---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/programming-projects/crypto-cracker-workbench/"}
---


# The classical crypto cracking workbench

We're going to make a fun little tool to help with cracking cryptograms and classical ciphers. 

## Simple substitution ciphers (the usual cryptogram)

- Letter frequency analysis
- n-gram frequency analysis
- interactive decryption key builder

### Lessons

- [[projects/school-fall-2024/programming/lessons/histogram-matching\|histogram-matching]]
- [[projects/school-fall-2024/programming/lessons/cryptogram-cracking\|cryptogram-cracking]]
- [[projects/school-fall-2024/programming/lessons/digraph-analysis\|digraph-analysis]]
- [[projects/school-fall-2024/programming/lessons/more-arrays-and-loops\|more-arrays-and-loops]]

## Polyalphabetic ciphers

This family of ciphers encrypts characters with more than one possible substitution. Sometimes it's because the cipher works on blocks of characters at a time (e.g. [[playfair-cipher\|playfair-cipher]]), and sometimes it's just literally a new key for every letter (viginere cipher). These are harder to break by hand, but we'll develop some tools to help with the process.


## Transposition ciphers

Transposition ciphers are different because they don't actually substitute new letters at all, they just shuffle the original letters around. This is going to take a completely different approach! We may or may not get to this before the end of the year.

