---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/algorithm-bubble-sort/"}
---


#  Bubble Sort!

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


### Lesson-specific resource links

- [bubble sort blog post](https://medium.com/basecs/bubbling-up-with-bubble-sorts-3df5ac88e592) 

- ***[[projects/school-fall-2024/programming/lessons/algorithm-bubble-sort\|Project index: algorithm-bubble-sort]]*** 
## Concept summary and lesson


- sorting 
- bubble sort 
- efficiency and big-O notation 

Sorting is a major piece of computer science algorithm design. It's an incredibly versatile thing, and it's also not as easy as you'd think to get it done quickly. We're going to learn the simplest sorting algorithm I know today, and talk about how slow it is. It's called Bubble Sort.

It gets its name from the way the elements move through the list while you're sorting it (the biggest elements tend to bubble to the end of the list).

All sorting algorithms have a few things in common:
- They *always* sort things by comparing two at a time
- They always impose a new order on the results without changing the size of the lists

Here's the basic idea:
1. Start at the first element of the list, and look at the ordering of it and the next one.
2. If they're in the right order, move on to the next element.
3. If they're in the wrong order, swap them!
4. Now move to the next element of the list (don't skip any, even if it's the one you just swapped!)
5. Go to step 2 and repeat until you reach the end of the list
6. Go to step 1 and repeat, but stop one element farther from the end for each iteration until there are only two unsorted elements left, then sort them!

The algorithm will pick up the biggest element it has seen up until each point and carry it along until it either reaches the end of the unsorted items, or it reaches the end of the list. In either case, it drops the biggest item and starts over.

## Examples/demo

[Bubble Sort animation](https://yongdanielliang.github.io/animation/web/BubbleSortNew.html)

## Media resources

- [Youtube search for "sorting"](https://www.youtube.com/results?search_query=sorting) 
- [Youtube search for "bubble sort"](https://www.youtube.com/results?search_query=bubble%20sort) 
- [Youtube search for "efficiency and big-O notation"](https://www.youtube.com/results?search_query=efficiency%20and%20big-O%20notation) 


## Exercises

- [ ] #hw (programming) Implement the bubble sort algorithm as a function that will sort an array of numbers, least to greatest. [[2025-01-29\|2025-01-29]]
