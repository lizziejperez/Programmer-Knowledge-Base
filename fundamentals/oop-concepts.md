# Object-Oriented Programming (OOP) Concepts

Object-Oriented Programming (OOP) is a paradigm based on organizing software around **objects**, which combine data and behavior.

## Core Concepts

### 1. Class

A **class** is a blueprint for creating objects.

It defines:
- Fields (data / attributes)
- Methods (behavior / functions)

Example (Java):

```java
public class Car {
    String color;

    void drive() {
        System.out.println("Driving");
    }
}
```

---

### 2. Object

An **object** is an instance of a class.

It:
- Has state (stored in fields)
- Has behavior (defined by methods)
- Exists in memory

Example (Java):
```java
Car myCar = new Car();
```

---

### 3. Instantiation vs Initialization

**Instantiation**:
Creating an object from a class

**Initialization**:
Assigning initial values to that object

Example (Java):
```java
Car myCar = new Car();      // Instantiation
myCar.color = "Blue";       // Initialization
```

---

### 4. Encapsulation

**Encapsulation** bundles data and methods together and restricts direct access to internal data.

Achieved using:
- Access modifiers (`private`, `public`, etc.)
- Getters and setters

Example (Java):
```java
private int speed;

public void setSpeed(int s) {
    speed = s;
}
```

Purpose:
- Protect data
- Control access
- Maintain invariants

---

### 5. Abstraction

**Abstraction** hides implementation details and exposes only essential functionality.

Goal:
- Reduce complexity
- Improve usability

Example :

A `Car` exposes `drive()` but hides engine mechanics.

---

### 6. Inheritance

**Inheritance** allows one class to inherit properties and behavior from another.

Promotes:
- Code reuse
- Hierarchical relationships

Example (Java):
```java
class Vehicle { }

class Car extends Vehicle { }
```

---

### 7. Polymorphism

**Polymorphism** allows objects to be treated as instances of their parent class.

Types:
- Method Overloading (compile-time polymorphism)
- Method Overriding (runtime polymorphism)

Example (Java):
```java
Vehicle v = new Car();
```

The variable type is `Vehicle`, but the object is `Car`.

---

### 9. Dynamic Binding

**Dynamic binding** determines which method implementation is executed at runtime.

Occurs during method overriding.

Example (Java):
```java
Vehicle v = new Car();
v.start();  // Calls Car's version at runtime
```

---

### 10. Message Passing

Objects communicate by calling methods on one another.

Example (Java):
```java
car.drive();
```

The method call acts as a **message**.

---

## Relationships Between Concepts
| Concept         | Purpose                     |
| --------------- | --------------------------- |
| Encapsulation   | Protect internal state      |
| Abstraction     | Hide complexity             |
| Inheritance     | Reuse code                  |
| Polymorphism    | Enable flexible behavior    |
| Dynamic Binding | Resolve behavior at runtime |