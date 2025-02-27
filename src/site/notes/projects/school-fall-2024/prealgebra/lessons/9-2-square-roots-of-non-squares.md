---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/prealgebra/lessons/9-2-square-roots-of-non-squares/"}
---


#  Square roots of non-squares

## Links and useful resources 

- [[projects/school-fall-2024/prealgebra/prealgebra-gr7\|gr7's Prealgebra Course Outline START HERE<<<]]
- [AoPS Online Textbook](https://artofproblemsolving.com/ebooks/prealgebra-ebook/c0toc)
- [IXL Grade 7 index](https://www.ixl.com/math/grade-7)
- [IXL Grade 8 index](https://www.ixl.com/math/grade-8)
- [AoPS Alcumus](https://artofproblemsolving.com/teacher/students)
- [IXL prealgebra practice index](https://www.ixl.com/math/grade-7)
- [OpenSTAX Prealgebra-1 textbook](https://openstax.org/books/prealgebra-2e/pages/1-introduction)

## Concept summary and lesson

- Any square number has even powers for all prime factors 
- Square root of any non-square number is irrational 
- Estimating square roots with upper and lower bounds 
- Comparing expressions with square roots 

## Worked examples

I use a couple of different strategies when I'm thinking about square root problems:
- Can I solve the problem by working with the squares of the terms (in other words, get rid fo the square roots entirely)?
- Does it help to look at it as a fractional exponent? $\sqrt{ x } = x^{1/2}$ 

Remember the rules of square roots:

- $\sqrt{ a\cdot b } = \sqrt{ a} \cdot \sqrt{ b }$
- $\sqrt{ a + b } \ne \sqrt{ a } + \sqrt{  b }$
- $(\sqrt{ x })^2  = x$
- $\sqrt{ x^2 } = x$

### Comparing square root expressions

Trying to determine which is larger when you're dealing with square root expressions can be tough, but you can often just square the terms and compare them that way. If $a>b$, then $a^2 > b^2$ (as long as $a,b \ge 0$). Since we've *defined* the square root to be just the positive value, we can safely use this property to compare terms involving square roots.

Example: Which is smaller, $5\sqrt{ 7 }$ or $7\sqrt{ 5 }$?

Solution: Square both and compare:

1. $(5\sqrt{ 7 })^2 = 25\times 7 = 175$
2. $(7\sqrt{ 5 })^2 = 49\times 5 = 245$
3. $245 > 175$, so $5\sqrt{ 7 }$ is the smaller term

### Estimating square roots by bounding above and below

You'll be asked to compute square roots to the nearest $n^{th}$ place value. The easiest way to do it is to figure out bounds, using your knowledge of numbers. You'll need to be creative in how you approach these kinds of problems because there isn't a formula to use.

Example: Estimate $\sqrt{ 2 }$ to the nearest tenth.

1. Start by just noticing some facts. Going for the nearest tenth means we'll have two digits in our answer, so we can use our knowledge of two-digit squares to help. Here are a few: $12^2 = 144$, $13^2 = 169$, $15^2 = 225$...
2. Look at the list, between 13 and 15 we cross over into the 200s, so 14 is a good candidate. $14^2=196$, which is very close to 200, and $1.4^2=1.96$
3. since $1.4^2 = 1.96$ and $1.5^2 = 2.25$, we can say that the closest value is 1.4, and we're done.

The things that make that work are:
- Knowing some squares (or being able to compute them quickly)
- Knowing how the decimal places work when you're multiplying (*two* of the digits will be after the decimal for a two-digit product, in other words)

### Fast mental math for squaring

Learning to square two-digit numbers rapidly is really useful, so here's how you do it:

We'll say we're computing $53^2$ for the example.

1. Find the nearest number with a zero in the ones-place digit. In this case, that's 50
2. What's the difference between that number and our real number? In this case, 3
3. Add and subtract that from our number to get two other numbers that are easy to multiply: in this case, 50 and 56
4. Multiply those numbers: $50\times 56 = 50\times 50 + 50 \times 6 = 2500 + 300 = 2800$
5. Add the *square* of the difference we got at the start. The difference was 3, so we add 9: $2800+9 = 2809$

Why does this work?

Let our number be $a$, and let the "adjustment" to make easy numbers be $b$. 

1. We're multiplying $(a+b)(a-b)=a^2 -b^2$.
2. Notice that if we add $b^2$ to that, we'll end up with just $a^2$
3. So no matter what numbers we use, as long as we follow that pattern it'll work. We could even do this trick with 3-digit numbers or more, as long as it's actually worth doing (the more digits, the more likely it is that the adjustment number itself is going to be a hassle to square).


## Media resources

- [Youtube search for "Any square number has even powers for all prime factors"](https://www.youtube.com/results?search_query=Any%20square%20number%20has%20even%20powers%20for%20all%20prime%20factors)  
- [Youtube search for "Square root of any non-square number is irrational"](https://www.youtube.com/results?search_query=Square%20root%20of%20any%20non-square%20number%20is%20irrational)  
- [Youtube search for "Estimating square roots with upper and lower bounds"](https://www.youtube.com/results?search_query=Estimating%20square%20roots%20with%20upper%20and%20lower%20bounds)  
- [Youtube search for "Comparing expressions with square roots"](https://www.youtube.com/results?search_query=Comparing%20expressions%20with%20square%20roots)  

## Guided practice


- [ ] Prove that the square root of a non-square is irrational  
- [ ] Which is larger, $7\sqrt{11}$ or $6\sqrt{15}$?  
- [ ] What is the largest integer less than $\sqrt{80,999,599}$?  
- [ ] How many intergers are between $\sqrt{13}$ and $\sqrt{131}$?  


## Homework


- [x] #hw (math) (gr7) 9.2 Square Roots of Non-square Integers (p. 358) [[2025-02-24\|2025-02-24]]
