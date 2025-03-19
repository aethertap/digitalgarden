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

Now, all we have to do is compile it. To do that, use either `clang` or `g++`. Those are both c++ language *compilers*, which means that they translate your source code into machine code.

### Using g++
```bash
# Compile the source cpp into an executable called state_machine
> g++ switch_state_machine.cpp -o state_machine
# We can run it like this:
> ./state_machine
```

### Using clang

```bash
# Compile the source cpp into an executable called state_machine
> clang++ switch_state_machine.cpp -o state_machine
# We can run it like this:
> ./state_machine
```

### Now Classify it, please.

The state machine switch statement is a useful pattern for very simple machines, but it breaks down when your states start to manage more data. When that happens, we can switch to using a class hierarchy.

```c++

// Today: We will write classes to implement the state machine for the jump pack strategem code.
// There are three *kinds* of class we need:
// - A StateMachine
// - A Generic State
// - A bunch of specific states
//
//  The StateMachine keeps track of all of the states, and takes the place of the while-loop from our switch statement version.
//  The Generic State serves as a way to describe the things that *all* states have to do.
//  The specific states each have a small behavior that does the job of the individual parts of our switch statement (updates the behavior according to the state).
// The strategem code is swwsw (Down, Up, Up, Down, Up)
// We can use states like this: S SW SWW SWWS SWWSW
#include <cstdio>
#include <string>
#include<iostream>

using namespace std;

namespace Names {
    // These are all the states that we have \/
    enum StateName{
        Init,
        S,
        SW,
        SWW,
        SWWS,
        SWWSW,
        Finished,
        Error,
        NumStates,
        NoChange,
    };
}



/// This is a pure-virtual class, because it can never be instantiated. All it does is describe what **all** actual states must be able to do.
/// We mark things are "pure-virtual" by putting "virtual" before the function and "=0" after them in the declaration.
class State {
    public:
    // Pure virtual functions mean that a class that inherits from here MUST implement this function
    virtual Names::StateName update(std::string input) = 0;

    // Initialize the state data and run anything that should be happening while the state is active
    virtual void enter(){}

    // This function will execute any last-minute code before leaving the current state, so that it
    // can clean up resources and stop any ongoing processes.
    virtual void leave(){}

    // this gives the state a chance to cause ANOTHER transition without waiting for input first.
    virtual Names::StateName epsilon() {
        return Names::StateName::NoChange;
    }

    // this function just checks to see if the input is what we're expecting, and goes to the correct state if it is. If not, it goes to the failure state.
    static Names::StateName expect(string input, string expected_input, Names::StateName on_success, Names::StateName on_failure = Names::StateName::Error) {
        if (input == expected_input){
            return on_success;
        }else{
            return on_failure;
        }
    }
};



class Init : public State {
public:
    Init() {
        cout << "Created State: Init" << endl;
    }

    ~Init() {
        cout << "State Init DYING" << endl;
    }

    // Pure virtual functions mean that a class that inherits from here MUST implement this function
    Names::StateName update(std::string input){
        return State::expect(input, "s", Names::StateName::S, Names::StateName::Init);
    }

    // Initialize the state data and run anything that should be happening while the state is active
    void enter(){
        cout << "Entering State: Init" << endl;
    }

    // This function will execute any last-minute code before leaving the current state, so that it
    // can clean up resources and stop any ongoing processes.
    void leave(){
        cout << "Leaving State: Init" << endl;
    }
};

class S :public State{
    public:
    S() {
        cout << "Creating State: S" << endl;
    }

    Names::StateName update(std::string input){
        if (input == "s"){
            return Names::StateName::S;
        } else {
            return State::expect(input,"w",Names::StateName::SW,Names::StateName::Error);
        }
    }

    void enter(){
        cout << "Entering State: S" << endl;
    }

    void leave(){
        cout << "Leaving State: S" << endl;
    }
};

class SW :public State{
    public:
    SW(){
        cout << "Creating State: SW" << endl;
    }

    Names::StateName update(string input){
        return State::expect(input, "w", Names::StateName::SWW);

    }

    void enter(){
        cout << "Entering State: SW" << endl;
    }
    void leave(){
        cout << "Leaving State: SW" << endl;
    }
};


class SWW : public State{
  public:

  SWW(){
      cout << "Creating State: SWW" << endl;
  }

  Names::StateName update(string input){
      return State::expect(input, "s", Names::StateName::SWWS, Names::StateName::Error);
  }

  void enter(){
      cout << "Entering State: SWW" << endl;
  }

  void leave(){
      cout << "Leaving State: SWW" << endl;
  }
};

class SWWS : public State{
  public:

  SWWS(){
      cout << "Creating State: SWWS" << endl;
  }

  Names::StateName update(string input){
      return State::expect(input, "w", Names::StateName::SWWSW, Names::StateName::Error);
  }

  void enter(){
      cout << "Entering State: SWWS" << endl;
  }

  void leave(){
      cout << "Leaving State: SWWS" << endl;
  }
};

class SWWSW : public State {
    public:

    SWWSW(){
        cout<< "Creating State: Finished" << endl;
    }

    Names::StateName update(string _input) {
        cout << "WHOAH HORSE. you can't update me" << endl;
        return Names::StateName::Error;
    }

    // but wait... there's no input needed here...
    // So, we use a function that requires so input.
    Names::StateName epsilon(){
        cout << "Ur toe touched grass and ur dead :O" << endl;
        cout << "Noooooo T^T" << endl;
        return Names::StateName::Finished;
    }

    void enter(){
        cout << "Entering State: SWWSW" << endl;
    }
    void leave(){
        cout << "Leaving State: SWWSW" << endl;
    }
};

class Error : public State{
    public:
    Error(){
        cout << "Created Error State"<< endl;
    }
    void enter(){
        cout << "Entering Error State" << endl;
    }
    void leave(){
        cout << "Leaving State Error" << endl;
    }
    Names::StateName update(string _input){
        cout << "Error! Wrong Code" << endl;
        return Names::Finished;

    }
    Names::StateName epsilon(){
        cout << "wrong" << endl;
        return Names::Finished;
    }

};

class Finished : public State {
public:
    Names::StateName update(string _input) {
        return Names::NoChange;
    }
    void enter() {
        cout << "Entered Finished state" << endl;
    }
    void leave() {
        cout << "Left Finished State" << endl;
    }
};

// This class is in charge of switching from state to state.
class StateMachine {
    public:
    StateMachine(){
        current_state = Names::Init;
        all_states[Names::Init] = new Init();
        all_states[Names::S] = new S();
        all_states[Names::SW] = new SW();
        all_states[Names::SWW] = new SWW();
        all_states[Names::SWWS] = new SWWS();
        all_states[Names::SWWSW] = new SWWSW();
        all_states[Names::Finished] = new Finished();
        all_states[Names::Error] = new Error();
    }

    void run() {
        while(current_state != Names::StateName::Finished) {
            string input = "";
            cout << "Enter a code letter: " ;
            cout.flush();
            cin >> input;
            Names::StateName next_state = all_states[current_state]->update(input);
            switchTo(next_state);
        }
    }

    void switchTo(Names::StateName new_state){
        if(new_state == Names::StateName::NoChange) {
            return;
        }
        all_states[current_state]->leave();
        current_state = new_state;
        all_states[current_state]->enter();
        Names::StateName epsilon_change = all_states[current_state]->epsilon();
        switchTo(epsilon_change);
    }

    Names::StateName current_state;

    State* all_states[Names::NumStates];
};


int main() {
    StateMachine machine;
    machine.run();
    return 0;
}
```

## Media resources

- [Youtube search for "How to structure c++ projects"](https://www.youtube.com/results?search_query=How%20to%20structure%20c++%20projects) 
- [Youtube search for "Implementing state machines in C++"](https://www.youtube.com/results?search_query=Implementing%20state%20machines%20in%20C++) 

## Homework

- [ ] #hw Finish implementing a simple state machine to control your robot's movement. [Example code and lesson link](https://school.ginosterous.com/projects/school-fall-2024/engineering/lessons/implementing-state-machines-cpp) [[2025-03-18\|2025-03-18]]
- [x] #hw Export and slice chassis models, get parts laid out on a build plate ready to print [[2025-03-13\|2025-03-13]]
- [ ] #hw Create a simple state machine for the robot in C++ using classes for `StateMachine`, `State`, and all of the particular states you can be in. [[2025-03-18\|2025-03-18]]
