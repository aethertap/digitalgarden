---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/introducing-tank-battle/"}
---


#  Introducing the Tank Battle Game

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


- ***[[projects/school-fall-2024/programming/programming-projects/tank-battle-game\|Project index: tank-battle-game]]*** 
## Concept summary and lesson


- typescript and html 
- monaco editor 
- matter-js physics library 
- differential steering bot simulator 
- control system loops 

## Examples/demo

This is HTML - it's used to set up the *structure* and *content* of a web page. By itself, this is very bland looking. We'll talk about CSS soon, but CSS is the language we use to add some *style* to the document below.

The important things to see here:
- Tags come in pairs, and each one is enclosed in angle brackets (like the tag `div`, which looks like this: `<div>`)
- Closing tags have a slash (`/` ) before the name: `</div>` closes the `<div>` tag from before
- Tags can have attributes inside that give you extra information about how to work with the content. This example uses the `id` tag, which gives a unique identifier to the tag, and the `class` tag, which is used mostly by the CSS styling system.
- The *content* for a tag generally goes between the opening and closing parts of the tag. 
- Tags can be *nested* in each other. We'll use this for creating page layouts, text with formatted parts, and other stuff.
```html
  <div id="container">
    <div class="column">
      <div id="game"></div>
      <div id="output">some test output</div>
    </div>
    <div class="column">
      <div class="flex1">
        <div id="loader">loading...</div>
        <div id="monaco-editor-embed" style="height: 800px;" />
      </div>
      <div class="row">
        <button id="shipcodebutton">ship it!</button>
        <button id="checkcodebutton">check it</button>
        <button id="reformatcodebutton">reformat</button>
        <button id="downloadbutton">download</button>
      </div>
    </div>
  </div>
 ```

### Javascript

Javascript is the language of web development that makes things dynamic. HTML and CSS are sufficient to make nice looking documents and even add a few effects and animations, but to get real dynamic content, you'll have to reach for javascript. Sadly, javascript development is fraught with strange choices and an extremely bloated and redundant ecosystem of tools that's very, **very** hard for a beginner to navigate. However, it's what we have and you can do really cool stuff with it despite the flaws.

We're going to be writing our code in *typescript*, which is a subset of javascript that has strong types. It was created in an effort to make javascript less prone to errors and subtle bugs that are hard to find, and it is a huge improvement. It still suffers from the ecosystem problems, but in general I find the typescript development process to be a lot less painful.

Here's some from the same page ([editor.html](https://github.com/aethertap/tank-battle/blob/main/editor.html)) in our [[projects/school-fall-2024/programming/programming-projects/tank-battle-game\|tank-battle-game]]

```javascript

  function script_loader(code) {
    let self=this;
    console.log(`script_loader: code = ${code}`);
    let uri = `data:text/javascript;base64,${btoa(code)}`;
    return import(uri)
      .then(scr=>{
        console.log("Imported script");
        return scr.default;
      });
  }
```

This is the code that we're currently using to make the stuff you type into the editor into something your tank can actually run. NOTE: The way we're doing this right now is VERY UNSAFE and should not be used an a public app that has any kind of user data. That's because the code you enter this way has full access to the browser, so if I wrote bad code and saved it to my tank, then another user logs in and my tank's code runs against theirs, then my code could access things from their browser and do nefarious stuff. We will be changing this method out so that it uses [hardened JS](https://hardenedjs.org), but that process is harder than I expected so i'm going to work on it in the background as we go through class.


## Media resources

- [Youtube search for "typescript and html"](https://www.youtube.com/results?search_query=typescript%20and%20html) 
- [Youtube search for "monaco editor"](https://www.youtube.com/results?search_query=monaco%20editor) 
- [Youtube search for "matter-js physics library"](https://www.youtube.com/results?search_query=matter-js%20physics%20library) 
- [Youtube search for "differential steering bot simulator"](https://www.youtube.com/results?search_query=differential%20steering%20bot%20simulator) 
- [Youtube search for "control system loops"](https://www.youtube.com/results?search_query=control%20system%20loops) 


## Exercises

- [ ] #hw (programming) Clone the [tank battle repository](https://github.com/aethertap/tank-battle), write a "drive in a square" script. [[2025-02-19\|2025-02-19]]
