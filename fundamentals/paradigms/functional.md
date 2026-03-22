# Functional Programming

Functional programming is a paradigm that treats computation as the evaluation of **functions**, avoiding mutable state and side effects.

## Table of Contents

* [Key Characteristics](#1-key-characteristics)
* [Core Concepts](#2-core-concepts)
* [Common Patterns](#3-common-patterns)
* [Examples](#4-examples)
* [Use Cases](#5-use-cases)
* [Advantages & Disadvantages](#6-advantages--disadvantages)
* [Interview Relevance](#7-interview-relevance)

## 1. Key Characteristics

* Functions are first-class citizens
* Emphasis on immutability
* Avoidance of side effects
* Declarative style (focus on what, not how)

## 2. Core Concepts

### Pure Functions

A pure function:

* Always returns the same output for the same input
* Has no side effects

Example (Python):

```python
def add(a, b):
    return a + b
```

### Immutability

Data is not modified after creation.

Instead of changing data, new data is created.

Example (Python):

```python
x = 5
x = x + 1   # creates a new value, does not modify original memory
```

### First-Class Functions

Functions can be:

* stored in variables
* passed as arguments
* returned from other functions

Example (Python):

```python
def greet(name):
    return "Hello " + name

f = greet
print(f("Lizzie"))
```

### Higher-Order Functions

Functions that take other functions as input or return functions.

Example (Python):

```python
def apply(func, value):
    return func(value)
```

### Recursion

Functions calling themselves instead of using loops.

Example (Python):

```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n - 1)
```

## 3. Common Patterns

### Map

Apply a function to every element in a collection.

```python
list(map(lambda x: x * 2, [1, 2, 3]))
```

### Filter

Select elements based on a condition.

```python
list(filter(lambda x: x > 2, [1, 2, 3, 4]))
```

### Reduce

Combine elements into a single value.

```python
from functools import reduce
reduce(lambda a, b: a + b, [1, 2, 3, 4])
```

### Function Composition

Combine multiple functions into one.

```python
def double(x): return x * 2
def increment(x): return x + 1

result = double(increment(3))
```

## 4. Examples

### JavaScript Example

```JavaScript
const nums = [1, 2, 3, 4];

const result = nums
    .map(x => x * 2)
    .filter(x => x > 4);
```

### Python Example

```python
nums = [1, 2, 3, 4]

result = [x * 2 for x in nums if x > 2]
```

## 5. Use Cases

* Data transformation pipelines
* Functional-style APIs (JavaScript, Python)
* Parallel and concurrent systems
* Declarative UI frameworks (React)

## 6. Advantages & Disadvantages

**Advantages**

* Easier reasoning about code
* Fewer bugs from shared state
* More predictable behavior
* Easier to test

**Disadvantages**

* Can be less intuitive for beginners
* Recursion can be harder to follow
* Performance overhead in some cases

## 7. Interview Relevance

Functional concepts appear in:

* JavaScript (map, filter, reduce)
* Python (list comprehensions, lambdas)
* System design (immutability, concurrency)

Common interview ideas:

* Transforming arrays efficiently
* Avoiding side effects
* Writing clean, composable functions