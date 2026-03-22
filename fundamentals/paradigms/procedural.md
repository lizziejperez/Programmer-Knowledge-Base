# Procedural Programming

Procedural programming is a paradigm based on organizing code into **procedures (functions)** that execute step-by-step.

## Table of Contents

* [Key Characteristics](#1-key-characteristics)
* [Core Concepts](#2-core-concepts)
* [Common Patterns](#3-common-patterns)
* [Examples](#4-examples)
* [Use Cases](#5-use-cases)
* [Advantages & Disadvantages](#6-advantages--disadvantages)
* [Interview Relevance](#7-interview-relevance)

## 1. Key Characteristics

* Organizes code around functions (procedures)
* Sequential execution of instructions
* Emphasis on control flow (loops, conditionals)
* Often uses shared or global state

## 2. Core Concepts

### Functions (Procedures)

A **function** is a named block of code that performs a specific task.

Example (C):

```c
int add(int a, int b) {
    return a + b;
}
```

### Control Flow

Programs execute using structured control flow:

* Conditionals (`if`, `switch`)
* Loops (`for`, `while`)
* Sequential execution

Example (C):

```c
for (int i = 0; i < 5; i++) {
    printf("%d\n", i);
}
```

### Variables and State

Data is stored in variables and may be modified over time.

Example (C):

```c
int x = 5;
x = x + 1;
```

### Global vs Local State

Procedural programs often rely on shared data.

* Local variables exist within functions
* Global variables can be accessed across functions

## 3. Common Patterns

### Step-by-Step Processing

Break a problem into ordered steps.

* Input
* Process
* Output

### Function Decomposition

Split large problems into smaller functions.

### Iterative Processing

Use loops to repeat actions over data.

### Top-Down Design

Start with a high-level solution, then break it into smaller procedures.

## 4. Examples

### C Example

```c
#include <stdio.h>

int main() {
    int sum = 0;

    for (int i = 1; i <= 5; i++) {
        sum += i;
    }

    printf("%d\n", sum);
    return 0;
}
```

### Python Example

```python
def sum_numbers(n):
    total = 0
    for i in range(1, n + 1):
        total += i
    return total
```

## 5. Use Cases

* Small programs and scripts
* Algorithm implementation
* System-level programming (e.g., C programs)
* Embedded systems

## 6. Advantages & Disadvantages

**Advantages**

* Simple and easy to understand
* Clear execution flow
* Efficient for small programs
* Minimal abstraction overhead

**Disadvantages**

* Difficult to scale for large systems
* Limited code reusability
* Harder to manage shared/global state
* Less modular than OOP

## 7. Interview Relevance

Procedural concepts appear in:

* Algorithm implementation
* Control flow problems (loops, conditionals)
* Low-level/system programming questions

Common interview ideas:

* Writing clean step-by-step logic
* Breaking problems into functions
* Understanding control flow and state changes