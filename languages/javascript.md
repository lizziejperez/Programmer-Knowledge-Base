# Javascript Guide

## Syntax

### Comments

```javascript
// one line comment

/*
 multi-line
 comment
*/
```

### Variables

```javascript
let num;        // declaration
num = 1;        // assignment

let num2 = 3.1;

let text = "hi";

let bool = true;

```

Other declarations:
```javascript
const PI = 3.14;   // cannot be reassigned
var oldStyle = 5;  // function-scoped (avoid in modern JS)
```
- `let` → block-scoped variable
- `const` → block-scoped, cannot be reassigned
- `var` → function-scoped (legacy)

### Arrays
```javascript
let arr = new Array(n);   // n empty slots
let arr2 = [1, 2, 3];
```
Access elements:
```javascript
arr2[0];
arr2.length;
```

### Conditionals
```javascript
if (condition1) {
  // code
} else if (condition2) {
  // code
} else {
  // code
}
```

### Loops
```javascript
for (let i = 0; i < max; i++) {
  // code
}

for (let value of arr2) {
  // iterate over values
}

while (condition) {
  // code
}

```

### Functions
```javascript
function greet(name) {
  return "Hello " + name;
}

// arrow function
const greet = (name) => {
  return "Hello " + name;
};
```

## Class Structure
```javascript
class ClassName {
  constructor(param) {
    this.param = param;
  }

  methodName() {
    // code
  }
}
```

Example:
```javascript
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log("Hello " + this.name);
  }
}
```
* Create object:
    ```javascript
    let p = new Person("Alice");
    p.greet();
    ```

### Modules
Export:
```javascript
export function greet() {}
```

Import:
```javascript
import { greet } from "./file.js";
```

## Useful Built-in Objects
### Console
```javascript
console.log("Hello");
console.error("Error message");
```
### Math
```javascript
Math.sqrt(9);
Math.floor(3.7);
Math.random(); // Returns a pseudo-random number in [0, 1).
```
Official Documentation: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)
### Date
```javascript
let now = new Date();
let specific = new Date(2024, 0, 15); // Jan 15, 2024
```
Official Documentation: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)

### Type Checking
```javascript
typeof 5;          // "number"
typeof "hello";    // "string"
typeof true;       // "boolean"
```
### Equality
```javascript
5 == "5";   // true (loose equality)
5 === "5";  // false (strict equality)
```
Use `===` (strict equality) in practice.