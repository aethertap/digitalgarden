---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/language/lessons/outlining/"}
---


#  Outlining skills for essay-writing

- [[projects/school-fall-2024/language/language-kanban\|language-kanban]]
- [[projects/school-fall-2024/language/language-review\|language-review]]
- [CoGrader Essay Grading AI](https://v2.cograder.com/app)
- [[projects/school-fall-2024/language/book-report-rubric\|book-report-rubric]]
- [[projects/school-fall-2024/language/literature-2024\|literature-2024]]


## Topics


- Single paragraph outlines (SPO)
- Structure - The sentences in the paragraph are sequenced in a way that ensures clarity for the reader.
- Coherence - The sentences are logically connected with transition words that signal the connection, including indications of change of direction or emphasis.
- Unity: Every sentence supports the main idea of the paragraph.
- Well-constructed sentences: The sentences are grammatically correct and clear, and their types and structures vary (some simple, some compound or complex).

### Single Paragraph Outlines

A single paragraph outline is... an outline for a single paragraph (gasp.)

It's a simplification of the way we've been making outlines, and it should make it easier to organize your thoughts for longer pieces of writing. Here's the basic scheme:

1. Write a complete topic sentence. This is going to form the backbone of your paragraph and tell your reader what the main idea is, so it needs to be a good one.
2. Write **notes** for three or more supporting ideas. 
    1. Each note *must support the main idea* - if it doesn't, save that for another paragraph (or update your main idea to be what you really want to say).
    2. The notes are ***NOT*** complete sentences
    3. Each note can end up making *more than one sentence* in the final paragraph! Example: a direct quotation or example can be more than one sentence
3. Write a complete sentence for the *concluding* sentence of the paragraph. 
    1. It needs to reference the main idea, but it should not be a restatement of it.
    2. If you're trying to make a point, this is where that should be very clear.

### In-class: Make an outline

This will be an instructional paragaph, so we'll use a template that has a sequence of steps. When the paragraph is in a narrative or instructional style, it'll usually use time-sequencing style of transitions (first, then, next, finally).

#### 1. Identify topic, audience, and purpose

Topic: Control a robot's position
Audience: Beginner engineer/programmers (some knowledge of code and controlling electronics, but not much experience).
Purpose: A clear explanation of how to get accurate movement.

#### 2. Brainstorm ideas for supporting details (try for 10-15, so you can pick the best)

1. **Knowing current position**
2. speeds (max/min/controllability)
3. current speed
4. rotation
5. angular velocity
6. radians, degrees, angles
7. ***proportional control***
8. **error estimating (target - current)**
9. how to turn
10. ***incremental updates (only a little at a time)***
11. differential steering
12. PWM
13. stopping
14. motor shield (dual h-bridge)
15. current limitations (don't fry arduino)
16. voltages and limits

#### 3. Generate a topic sentence


***Topic sentence:***  
- Control a robot by keeping track of where it is versus where it needs to be, then generating controls to get closer.
- Controlling a robot is simply controlling its speed and direction for a long enough time to get to where it needs to go.
- When you're trying to control a robot's movement, it's important to know where it is compared to where you want it to be, and then find the best route to get there.
- Proportional control combined with a good estimate of the error can make it simple to find the right control signals to navigate a robot to a target position.

#### 4. Select and organize details into notes

***First (note)***: Prop.Ctrl = big moves for big errors, small for small.
***next* (note)**: PC needs error, use to know what to do. Err = Target - Current
***then: (note)***: incremental: each loop, only small change. faster for big errors
***finally: (note)***: when small enough error, set controls to stop.

#### 5. Generate a concluding sentence

Use a [[projects/school-fall-2024/language/language-review/subordinating-conjunctions\|subordinating conjunction]], [[projects/school-fall-2024/language/lessons/appositives\|appositive]], or a fresh [[projects/school-fall-2024/language/language-review/sentence-types\|sentence type]] to set it apart and wrap up the paragraph. It **might** be appropriate to use a concluding transition to start this sentence, but don't assume you need it. Use one if it makes things flow better.

***Conclusion sentence:*** 
- Controlling a robot with proportional inputs is simple, because the only things required are to know how big the gap is between the target and the current position, and then to make small changes in the right direction. **seems more like a topic sentence**
- By following these steps, it's simple to apply proportional control to get a robot to go where it needs to be.


### Example paragraph (this isn't part of the outline....)

Proportional control combined with a good estimate of the error can make it simple to find the right control signals to navigate a robot to a target position. Proportional control is a simple way to use the size of the error to decide how fast the control inputs should move the robot. Big errors should give big adjustments, and small errors should move more cautiously. The trickiest part is knowing what the error is. That can be found by subtracing the current position from the target position. Doing it in that order means that you can use the positive or negative sign of the result to decide which direction to go, and the size of the result to know how fast. On an Arduino plaform, the control program only runs for a very short time, but it runs over and over in a loop. That means that the controls can be adjusted quickly, but that it's important not to take too long to make a decision. When the error is less than some amount that seems good enough, set the controls to stop the robot. By folowing these steps, it's simple to apply proportional control to get a robot to go where it needs to be.



The next one will be a description of trade across Eurasia in the 1500s. In this case, we'll want to use varied transitions to introduce examples and other supporting details. Since this paragraph is not really telling a linear story or set of instructions, we'll be using more of the transitions related to clarifying, elaborating, and changing direction.

Topic: Trade in 1500s Eurasia
Audience:
Purpose:

***Ideas:***

1. 

***Topic Sentence:***
***Support (note)***:
***Support (note)***:
***Support: (note)***
***Support: (note)***
***Conclusion sentence:***


## Homework

- [ ] #hw (lang) Make a Single Paragraph Outline ([outlining lesson is here](https://school.ginosterous.com/projects/school-fall-2024/language/lessons/outlining)) that you can use in your essay [[2025-03-11\|2025-03-11]]
- [ ] #hw (lang) Make a single paragraph outline ([outlining lesson is here](https://school.ginosterous.com/projects/school-fall-2024/language/lessons/outlining)) that tries to persuade politicians that kids should be paid for their work at school. [[2025-03-11\|2025-03-11]]
