---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/line-following/"}
---


#  Line-following

## Links and useful resources 

- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)

 
- ***[[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|differential-steering-bot]]*** 

## How to follow a line

Today, we're going to start working on a control algorithm to make our bots actually drive along a line. In order to do that, we have to figure out how they can keep track of which way to turn and when to go forward. So, let's analyze the situation. There are four cases we'll start with (and two more that we'll add in a little while...):

1. The center sensor says it's on the line
2. The left sensor says it's on the line
3. The right sensor says it's on the line
4. None of the sensors detects the line

Note that, if *two* of the sensors detect the line, then one of them is going to be the center, so we can just treat that as being on the center for now. Since these are all of the possible states for our sensors to be in, and our bot's actions are controlled by the sensors, that means we need to handle these cases!

Right away, we need to have a specific action pre-planned to take for each case. Let's go through them one by one:

- **The center sensor detects the line:** If the center sensor detects the line, that means we're headed in the right direction. In that case, we should just drive forward.
- **The left sensor detects the line:** In this case, we're still *close* to the line, but we're a little off to the right. We should steer left, but still move mostly forward.
- **The right sensor detects the line:** This is just like the left sensor, but with the opposite steering direction
- **No sensors detect the line:** In this case, we need to start searching. The easiest thing to do would be just to pick a direction and spin in place until we find the line again. How about left?

That algorithm *should* get us line-following! It's that simple. But, I think we can do better. One thing we're not going to handle well at this point is sharp turns. If we only turn gradually when a side-sensor triggers, then a sharp turn will make us lose the line. Then, if the we start spinning in a particular direction, we could end up finding our own *back trail* instead of the track forward, and we'll go backward along the track! 

So, what separates that case from the behavior we want? Ideally, we'd spin in place *toward where the path leads* until we pick it up again. That means we probably want to **remember** the last sensor readings that actually saw the line. If the path turned sharply left, then we should see a moment when the left sensor was active just before we lose the trail. In that case, we'd want to turn to the left to find it again. The right side would work the same way. This will change the last step of our algorithm, making it into three parts:

- **No sensors detect the line, and the last side was left:** Stop moving forward, spin left until a sensor detects the line.
- **No sensors detect the line, and the last side was right:** Stop moving forward, spin right until a sensor detects the line
- **No sensors detect the line, and neither side saw it pass by:** Stop moving forward, choose a direction and spin until the line reappears. If it doesn't appear after a full revolution, just stop.

### Using a state machine

This might be a good chance to put your state machine knowledge to work: Our bot has eight states at this point: WaitToStart, Stop, Forward, VeerLeft, VeerRight, SpinLeft, SpinRight, Spin360. You can make a state machine class with state instances for each of those states, and define the transitions you need so that your bot will follow the line.

A few of the states probably require some explanation:

- **WaitToStart**: This is just here to give you time to get all of the wires plugged in before your bot starts trying to move. Start in this state, wait for a few seconds, then transition to the next state based on the sensor input
- **Stop**: A state with no exit. This is for when we have lost the line and want the bot to give up and wait for help
- **Spin360**: This is for when we've lost the line and we don't know which side to look on - just spin a full revolution and follow any line you find. It might be backwards, but what can you do?

### Managing states in c++

We want our `Robot` to be the state machine. It should have all of the states that it needs, and the state instances should just tell which one to change to when necessary. One complication in C++ is that memory is NOT freed up automatically - if you keep calling `new`, you'll run out. So, let's avoid that.

We can name and index our states using an  `enum`:

```c++
enum StateName {
    WaitToStart=0,
    DriveStraight,
    VeerLeft,
    VeerRight,
    SpinLeft,
    SpinRight,
    Spin,
    Stop,
    NumberOfStates
};
```

Then, those are just names for increasing integer counting numbers: For example, `WaitToStart` is 0, `VeerLeft` is 2, and the rest are numbered according to where they show up in the list. So now we can use them for indexes into an array of State objects:

```c++
class Robot {
public:

    State* my_states[NumberOfStates];
    StateName current_state;
    Robot() {
        this->setup();
    }

    void setup(){
        this->current_state = StateName::WaitToStart;
        my_states[WaitToStart] = new WaitToStartState(5000 /*delay*/);
        my_states[DriveStraight] = new DriveStraightState(0.3 /*speed*/);
        my_states[VeerLeft] = new VeerLeftState(0.1 /*turn rate*/);
        my_states[VeerRight] = new VeerRightState(0.1 /*turn rate*/);
        // ... do the rest of the states
    }

    void update() {
        StateName next_state = this->my_states[this->current_state]->update(this);
        if(next_state != this->current_state) {
            this->states[this->current_state]->leave();
            this->states[next_state]->enter();   
            this->current_state = next_state;
        }
    }
```

But, what are all of those `DoSomethingStates`? They would be subclasses of a `State` class that has a simple interface.

```c++
class State {
    // I want a function that will update the current state of my bot, and return the name of a new state if a change is needed.
    virtual StateName update(Robot*) = 0;
}

class WaitToStartState: public State {
public:
    int start_ms;
    int delay_ms;
    WaitToStartState(int delay_ms) {
        this->delay_ms = delay_ms;
        this->start_ms = -1;
    }        
    
    StateName update(Robot* _robot) {
        if(this->start_ms < 0) { // we haven't initialized it yet!
            start_ms = millis();
        }
        if(millis() - this->start_ms >= delay_ms) {
            return StateName::DriveStraight;
        } else {
            return StateName::WaitToStart;
        }
    }
}
```



## Homework

- [ ] #hw Do the homework tasks in [the line-following lesson](https://school.ginosterous.com/projects/school-fall-2024/engineering/lessons/line-following) [[2025-03-06\|2025-03-06]]

1. Write code to implement the simple 4-step steering algorithm from the lesson
2. Add code to keep track of which side the track was on when it was lost. You'll need to have a default direction to spin also, in case the side sensors just didn't pick it up at all.
3. Experiment with your bot's speed controls until you find the slowest speed you can use and still have reliable control.
4. Make a track with electrical tape and pieces of paper and try to get your bot to follow it. You'll want your bot to move *slowly* because it's very easy to lose the track at the speeds they've been moving.
