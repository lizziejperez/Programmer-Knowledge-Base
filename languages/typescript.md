# TypeScript Guide

## Files

### `.ts` Files

These are standard TypeScript files used for code that does not contain JSX (JavaScript XML) syntax.

They typically house:
- Utility functions
- Helper logic
- API calls and data fetching logic
- Type definitions, interfaces, and classes
- Redux store and reducer logic
- Any other non-UI related logic

### `.tsx` Files

These files are specifically for code that **includes** JSX syntax, meaning they are used to define React components and their UI structure.

## Comments

```typescript
// single line comment

/*
    Multi-line
    comment
*/
```

## Primitive Types

### String

```typescript
let name: string;
name = "Lizzie";
```

### Number

```typescript
let decimal: number = 6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
```

### Boolean

```typescript
let isDone: boolean = false;
isDone = true;
```

### Big Int

```typescript
let big: bigint = 100n;
```

## Special Types

- `any` — Disables type checking for a value, allowing it to be assigned and used as any type.
- `unknown` — Represents a value of unknown type that must be type-checked before being used.
- `void` — Indicates that a function does not return a value.
- `null` — Represents the intentional absence of an object value.
- `undefined` — Represents a variable that has been declared but not assigned a value.

## Arrays

```typescript
let nums: number[] = [1, 4, 7];
let nums: Array<number> = [1, 4, 7]; // another way
```

## Tuples

```typescript
let pair: [number, string];
pair = [1, "dog"];
```

## Objects

`object` is a type that represents the non-primitive type, i.e. anything that is **not** number, string, boolean, bigint, symbol, null, or undefined.

### I. Inline Object Type

```typescript
let user: { name: string; age: number };

user = {
    name: "Lizzie",
    age: 27
};
```

### II. Type Alias

Used to define a reusable custom type.

```typescript
type User = {
    name: string;
    age: number;
};

let user: User = {
    name: "Lizzie",
    age: 27
};
```

#### Optional & Readonly Properties

- Use `?` to make the property optional.
- Use `readonly` to prevent modification after assignment.


```typescript
type User = {
    readonly id: number; // readonly
    name: string;
    age?: number; // optional
};

let user: User = { id: 1, name: "Lizzie" };

// user.id = 2;  // error
```

### III. Interface
```typescript
interface User {
    name: string;
    age: number;
}

let user: User = {
    name: "Lizzie",
    age: 27
};
```

### When to Use What
- Inline type → quick one-off object
- type → flexible (can use unions, intersections)
- interface → commonly used for object shapes, especially for React props

## Functions

```typescript
// function definition
function printText(text: string) : void {
    console.log(text);
}

// function call
printText("Hello World!");
```

`void` means the function does not return anything. This can be replaced with any return type.

### Default Parameters

```typescript
function greet(name: string = "Guest"): string {
    return `Hello ${name}`;
}
```

### Arrow Functions

```typescript
const add = (a: number, b: number): number => {
    return a + b;
};
```

Short form (implicit return):

```typescript
const square = (x: number): number => x * x;
```

### Overloaded Functions

TypeScript allows function overload signatures.

```typescript
function combine(a: string, b: string): string;
function combine(a: number, b: number): number;

function combine(a: any, b: any): any {
    return a + b;
}
```

### Async Functions

```typescript
async function fetchData(): Promise<string> {
    return "data";
}
```

Async functions return a `Promise<T>`.

## Function Type

### Function Type Annotation

You can define the type of a function.

```typescript
let multiply: (a: number, b: number) => number;

multiply = (a, b) => a * b;
```

### Function Type Alias

```typescript
type MathOperation = (a: number, b: number) => number;

const subtract: MathOperation = (a, b) => a - b;
```

## Classes

TypeScript supports classes with typed fields and methods.

### Basic Class

```typescript
class Person {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    greet(): string {
        return `Hello, my name is ${this.name}`;
    }
}

let p = new Person("Lizzie", 27);
p.greet();
```

### Access Modifiers
TypeScript supports access modifiers inside classes.
| Modifier  | Meaning                                |
| --------- | -------------------------------------- |
| public    | Accessible anywhere (default)          |
| private   | Accessible only within the class       |
| protected | Accessible within class and subclasses |
| readonly  | Cannot be changed after initialization |


Example:

```typescript
class User {
    public name: string;
    private password: string;
    readonly id: number;

    constructor(name: string, password: string, id: number) {
        this.name = name;
        this.password = password;
        this.id = id;
    }
}
```

### Parameter Properties (Shortcut)

You can declare and initialize fields directly in the constructor:

```typescript
class User {
    constructor(
        public name: string,
        private password: string,
        readonly id: number
    ) {}
}
```

### Inheritance

```typescript
class Animal {
    move(): void {
        console.log("Moving...");
    }
}

class Dog extends Animal {
    bark(): void {
        console.log("Woof!");
    }
}
```

### Implementing Interfaces

```typescript
interface Printable {
    print(): void;
}

class Document implements Printable {
    print(): void {
        console.log("Printing...");
    }
}
```

## Union Types (`|`)

A union type allows a variable to hold more than one type.

Syntax uses the `|` (pipe) operator.

Example:

```typescript
let value: string | number;

value = "hello";  // valid
value = 42;       // valid
value = true;     // error
```

### Type Narrowing

When using union types, TypeScript needs help determining the exact type.

```typescript
function printId(id: string | number) {
    if (typeof id === "string") {
        console.log(id.toUpperCase()); // safe
    } else {
        console.log(id.toFixed(2)); // safe
    }
}
```

### Union with Literal Types

```typescript
type Direction = "left" | "right" | "up" | "down";

let move: Direction;

move = "left";   // valid
move = "forward"; // error
```

### Union with Objects

```typescript
type Success = {
    status: "success";
    data: string;
};

type Error = {
    status: "error";
    message: string;
};

type Response = Success | Error;
```

### Discriminated Union

```typescript
function handleResponse(res: Response) {
    if (res.status === "success") {
        console.log(res.data);
    } else {
        console.log(res.message);
    }
}
```

This is very common in React and API handling.

## Intersection Types (`&`)

An intersection type combines multiple types into one.

```typescript
type Person = { name: string };
type Employee = { id: number };

type Worker = Person & Employee;

let worker: Worker = {
    name: "Lizzie",
    id: 101
};
```

## Imports

Used to bring code or resources from another file or package.

### Default Import

```typescript
import React from 'react';
```

Imports the default export from a module.

### Named Import

```typescript
import { useState } from 'react';
```

Imports specific exported members.

### Namespace Import
```typescript
import * as React from 'react';
```

Imports all exports under a namespace.

### Side-Effect Import
```typescript
import './App.css';
```

Imports a file for its side effects (e.g., applying CSS).

### Relative vs Package Imports

- `./file` → local file
- `../file` → parent folder
- `'react'` → installed package (node_modules)