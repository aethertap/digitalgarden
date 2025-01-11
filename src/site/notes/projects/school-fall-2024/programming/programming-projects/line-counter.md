---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/programming-projects/line-counter/"}
---


# Write a line counter

Your mission: Write a program that reads data from a file, counts the number of lines it finds, and prints the result to the console.

## Things that might be handy

### Reading a file in node

```javascript

import {readFile} from 'fs';
const args = process.argv[2..];

for(let path of args) {
    let c = count_lines(fs.readFileSync(filePath, {encoding: 'utf-8'});
    console.log(`${path}: ${c}`);
}

```

### Getting command line arguments in node

