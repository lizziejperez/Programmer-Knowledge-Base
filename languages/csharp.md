# C# Guide

## Syntax

### Comments

```csharp
// one line comment

/*
 multi-line
 comment
*/
```

### Variables
```csharp
int num;        // declaration
num = 1;        // assignment

double num2 = 3.1;

string text = "hi";

bool isActive = true;
```

#### Declaration + Initialization
```csharp
int count = 10;
```

#### Constants
```csharp
const float PI = 3.14f;
```

### Arrays
```csharp
int[] arr = new int[5];

int[] arr2 = new int[] {1, 2, 3};

int[] arr3 = {1, 2, 3};
```

Access:
```csharp
arr3[0];
arr3.Length;
```

### Conditionals
```csharp
if (condition1)
{
    // code
}
else if (condition2)
{
    // code
}
else
{
    // code
}
```

### Loops
```csharp
for (int i = 0; i < max; i++)
{
    // code
}

while (condition)
{
    // code
}

foreach (int value in arr3)
{
    // iterate
}
```

### Methods
```csharp
int Add(int a, int b)
{
    return a + b;
}
```

## Class Structure
```csharp
public class Person
{
    // Fields
    public string name;

    // Constructor
    public Person(string name)
    {
        this.name = name;
    }

    // Method
    public void Greet()
    {
        Console.WriteLine("Hello " + name);
    }
}
```

Create object:
```csharp
Person p = new Person("Alice");
p.Greet();
```

### Access Modifiers
| Modifier  | Meaning                            |
| --------- | ---------------------------------- |
| public    | Accessible everywhere              |
| private   | Accessible within the same class   |
| protected | Accessible in class and subclasses |
| internal  | Accessible within same assembly    |

### Static
```csharp
public static class MathUtility
{
    public static int Square(int x)
    {
        return x * x;
    }
}
```

Call:
```csharp
MathUtility.Square(5);
```

### Properties
```csharp
public int Health { get; set; }
```

Expanded form:
```csharp
private int health;

public int Health
{
    get { return health; }
    set { health = value; }
}
```

## Type System

### Value Types
- int
- float
- double
- bool
- char
- struct

### Reference Types
- string
- class
- object
- array

### Null
Used to mean no object exists at this reference.
```csharp
object obj = null;
```
Use null checks:
```csharp
if (obj != null)
{
    // safe
}
```

### Type Casting
```csharp
int x = 5;
float y = (float)x;
```

## Operators
### Equality
```csharp
5 == 5;   // true
5 != 3;   // true
```
For objects:
```csharp
if (obj == null)
{
    // check for null
}
```

### Arithmetic Operators

Used for mathematical calculations.

| Operator | Meaning | Example | Result |
|----------|---------|----------|--------|
| + | Addition | 5 + 2 | 7 |
| - | Subtraction | 5 - 2 | 3 |
| * | Multiplication | 5 * 2 | 10 |
| / | Division | 5 / 2 | 2 (integer division) |
| % | Modulus (remainder) | 5 % 2 | 1 |

#### Notes

- If both operands are integers, division performs integer division.
- Use a float/double for decimal division:
```csharp
5.0 / 2   // 2.5
```

### Logical Operators

Used to combine or invert boolean expressions.

| Operator | Meaning | Example |
|----------|----------|----------|
| && | Logical AND | a && b |
| \|\| | Logical OR | a \|\| b |
| ! | Logical NOT | !a |

## Common Built-in Classes
Console (non-Unity)
```csharp
Console.WriteLine("Hello");
```

## Unity-Specific Basics

### `MonoBehaviour`
```csharp
using UnityEngine;

public class Player : MonoBehaviour
{
    void Start()
    {
        Debug.Log("Game started");
    }

    void Update()
    {
        // called once per frame
    }
}
```

Debugging
```csharp
Debug.Log("Message");
Debug.LogWarning("Warning");
Debug.LogError("Error");
```