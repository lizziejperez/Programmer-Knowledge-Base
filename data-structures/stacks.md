# Stacks

A **stack** is a linear data structure that follows **Last In, First Out (LIFO)**.

## Table of Contents

* [Key Characteristics](#1-key-characteristics)
* [Time Complexity](#2-time-complexity)
* [Structure](#3-structure)
* [Common Operations](#4-common-operations)
* [Variants](#5-variants)
* [Use Cases](#6-use-cases)
* [Advantages & Disadvantages](#7-advantages--disadvantages)
* [Interview Patterns](#8-interview-patterns)

## 1. Key Characteristics

* LIFO (Last In, First Out)
* Access only from the top
* Simple structure

## 2. Time Complexity

| Operation | Time |
| --------- | ---- |
| Push      | O(1) |
| Pop       | O(1) |
| Peek      | O(1) |
| Search    | O(n) |

## 3. Structure

```
Top → [3]
[2]
[1]
```

## 4. Common Operations

### Push

Add an element to the top.

```
stack = [1, 2]
stack.append(3)  → [1, 2, 3]
```

### Pop

Remove the top element.

```
stack = [1, 2, 3]
stack.pop() → [1, 2]
```

### Peek

View the top element without removing it.

```
stack[-1]
```

## 5. Variants

* Array-based stack
* Linked list stack

## 6. Use Cases

* Function call stack
* Undo/redo systems
* Expression evaluation
* DFS traversal

## 7. Advantages & Disadvantages

**Advantages**

* Simple
* Fast operations

**Disadvantages**

* Limited access (no indexing)

## 8. Interview Patterns

Common problem-solving patterns involving stacks:

* **Monotonic stack**: Maintain increasing/decreasing order for efficient comparisons

  * Example: https://leetcode.com/problems/daily-temperatures/

* **Balanced parentheses**: Validate matching symbols

  * Example: https://leetcode.com/problems/valid-parentheses/

* **Expression evaluation**: Evaluate postfix/prefix expressions

  * Example: https://leetcode.com/problems/evaluate-reverse-polish-notation/