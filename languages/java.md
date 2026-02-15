# Java Guide

## Syntax
### Comments
```java
// one line comment

/* multi-line
* comment
*/
```
### Variables
```java
int num; // declaration
num = 1; // assignment

double num2 = 3.1; // declaration + initialization

String text = "hi";

boolean bool = true;
```
### Arrays
```java
int[] arr = new int[n]; // n is the number of elements in the array
int[] arr2 = new int[] {1, 2, 3};
```
### Conditionals
```java
if(condition1) {
  // code
} else if(condition2) {
  // code
} else {
  // code
}

for(int i=0; i < max; i++) {
  // code
}

while(condition) {
  // code
}
```

## Class File Structure
```java
package example.package; // optional

import java.util.*; // optional - for access to other packages

public class ClassName {
  // Fields

  // Constructors

  // Methods

  public static void main(String[] args) {
    // Program entry point
  }
}
```
### Package
```java
package example.package;
```
- This groups related classes together.
- Folder structure must match the package name.
- Optional for small or single-file programs. Required in most larger projects.

### Class Declaration
```java
public class ClassName {
```
Access modifiers
Modifier | Meaning
--- | --- |
public | Accessible everywhere
private | Accessible only within the same class
protected | Accessible within package + subclasses
(none) | Package-private (default)

Other Optional Keywords
Keyword | Purpose
--- | --- |
abstract | Cannot be instantiated
final | Cannot be extended
static | Belongs to class, not instance

Example:
```java
public final class UtilityClass {
```

## Useful Classes
Print
```java
System.out.print("The value of x is " + x + "\n");
System.out.println("The value of y is " + y);
```
Scanner
```java
Scanner scan = new Scanner(Stystem.in);
int num = scan.nextInt();
double num2 = scan.nextDouble();
String text = scan.next();
```
