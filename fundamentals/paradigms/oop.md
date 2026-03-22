# Object-Oriented Programming (OOP)

Object-Oriented Programming (OOP) is a paradigm based on organizing software around **objects**, which combine data and behavior.

## Table of Contents

* [Key Characteristics](#1-key-characteristics)
* [Core Concepts](#2-core-concepts)
* [Relationships Between Concepts](#3-relationships-between-concepts)
* [Use Cases](#4-use-cases)
* [Advantages & Disadvantages](#5-advantages--disadvantages)
* [Interview Relevance](#6-interview-relevance)

## 1. Key Characteristics

* Organizes code around objects
* Combines data (fields) and behavior (methods)
* Supports modular and reusable design
* Models real-world entities and relationships

## 2. Core Concepts

### Class

A **class** is a blueprint for creating objects.

It defines:

* Fields (data / attributes)
* Methods (behavior / functions)

Example (Java):

```java
public class Car {
    String color;

    void drive() {
        System.out.println("Driving");
    }
}
```

### Object

An **object** is an instance of a class.

It:

* Has state (stored in fields)
* Has behavior (defined by methods)
* Exists in memory

Example (Java):

```java
Car myCar = new Car();
```

### Instantiation vs Initialization

**Instantiation**:
Creating an object from a class

**Initialization**:
Assigning initial values to that object

Example (Java):

```java
Car myCar = new Car();      // Instantiation
myCar.color = "Blue";       // Initialization
```

### Encapsulation

**Encapsulation** bundles data and methods together and restricts direct access to internal data.

Achieved using:

* Access modifiers (`private`, `public`, etc.)
* Getters and setters

Example (Java):

```java
private int speed;

public void setSpeed(int s) {
    speed = s;
}
```

Purpose:

* Protect data
* Control access
* Maintain invariants

### Abstraction

**Abstraction** hides implementation details and exposes only essential functionality.

Goal:

* Reduce complexity
* Improve usability

Example:

A `Car` exposes `drive()` but hides engine mechanics.

### Inheritance

**Inheritance** allows one class to inherit properties and behavior from another.

Promotes:

* Code reuse
* Hierarchical relationships

Example (Java):

```java
class Vehicle { }

class Car extends Vehicle { }
```

### Polymorphism

**Polymorphism** allows objects to be treated as instances of their parent class.

Types:

* Method Overloading (compile-time polymorphism)
* Method Overriding (runtime polymorphism)

Example (Java):

```java
Vehicle v = new Car();
```

The variable type is `Vehicle`, but the object is `Car`.

### Dynamic Binding

**Dynamic binding** determines which method implementation is executed at runtime.

Occurs during method overriding.

Example (Java):

```java
Vehicle v = new Car();
v.start();  // Calls Car's version at runtime
```

### Message Passing

Objects communicate by calling methods on one another.

Example (Java):

```java
car.drive();
```

The method call acts as a **message**.

## 3. Relationships Between Concepts

| Concept         | Purpose                     |
| --------------- | --------------------------- |
| Encapsulation   | Protect internal state      |
| Abstraction     | Hide complexity             |
| Inheritance     | Reuse code                  |
| Polymorphism    | Enable flexible behavior    |
| Dynamic Binding | Resolve behavior at runtime |

## 4. Use Cases

OOP is commonly used when modeling systems with clearly defined entities and behaviors.

Typical use cases:

* Large-scale applications with many interacting components
* GUI applications (buttons, windows, event systems)
* Game development (players, enemies, objects)
* Backend systems (services, controllers, models)
* Domain modeling (e.g., banking systems, inventory systems)

## 5. Advantages & Disadvantages

**Advantages**

* Encourages modular and reusable code
* Improves organization through clear structure
* Makes complex systems easier to model
* Supports code reuse via inheritance
* Promotes maintainability

**Disadvantages**

* Can introduce unnecessary complexity for small problems
* Inheritance hierarchies can become difficult to manage
* Over-abstraction can make code harder to understand
* More boilerplate compared to simpler paradigms

## 6. Interview Relevance

OOP concepts frequently appear in:

* System design questions (design a class or system)
* Object modeling problems
* Language-specific questions (Java, C#, C++)
* Understanding code structure and behavior

Common interview topics:

* Designing classes and relationships
* Explaining encapsulation, inheritance, and polymorphism
* When to use composition vs inheritance
* Identifying over-engineered or poorly designed systems
