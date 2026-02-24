# C Guide

C is a low-level, compiled, procedural programming language developed in the early 1970s.

It provides:

- Direct memory access
- Manual memory management
- Minimal runtime abstraction
- High performance

C is widely used in:

- Operating systems
- Embedded systems
- Compilers
- Game engines
- Performance-critical software

## Basic Structure

```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

Key Parts

- `#include` → Preprocessor directive
- `main()` → Entry point
- `printf()` → Standard output
- `return 0;` → Program exit status

## Compilation Process

C is compiled before execution.

```bash
gcc program.c -o program
./program
```

Stages:

1. Preprocessing
2. Compilation
3. Linking

## Primitive Data Types
```c
int
float
double
char
```

Modifiers:
```c
short
long
unsigned
signed
```

Example:
```c
unsigned int x = 10;
long long y = 1000000;
```

## Variables & Constants

```c
int age = 25;
const float PI = 3.14;
```

## Control Flow

### Conditionals
```c
if (x > 0) {
    printf("Positive");
} else {
    printf("Non-positive");
}
```

### Switch
```c
switch (x) {
    case 1:
        break;
    default:
        break;
}
```

### Loops
```c
for (int i = 0; i < 10; i++) { }

while (condition) { }

do { } while (condition);
```

## Functions

```c
int add(int a, int b) {
    return a + b;
}
```

Function prototype (declaration):
```c
int add(int a, int b);
```

## Pointers (Deep Dive)

A **pointer** is a variable that stores the memory address of another variable.

```c
int x = 10;
int *ptr = &x;
```

- `&x` → address of x
- `ptr` → stores that address
- `*ptr` → dereferences (accesses value at that address)

### Pointer Types

Pointers are typed:

```c
int *a;
char *b;
double *c;
```

The type determines:

- How many bytes are read
- Pointer arithmetic behavior

### Pointer Arithmetic

Pointers can be incremented.

```c
int arr[3] = {10, 20, 30};
int *p = arr;

p++;  // moves to next int
```

`p++` increases by `sizeof(int)` bytes, not 1 byte.

This is why arrays and pointers are closely related.

### Arrays and Pointers

Arrays decay to pointers when passed to functions.

```c
int arr[5];
int *p = arr;  // equivalent to &arr[0]
```

These are equivalent:

```c
arr[i]
*(arr + i)
```

This is fundamental in C.

### Pointers to Pointers

You can store the address of a pointer:

```c
int x = 5;
int *p = &x;
int **pp = &p;
```

- `*pp` → pointer to x
- `**pp` → value of x

Used in:

- Dynamic memory structures
- Function modifications of pointers

### Null Pointers

A null pointer points to nothing:

```c
int *ptr = NULL;
```
Dereferencing a null pointer causes undefined behavior.

Always initialize pointers.

### Void Pointers

A `void *` can point to any type.

```c
void *ptr;
```

But must be cast before dereferencing:
```c
int *ip = (int *)ptr;
```

Used in:
- Generic functions
- Memory allocation

### Pointers and Functions

#### Pass by Reference (Simulation)

C does not have true pass-by-reference.

You simulate it with pointers:

```c
void increment(int *x) {
    (*x)++;
}

int a = 5;
increment(&a);
```

This modifies the original variable.

### Function Pointers

Functions have addresses too.

```c
int add(int a, int b) {
    return a + b;
}

int (*func_ptr)(int, int) = add;

int result = func_ptr(2, 3);
```

Used in:

- Callbacks
- Event systems
- Dispatch tables

### Dynamic Memory & Pointers

Dynamic memory returns pointers:

```c
int *arr = malloc(5 * sizeof(int));
```

Memory must be freed:

```c
free(arr);
```

### Dangling Pointers

Occurs when:

- Memory is freed
- Pointer still references old address

```c
free(ptr);
ptr = NULL;  // good practice
```

### Common Pointer Errors

- Dereferencing uninitialized pointer
- Forgetting to free memory
- Double free
- Buffer overflow
- Off-by-one errors
- Using freed memory


### Why Pointers Matter

Pointers enable:

- Manual memory management
- Dynamic data structures (linked lists, trees)
- Efficient array handling
- Low-level system access
- Function callbacks
- Memory-mapped hardware access

C’s **power** comes from pointers — and so do most of its **dangers**.

## Memory Management

C requires manual memory management.

```c
#include <stdlib.h>

int *arr = malloc(5 * sizeof(int));

free(arr);
```

Key functions:

- `malloc()`
- `calloc()`
- `realloc()`
- `free()`

Failing to free memory causes leaks.

## Arrays
```c
int arr[5] = {1, 2, 3, 4, 5};
```

Arrays decay to pointers when passed to functions.

## Structs
```c
struct Person {
    char name[50];
    int age;
};
```

Using typedef:

```c
typedef struct {
    char name[50];
    int age;
} Person;
```

## Strings

Strings are arrays of characters ending with `\0`.

```c
char str[] = "Hello";
```

Common functions (string.h):

- `strlen()`
- `strcpy()`
- `strcmp()`

## Header Files

- `.h` files contain declarations
- `.c` files contain implementations

Example:
```c
// math_utils.h
int add(int a, int b);
```

## Important Characteristics

- Compiled language
- Procedural
- Statically typed
- No built-in garbage collection
- Manual memory management
- Minimal abstraction

## Common Pitfalls

- Buffer overflows
- Memory leaks
- Dangling pointers
- Undefined behavior
- No bounds checking on arrays

## When to Use C

Use C when:

- Performance is critical
- Low-level hardware control is required
- Building operating systems or embedded software
- Writing compilers or interpreters

## Summary

C gives:

- Direct control over memory
- High performance
- Low-level system access

But requires:

- Careful memory management
- Attention to safety
- Understanding of pointers and memory layout
