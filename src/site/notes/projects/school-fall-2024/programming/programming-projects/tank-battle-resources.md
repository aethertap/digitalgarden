---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/programming-projects/tank-battle-resources/"}
---


# Useful stuff for the tank battle game project

- [Loading javascript dynamically as a module (still unsafe alternative to eval)](https://2ality.com/2019/10/eval-via-import.html) ***NOT FOR PRODUCTION USE, dangerous for users!***
- [SES hardened javascript for loading untrusted code (safe alternative to eval)](https://github.com/endojs/endo/blob/master/packages/ses/docs/guide.md) - this is the way to do it, but too complex for immediate use
    - [hardenedjs.org](https://hardenedjs.org/#examples) appears to be the up-to-date home of this effort

## Using Localstorage

[Localstorage tutorial on logrocket](https://blog.logrocket.com/localstorage-javascript-complete-guide/)

## Matter-js

Matter is a pretty powerful javascript physics library, but it has some really strange properties. The biggest one is ***time***:

***IN MATTER-JS, TIME IS MEASURE IN 1/60 SECONDS***

That means that velocity calculations, and anything with a rate of change, is ***not per second***, but rather ***per time step***.

As far as I can tell, this is not officially documented *anywhere*.
