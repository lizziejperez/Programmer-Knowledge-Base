# Logic Programming

Logic programming is a paradigm based on **formal logic**, where programs consist of facts and rules, and computation is performed through logical inference.

## Table of Contents

* [Key Characteristics](#1-key-characteristics)
* [Core Concepts](#2-core-concepts)
* [Common Patterns](#3-common-patterns)
* [Examples](#4-examples)
* [Use Cases](#5-use-cases)
* [Advantages & Disadvantages](#6-advantages--disadvantages)
* [Interview Relevance](#7-interview-relevance)

## 1. Key Characteristics

* Programs are defined using facts and rules
* Execution is driven by queries
* Focus on what is true, not how to compute it
* Declarative programming style

## 2. Core Concepts

### Facts

Facts represent basic truths.

Example (Python):

```python
facts = [
    ("alice", "bob"),
    ("bob", "charlie")
]
```

### Rules

Rules define relationships between facts.

Example (Python):

```python
def is_grandparent(x, z):
    for a, b in facts:
        if a == x:
            for c, d in facts:
                if c == b and d == z:
                    return True
    return False
```

Meaning:

X is a grandparent of Z, if X is a parent of Y, and Y is a parent of Z.

### Queries

Queries ask questions about the defined facts and rules.

Example (Python):

```python
is_grandparent("alice", "charlie")
```

### Unification

Unification is the process of matching variables with values or other variables to satisfy a rule or query.

It allows the system to determine if a query can be satisfied.

### Backtracking

Backtracking is used to explore multiple possible solutions.

If one path fails, the system automatically tries another.

This is commonly used in problems like permutations, combinations, and pathfinding.

## 3. Common Patterns

### Rule-Based Systems

Define behavior using rules instead of explicit control flow.

### Constraint Solving

Solve problems by defining constraints rather than step-by-step instructions.

### Search Through Possibilities

Explore multiple solutions using backtracking.

## 4. Examples

### Python Example (Rule-Based Logic)

Facts:

```python
facts = [
    ("alice", "bob"),
    ("bob", "charlie")
]
```

Rule:

```python
def is_grandparent(x, z):
    for a, b in facts:
        if a == x:
            for c, d in facts:
                if c == b and d == z:
                    return True
    return False
```

Query:

```python
is_grandparent("alice", "charlie")
```

### Key Idea

Logic programming focuses on:

* defining relationships (rules)
* querying those relationships
* letting the system determine how to compute the result

## 5. Use Cases

* Rule-based systems
* AI and knowledge representation
* Expert systems
* Constraint solving problems

## 6. Advantages & Disadvantages

**Advantages**

* Clear and expressive for rule-based problems
* Focuses on logic instead of control flow
* Can automatically explore multiple solutions

**Disadvantages**

* Less intuitive for most programmers
* Limited mainstream use
* Performance can be unpredictable
* Harder to debug compared to procedural or OOP

## 7. Interview Relevance

Logic programming concepts appear in:

* Constraint-based problems
* Backtracking algorithms
* Recursive problem solving

Common interview ideas:

* Understanding backtracking (e.g., puzzles, search problems)
* Expressing rules and relationships
* Thinking declaratively instead of procedurally