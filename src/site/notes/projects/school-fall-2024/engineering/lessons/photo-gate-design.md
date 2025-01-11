---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/photo-gate-design/"}
---


#  Building a Photo Gate

## Links and useful resources 

- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)


### Lesson-specific resource links

- https://www.instructables.com/IR-Photogate/ 
- https://www.instructables.com/DIY-Photogate/ 
 
- ***[[projects/school-fall-2024/engineering/engineering-projects/photo-gate-project\|Project index: photo-gate-design]]***

## Concept summary and connections


- phototransistor 
- pull-up resistor 
- photodiode 
- errors and measurements
    - How to design for accuracy

## Examples

- [Phototransistor tutorial](https://www.youtube.com/watch?v=zx4OUXk0LSQ)
- [build a photogate for rpi](https://www.youtube.com/watch?v=KLeQTd1Ll_g)

### The Design Process

1. Concept
    1. Requirements/MVP
    2. Block-level design (just like writing code)
    3. Iterate
2. Prototype
3. iterate

## Media resources

- Youtube search for "phototransistor": https://www.youtube.com/results?search_query=phototransistor 
- Physics classroom search for "phototransistor": 
- Youtube search for "pull-up resistor": https://www.youtube.com/results?search_query=pull-up%20resistor 
- Physics classroom search for "pull-up resistor": 
- Youtube search for "photodiode": https://www.youtube.com/results?search_query=photodiode 
- Physics classroom search for "photodiode": 
- [USB-C breakout board](https://docs.cirkitdesigner.com/component/d424ebef-9fe4-449c-8a73-f6c1eb706f02/usb-c-breakout-board)
- 
## Guided practice

- What are our requirements?
- What is our concept?
- What's the minimum viable product?
- Can we make a prototype ***right now***?
    - Use the prototype for a while and gather new requirements
- Can we figure out a way to chain several gates together?
    - One data line
    - one device enable line for each gate
    - Use USB-c and breakout boards for the connections
    - Enable them in sequence using the microcontroller's code, in pin order
    - Mark each gate with its sequence position.
- When should we start the timer?
- Should we output absolute clock numbers or time-since-start? (or both?)

- [x] Problem: Draw a circuit with a pull-up resistor to measure state of photodiode.  
- [ ] #quiz What is the purpose of a pull-up or pull-down resistor? How does it work?
- [ ] #quiz Draw a circuit that uses a *pull-up* resistor to determine whether a switch is closed or open.
- [ ] #quiz Draw a circuit that uses a pull-down resistor to determine whether a switch is closed or open.
- [ ] #quiz Draw a circuit with a voltage divider.
- [ ] #quiz A circuit has +5v input, then a 1k$\Omega$ resistor, then a $9k \Omega$ resistor, then ground. What is the voltage between the resistors?
- [ ] #quiz What is the formula for finding voltage drops in a two-resistor voltage divider?
- [ ] #quiz What does a phototransistor do in a circuit?
- [ ] #quiz Design a voltage divider that will give you 3.5v from a 5v source.
- [ ] #quiz What is PWM and what are some common uses for it?
- [ ] #quiz Why would you choose to use a pull-up resistor configuration over a pull-down configuration in some designs?
- [ ] #quiz How does the engineering design process work? What are the main stages?