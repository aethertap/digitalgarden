---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/engineering/lessons/implementing-state-machines-cpp/"}
---


#  Chassis design review, state machines in C++

## Links and useful resources 

- (https://docs.arduino.cc/language-reference/)
- [OnShape](https://cad.onshape.com)
- [How To Mechatronics](https://howtomechatronics.com)
- [Thingiverse](https://thingiverse.com)

 
- ***[[projects/school-fall-2024/engineering/engineering-projects/differential-steering-bot\|Project index: differential-steering-bot]]*** 

## Concept summary and connections


- How to structure c++ projects 
- Implementing state machines in C++ 

## Lesson Content

In C++, write a state machine to process Helldivers 2 Strategem codes. First, write the state machine as a simple switch statement so that you can watch to see how it runs, then update it to use the object-per-state strategy.

### A simple switch statement

Here's the implementation we did in class, by writing simultaneously into the same code buffer from three different editors. Some things are a bit crazy...

However, it shows how a simple state machine deals with state transitions. First, we take care of including the libraries we'll need (strings and input/output). The `get_code` function is a convenience to make it simpler to prompt the user for a strategem code letter. In this case, we're looking for the code for the 500kg bomb, which is `wdsss` ($\uparrow \rightarrow \downarrow\downarrow\downarrow$). 

```c++
#include<iostream>
#include<string>
using namespace std;

// purpose: to determine whether the user can type a strategem code correctly. The code will be wdsss (500kg bomb).
// Future work: jump pack: swwsw
// konichiwa

string get_code() {
    string result;
    cout << "Enter strategem letter (ONE LETTER, yes, ***ONE***): ";
    cin >> result;
    return result;
}

```

Next, we have to define the set of states we can be in at any given time. These are just `enum` values, meaning that they're just symbolic names for integers. The `Init` state is zero,  and they count up from there. Note, anything that has a `one` at the end should be read as "W - one" or " D - one", not as a word. The Finished, Error, and Kablooey states are special in that they have a side-effect or they cause the function to return. The rest are just transitional, meant to keep track of where we are in the sequence. A better naming scheme for these probably would have been to follow the letters of the code that have been typed out so far: w, wd, wds, wdss, finished.
```c++

enum States {
    Init,
    Wone,
    Done,
    Sone,
    Stwo,
    Sthree,
    Kablooey,
    Finished,
    Error,
    NumStates
};

```

We created an array of names for our states so that we can print them out easily.
```c++

string state_name(States s) {
    string names[] = {
        "Init",
        "Wone",
        "Done",
        "Sone",
        "Stwo",
        "Sthree",
        "Kablooey",
        "Finished",
        "Error",
        "NumStates"
    };
    return names[s];
}
```

This function was discovered from the body of each state. All of the main states followed the pattern of simply getting a code letter and checking it against what was expected, then switching to the next one or to the error state. This function just makes that into one line.
```c++
States expecting(string expected, States success, States failure = States::Error) {
    string code = get_code();
    if(code != expected) {
        return failure;
    } else {
        return success;
    }
}
```

And we at last arrive at the actual state machine. The things that define this style of state machine are all present:
- All of the data is *right there in the same function*
- The entire state machine is encoded as a switch statement in a loop, and all it does is cycle through the states in the order we defined based on input
- The states themselves are very simple. They don't have any logic or cleanup for entry and exit, and they don't have any attached data.
```c++
void state_machine() {
    States current_state = States::Init;
    string last_code = "";
    while(current_state != States::Finished) {
        cout << "Entering state " << state_name(current_state) << endl;
        switch(current_state) {
            case States::Init:
                current_state = expecting("w", States::Done);
                break;
            case States::Done:
                current_state = expecting("d",States::Sone);
                break;
            case States::Error:
                cout << "Error! That is the wrong code!! YOU DIED! Pls retry, how can you retry if you are dead? YOU CAN'T omgoodness. Dern" << endl;
                current_state = States::Finished;
                break;
            case States::Sone:
                current_state = expecting("s", States::Stwo);
                break;
            case States::Stwo:
                current_state = expecting("s", States::Sthree);
                break;
            case States::Sthree:
                current_state = expecting("s", States::Kablooey);
                break;
            case States::Kablooey:
                cout << "Kaboom" << endl;
                return;
            case States::Finished:
                cout << "Mission Over. State machine exiting." << endl;
                return;
            default:
                cout << "whoops, I quit." << endl;
                return;
        }
    }
}

int main() {
    cout << "Enter strategem code, ONE LETTER AT A TIME!" << endl;
    state_machine();
    return 0;
}
```

### Now Classify it, please.

The state machine switch statement is a useful pattern for very simple machines, but it breaks down when your states start to manage more data. When that happens, we can switch to using a class hierarchy.



## Media resources

- [Youtube search for "How to structure c++ projects"](https://www.youtube.com/results?search_query=How%20to%20structure%20c++%20projects) 
- [Youtube search for "Implementing state machines in C++"](https://www.youtube.com/results?search_query=Implementing%20state%20machines%20in%20C++) 

## Homework

- [ ] #hw Finish implementing a simple state machine to control your robot's movement. [Example code and lesson link](https://school.ginosterous.com/projects/school-fall-2024/engineering/lessons/implementing-state-machines-cpp) [[2025-03-18\|2025-03-18]]
- [ ] #hw Export and slice chassis models, get parts laid out on a build plate ready to print [[2025-03-13\|2025-03-13]]
- [ ] #hw Create a simple state machine for the robot in C++ using classes for `StateMachine`, `State`, and all of the particular states you can be in. [[2025-03-18\|2025-03-18]]
