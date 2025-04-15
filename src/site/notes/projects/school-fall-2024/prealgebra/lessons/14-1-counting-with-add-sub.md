---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/prealgebra/lessons/14-1-counting-with-add-sub/"}
---


#  14.1 - Counting with Addition and Subtraction

## Links and useful resources 

- [[projects/school-fall-2024/prealgebra/prealgebra-gr7\|gr7's Prealgebra Course Outline START HERE<<<]]
- [AoPS Online Textbook](https://artofproblemsolving.com/ebooks/prealgebra-ebook/c0toc)
- [IXL Grade 7 index](https://www.ixl.com/math/grade-7)
- [IXL Grade 8 index](https://www.ixl.com/math/grade-8)
- [AoPS Alcumus](https://artofproblemsolving.com/teacher/students)
- [IXL prealgebra practice index](https://www.ixl.com/math/grade-7)
- [OpenSTAX Prealgebra-1 textbook](https://openstax.org/books/prealgebra-2e/pages/1-introduction)

## Concept summary and lesson


- Fencepost errors and asking, "How many do I need to *remove*?" 
- For counting: Convert the list into the counting numbers, using the same operation for all elements. 

### Converting a list of numbers into the counting numbers

Whenever you're asked to count something that follows a pattern, the easiest way to make sure you get it right is to convert it into the counting numbers. In order to do that, you first need to write out some of the list of things. For example:
- How many multiples of six are there between 15 and 97?

First, we need to see what kind of list we have, so we write the first few terms and the last one:

The complete list would be $\cancel{15}, \cancel{16}, \cancel{17}, 18, \cancel{19}, \dots, 24, \dots, \cancel{95}, 96, \cancel{97}$. So, if we write the list without all of the invalid items (non-multiples of 6), we get:

$18, 24, 30, ..., 96$

That list gives us the basic shape of what we're looking at. Now, we need to convert it into the counting numbers. We have two problems:
1. The list doesn't start with 1
2. The numbers aren't adjacent to each other.

Our strategy is this: **Do the same things to every element in the list, so that we end up with the same number of things, but they've turned into the counting numbers**.

We need to solve both of those problems, but it will be easier one way than the other. So, what could we do?

- Divide the whole list by 6 to shrink it down to the counting numbers, but starting at 3
    - It's easy to then shift the list down to start at one by just subtracting two from each thing
- Subtract 17, so that it starts with 1, but then we have 1, 7, 13, ... It's not really obvious what we'd do next if we started out this way, right? Those numbers don't have any common factors we could divide out...

Let's divide by 6:

$$
\frac{18}{6}, \frac{24}{6}, \frac{30}{6}, \dots, \frac{96}{6} = 3, 4, 5, \dots 16
$$
Now we have $3, 4, 5, \dots, 15, 16$. We can just subtract two from each item:

$$
(3-2), (4-2), (5-2), \dots, (16-2) = 1,2,3,\dots,14
$$
Now we have the counting numbers! So, there are 14 items, which means there are 14 multiples of 6 between 15 and 97!

### Weird stuff

There are an unlimited number of weird countable things out there. Figuring out how to count them will always take some careful thought, some experimentation, and writing down some ideas. Sometimes, you'll want to count them in groups because you can use a trick for just part of the list at a time. Just remember this: As long as you don't change the number of things in your list, you can do **anything** on the way to transforming it to the counting numbers!

Whatever you think of is valid as long as you keep track of all of the list items.

## Guided practice

- [ ] How many numbers are in the list $9,  10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27$? 
    - We could also ask this problem as “How many numbers are there between 9 and 27 inclusive?”
- [ ] Given two integers $a$ and $b$, with $b > a$, find a formula for how many integers there are between $a$ and $b$ inclusive. (Remember, inclusive means that we include $a$ and $b$ in our count.)   
- [ ] How many multiples of 4 are between 25 and 101?   
- [ ] (a) How many multiples of 10 are between 9 and 101?  (b) How many multiples of 10 are between 11 and 103?  (c) We know that $(101-9) = (103-11) = 92$, so shouldn’t your answers to (a) and (b) be the same? Why aren’t they?   
- [ ] At Brown High School, there are 12 players on the basketball team. All of the players are taking at least one foreign language class. The school offers only Spanish and French as its foreign language classes. 8 of the players are taking Spanish and 5 of the players are taking both languages. How many players are taking French?  


## Homework

- [x] #hw (math) (gr7) 14.1 Counting with Addition and Subtraction (p. 510) [[2025-04-09\|2025-04-09]]
