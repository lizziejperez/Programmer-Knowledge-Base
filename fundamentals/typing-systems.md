# Typing Systems

A typing system defines how a programming language classifies values and enforces constraints on operations.

## Table of Contents

* [Key Characteristics](#1-key-characteristics)
* [Core Concepts](#2-core-concepts)
* [Common Patterns](#3-common-patterns)
* [Examples](#4-examples)
* [Use Cases](#5-use-cases)
* [Advantages & Disadvantages](#6-advantages--disadvantages)
* [Interview Relevance](#7-interview-relevance)

## 1. Key Characteristics

* Determines how values are categorized (types)
* Defines how operations interact with those types
* Influences safety, flexibility, and performance
* Varies across programming languages

## 2. Core Concepts

### Static vs Dynamic Typing

**Static Typing**:

* Types are checked at compile time.
* Examples: C, Java, C#

**Dynamic Typing**

* Types are checked at runtime.
* Examples: Python, JavaScript

### Strong vs Weak Typing

**Strong Typing**: 
Prevents implicit type conversions that could lead to errors.

Example (Python):

```python
"5" + 5   # error
```

**Weak Typing**: 
Allows implicit type conversions.

Example (JavaScript):

```javascript
"5" + 5   // "55"
```

### Type Inference

The language automatically determines types without explicit annotation.

Example (TypeScript):

```ts
let x = 5;  // inferred as number
```

### Type Annotations

Explicitly specifying types.

Example (Python):

```python
def add(a: int, b: int) -> int:
    return a + b
```

### Primitive vs Composite Types

**Primitive Types**

* int, float, boolean, char

**Composite Types**

* arrays, objects, structs, lists

### Duck Typing

Objects are considered valid based on behavior, not explicit type.

Example (Python):

```python
def print_length(x):
    print(len(x))
```

Works for any object with `len`.

## 3. Common Patterns

### Type Safety

Prevent invalid operations through type checking.

### Generic Programming

Write code that works across multiple types.

Example (Java):

```java
List<T>
```

### Type Casting

Convert one type to another.

Example (C):

```c
(int) 3.14
```

## 4. Examples

### Static Typing (Java)

```java
int x = 5;
x = "hello";  // error
```

### Dynamic Typing (Python)

```python
x = 5
x = "hello"  # allowed
```

### Weak Typing (JavaScript)

```javascript
"5" + 5  // "55"
```

### Strong Typing (Python)

```python
"5" + 5  # error
```

## 5. Use Cases

* Static typing for large, maintainable systems
* Dynamic typing for rapid prototyping
* Strong typing for safer systems
* Weak typing for flexibility in scripting

## 6. Advantages & Disadvantages

**Advantages (Static / Strong)**

* Fewer runtime errors
* Better tooling (autocomplete, type checking)
* Easier to maintain large systems

**Disadvantages (Static / Strong)**

* More verbose
* Slower development speed initially

**Advantages (Dynamic / Weak)**

* Faster prototyping
* Less boilerplate
* More flexible

**Disadvantages (Dynamic / Weak)**

* More runtime errors
* Harder to maintain large systems
* Less predictable behavior

## 7. Interview Relevance

Typing systems appear in:

* Language comparison questions
* System design discussions
* Debugging and code reasoning

Common interview questions:

* Static vs dynamic typing
* Strong vs weak typing
* Type safety and runtime errors
* Differences between languages (Java vs Python vs JavaScript)