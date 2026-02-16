# Python Guide

## Comments

```python
# one line comment

"""
multi-line
comment
"""
```

## Variables

Python is dynamically typed (no type declaration required).

```python
num = 1
num2 = 3.1
text = "hi"
is_active = True
```

Multiple Assignment

```python
a, b = 1, 2
```

## Data Types

Numeric
- int
- float
- complex

Boolean
- True
- False

String

```python
text = "hello"
```

Type Checking
```python
type(num)
```

## Type Conversion

```python
int("5")
float("3.2")
str(10)
bool(1)
```

## Strings

```python
text = "hello"

text[0]        # indexing
text[1:4]      # slicing
len(text)
```

Formatted strings:

```python
name = "Alice"
f"Hello {name}"
```

## Lists
```python
arr = [1, 2, 3]

arr[0]
arr.append(4)
arr.remove(2)
len(arr)
```

## Tuples
```python
t = (1, 2, 3)
```

Immutable (cannot change values)

## Dictionaries
```python
d = {"name": "Alice", "age": 25}

d["name"]
d.get("age")

## Sets
s = {1, 2, 3}

s.add(4)
```

No duplicate values

## Conditionals
```python
if condition1:
    # code
elif condition2:
    # code
else:
    # code
```

## Loops

For Loop

```python
for i in range(5):
    print(i)
```

While Loop

```python
while condition:
    # code
```

## Functions
```python
def add(a, b):
    return a + b
```

Default parameters:

```python
def greet(name="Guest"):
    return f"Hello {name}"
```

## Lambda Functions
```python
square = lambda x: x * x
```

## Classes
```python
class Person:
    def __init__(self, name):
        self.name = name

    def greet(self):
        print("Hello", self.name)
```

Create object:
```python
p = Person("Alice")
p.greet()
```

## Imports
```python
import math
math.sqrt(9)

from math import sqrt
sqrt(9)
```

## Exception Handling
```python
try:
    x = 1 / 0
except ZeroDivisionError:
    print("Cannot divide by zero")
finally:
    print("Done")
```

## Useful Built-ins
```python
len()
range()
print()
type()
input()
```

## Equality
```python
5 == 5
5 != 3
```

Identity vs Equality:
```python
a = [1,2]
b = [1,2]

a == b   # True (same values)
a is b   # False (different objects)
```

## None

Represents absence of a value.

```python
x = None

if x is None:
    print("No value")
```

Use is None instead of == None.