---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/photogate-review-and-robot-programming/"}
---


#  Photogate review and bot programming

## Links and useful resources 

- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)


> To the optimist, the glass is half full.   
> To the pessimist, the glass is half empty.   
> ​To the engineer, the glass is twice as big as it needs to be.

> Normal people believe that if it ain't broke, don't fix it.   
> Engineers believe that if it ain't broke, it doesn't have enough features yet.


### Lesson-specific resource links

- [Adafruit MPU6050 page](https://www.adafruit.com/product/3886) 
- [I2C serial protocol](https://docs.arduino.cc/learn/communication/wire/) 
 
- ***[[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|Project index: differential-steering-bot]]*** 

## Concept summary and connections


- Review the designs for the photogates 
- Check the repairs on the broken bot 
- main topic: turning radius with a differential steering bot 
- Using 6 DOF MPU6050 for pose tracking 
- Tracking state variables as class members 

## Lesson Content

The robot has several things it needs to keep track of at each update:
- The sensor readings from three different IR obstacle sensors
- The target speed of each wheel
- (eventually) Its estimated pose, which means orientation and position
- (eventually) The last readings from the IMU

These things taken together represent the *state* of our robot, and they're going to be called *state variables*.

We will use the *encapsulation* property of object-oriented design to make the state variables easier to manage. That means we're going to make a single class called `Robot` that keeps track of all of those variables for itself, using code that's organized and easy to maintain.

Without encapsulation, we'd end up with a bunch of global variables and special-case functions to deal with the complexity of this robot. By putting them into a single `Robot`, we get the big benefit of treating the whole works as a single package. Just knowing where to put things is a big aid in programming - it gives you a chance to make good names for things that are automatically interpreted *relative to the class* instead of *globally to the whole program*. It also makes it easy to find the locations of any variables and functions, because it collects them all into a neat package.

Eventually, our `Robot` class will have some cool features: 
- It will have a good idea of where it is at all times
- It will be able to drive along a path that involves lines and arcs, without stopping at each turn
- It will be able to follow commands like "drive to 200,347" because it has an internal model of the world and knows where it is.

For today, it's enough to wrap the data we're using up with a class and make it drive in a straight line.

Today's goals for our bot:
- Get all of the wiring connected, including battery packs
- Test that it can drive in a straight line (make a program that drives forward for three seconds then quits)
- Write a `Robot` class with member variables for:
    - left wheel target speed
    - right wheel target speed
    - left sensor reading
    - center sensor reading
    - right sensor reading
- Add a method called `update(int dt_micros)` that uses the state varialbes to keep the motors going at the desired speed, and also updates the information from the three sensors.
- Add a method called `drive_straight(float speed)` that drives the bot forward or backward in a line. If the speed is -1.0, it should go backward at full speed. If the speed is 1.0, it should go forward at full speed. Otherwise, it should try to make its speed proportional to the requested value (0 should be stopped! remember how strange servo control is: 90 is the zero position!).
- Look back at our original robot code. We wrote a function called `map` that converted any number in the range $-1 \dots 1$ into a number in the range $0 \dots 180$. That's how we're going to want to control the motor speed here as well.

### Bonus if we have time

We have a few of [these](https://a.co/d/9SgeT5v) IMU 6050 sensor boards. They make it "easy" to track our orientation and acceleration, which we know from physics means we can use them to estimate our location with some math. They're a little bit complex to use, but if we have time today we'll take a look at what they can do.

The basic idea of an IMU is that it contains a device that can sense accelerations in three directions, and rotations around three axes. Some of them also have a three-axis magnetic field sensor that you can use to get an idea of your absolute orientation (basically a compass to read Earth's magnetic field). These don't have that, but we do have a few *different* boards with that feature.

When you use an IMU to keep track of your bot's pose, you end up measuring acceleration and rotation over and over again as quickly as possible. You then use the acceleration data to estimate your velocity change over that time, and *then* you use the average velocity over that time to estimate your position change. It's an error-prone process, but with a fast enough time step and a good sensor you can do pretty well at keeping track of where you are and which direction you're facing.

In order to implement that, we'll need to add several more state variables to our `Robot`:
- `long acceleration[3]` should hold the most recent three-axis acceleration values
- `long velocity[3]` should hold the current average velocity estimate
- `long position[3]` should hold the current estimate of our position, based on the accelerometer data
- `long orientation[3]` should hold our best estimate of our bot's orientation.

### Coordinate systems

We're used to thinking of the world as having a set coordinate system that's kind-of attached to the ground, and our bot just moves around on it. However, for this it's probably going to be more convenient to imagine our bot is the origin of the coordinate system, and the world is moving around under it. The practical meaning of that is that the acceleration and velocity data are all going to be relative to our bot, not absolute in the world (driving forward will always give us an acceleration in the Y direction, for example, instead of being different depending on which direction the bot is facing).


## Media resources

- [Youtube search for "Review the designs for the photogates"](https://www.youtube.com/results?search_query=Review%20the%20designs%20for%20the%20photogates) 
- [Youtube search for "Check the repairs on the broken bot"](https://www.youtube.com/results?search_query=Check%20the%20repairs%20on%20the%20broken%20bot) 
- [Youtube search for "main topic: turning radius with a differential steering bot"](https://www.youtube.com/results?search_query=main%20topic:%20turning%20radius%20with%20a%20differential%20steering%20bot) 
- [Youtube search for "Using 6 DOF MPU6050 for pose tracking"](https://www.youtube.com/results?search_query=Using%206%20DOF%20MPU6050%20for%20pose%20tracking) 
- [Youtube search for "Tracking state variables as class members"](https://www.youtube.com/results?search_query=Tracking%20state%20variables%20as%20class%20members) 

## Practice

- [x] #hw (engr) Write a `Robot` class to keep track of your bot's motor speeds and sensor values.  [[2025-01-30\|2025-01-30]]
- [x] #hw (engr) Write a `drive_straight(float speed)` function that will go full backward with -1.0, full forward with 1.0, and proportional speed for any value in between.  [[2025-01-30\|2025-01-30]]
