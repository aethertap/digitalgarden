---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/photogate-and-robot/"}
---


#  Protogate final class and Robot revival

## Links and useful resources 

- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)


### Lesson-specific resource links

- [op-amp differential amplifier](https://www.electronics-tutorials.ws/opamp/opamp_7.html) 
- [stackexchange dual-edge-detector](https://electronics.stackexchange.com/questions/270894/dual-edge-detector) 
- [arduino attachInterrupt](https://www.arduino.cc/reference/cs/language/functions/external-interrupts/attachinterrupt/) 
 
- ***[[projects/school-fall-2024/engineering/engineering-projects/photo-gate-project\|Project index: photo-gate-project]]*** 
- ***[[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|Project index: differential steering robot]]*** 

## Concept summary and connections


- edge-detection in code 
- edge-detection circuit 
- differential amplifier review 
- edge-to-glitch detector 
- integer overflow 
- millis vs micros 
- differential steering math 

## Lesson Content

Edge-detection: when you have a signal and you only want to notice when it **changes**, you're doing *edge detection*. We can do this in software or in hardware.

The key in either case is that you have to have at least a brief period during which you can compare *what it was before* to *what it is now*. That means you need some kind of **memory** of the value, at least for a brief instant.

In code, this is simple. Just make a variable to hold the previous value of your sensor, and compare it to the newly-read value **before** you update the stored version:

```c
bool beam_is_broken = false;

void loop() {
    bool beam_status = digitalRead(BEAM_PIN);
    if(beam_status != beam_is_broken) { // a change happened!
        Serial.print("Beam state changed to ");
        Serial.print(beam_status);
        Serial.print(", timestamp: ");
        Serial.println(millis());
    }
    beam_is_broken = beam_status;
}
```

In hardware, you need some way to compare the old with the new. One such way is with a *differential amplifier*. A differential amplifier is an op-amp circuit that amplifies the *difference* between its inputs. By wiring it so that the difference will have a momentary spike when the input signal changes, the op-amp can give you a spike whenever a change happens. 

### Using Interrupts

Most microcontrollers have a feature called *interrupts*, which lets you tell the microcontroller to watch a pin and let you know when it changes automatically. In arduino, this is done with the [attachInterrupt](https://www.arduino.cc/reference/cs/language/functions/external-interrupts/attachinterrupt/) function:

This example will toggle the output LED whenever the input on pin 2 *changes* (either rising or falling edge).

```c
const byte ledPin = 13;
const byte interruptPin = 2;
volatile byte state = LOW;

void setup() {
  pinMode(ledPin, OUTPUT);
  
  // INPUT_PULLUP attaches an internal 20k pull-up resistor to the input pin so 
  // that it is HIGH when there is no connection on the attached circuit.
  pinMode(interruptPin, INPUT_PULLUP);
  
  // digitalPinToInterrupt is a helper function to make sure the pin number you
  // want is actually the right one for an interrupt. Digital pin numbers don't 
  // necessarily match interrupt pin numbers, so you have to use this mapping to 
  // make sure you're actually monitoring the pin you have your wires connected to.
  attachInterrupt(digitalPinToInterrupt(interruptPin), blink, CHANGE);
}

// Notice that loop doesn't do anything with the interruptPin at all! The arduino
// itself takes care of calling the ISR when an event happens. You can use the ISR
// to change some global data if you want so that loop can be aware of the state
// of things, or you can just do something directly in the ISR. In this case, the ISR
// controls the state variable, which the loop function uses to decide whether to 
// turn the LED on or off.
void loop() {
  digitalWrite(ledPin, state);
}

// blink is the Interrupt Service Routine (ISR) for this example. It will be called
// whenever the interrupt gets triggered, which in this case happens whenever the
// value on interruptPin **changes**
void blink() {
  state = !state;
}
```



## Media resources

- [Youtube search for "edge-detection in code"](https://www.youtube.com/results?search_query=edge-detection%20in%20code) 
- [Youtube search for "edge-detection circuit"](https://www.youtube.com/results?search_query=edge-detection%20circuit) 
- [Youtube search for "differential amplifier review"](https://www.youtube.com/results?search_query=differential%20amplifier%20review) 
- [Youtube search for "edge-to-glitch detector"](https://www.youtube.com/results?search_query=edge-to-glitch%20detector) 
- [Youtube search for "integer overflow"](https://www.youtube.com/results?search_query=integer%20overflow) 
- [Youtube search for "millis vs micros"](https://www.youtube.com/results?search_query=millis%20vs%20micros) 
- [Youtube search for "differential steering math"](https://www.youtube.com/results?search_query=differential%20steering%20math) 

## Practice


- What is the turning radius for a robot with wheels 10cm apart if one wheel goes 4 cm while the other goes 6 cm?
- How far would the robot you built move if both drive wheels moved forward exactly one full revolution?
- How long (in seconds) would it take for an 8-bit milliseconds timer to overflow back to zero?