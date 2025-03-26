---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/bot-build-and-load/"}
---


#  Build and Code Load the bots

## Links and useful resources 

- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)

 
- ***[[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|Project index: differential-steering-bot]]*** 

## Concept summary and connections


- Bots partial assembly, loading the code 
- Checking state machine implementations 
- Writing a pwm motor class 

## Lesson Content

### Assembling what we have

We have the two updated designs *mostly* printed out (short some wheels and axles, which will print today). Let's get them assembled as much as possible, inserting bearings and attaching motors and stuff. Don't permanently attach any electronics yet - we may need to load these things up on a shop tool in order to make adjustments to holes for things to fit properly. Once it's all fitted together, move on to the next phase of updating your code for the new drive system.

### Updating code for PWM-controlled DC motors

We need to update our bots so that they use the [[projects/school-fall-2024/engineering/lessons/tb6612fng-motor-driver-setup\|tb6612fng-motor-driver-setup]]. This will be different from the `ContinuousServo` class because we will be directly controlling the actual motor chip, and it'll take *three pins*: one for forward, one for reverse, and a PWM pin for speed. Here's the API it needs to present:

```c++
// File: motor_pwm.hpp
#ifndef MOTOR_PWM_HPP
#define MOTOR_PWM_HPP

/// This class implements a simple motor control scheme for a DC motor
// being driven by a TB6612fng dual h-bridge. You can configure the
// motor to be in normal or left-handed mode. In left-handed mode, it
// operates in reverse in order to allow you to use the same definition of
// forward for motors that are oriented in opposite directions (i.e. one on
// each side of a chassis to drive the wheels...). 
//
// Speed ranges from -1 to 1 as a floating point value. The direction of rotation
// is the sign of the number, and the magnitude is mapped from [0...1] -> [0...255].

class MotorPWM {
public:
    MotorPWM(int fwd_pin, int rev_pin, int speed_pwm_pin);
    // The new speed ranges from [-1 ... 1], with negative numbers indicating reverse direction from positive.
    void set_speed(float new_speed);
    
    // Set this motor to be "left-handed", meaning that its rotation is reversed from normal 
    void set_left_handed(bool is_left_handed);
};

#endif
```

Remember that you'll use this code as the basic *interface*, but your actual class will need to have some member variables to keep track of speed, pin numbers, and direction, and you'll have to write the *implementation* for each method in a `.cpp` file.


## Homework


- [x] #hw (engr) Write a class like the ContinuousServo, but for a PWM-controlled motor using the tb6612fng control board. It should implement the [MotorPWM API](https://school.ginosterous.com/projects/school-fall-2024/engineering/lessons/bot-build-and-load) from the lesson.  [[2025-03-25\|2025-03-25]]