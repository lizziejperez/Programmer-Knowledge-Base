# Arrays

An array is a data structure that stores elements in **contiguous memory locations** and allows **indexed access**.

## Table of Contents

* [Key Characteristics](#1-key-characteristics)
* [Time Complexity](#2-time-complexity)
* [Structure](#3-structure)
* [Common Operations](#4-common-operations)
* [Variants](#5-variants)
* [Use Cases](#6-use-cases)
* [Advantages & Disadvantages](#7-advantages--disadvantages)
* [Interview Patterns](#8-interview-patterns)
* [Multidimensional Arrays](#9-multidimensional-arrays)
* [Arrays vs Linked Lists](#10-arrays-vs-linked-lists)
* [Important Concepts](#11-important-concepts)
* [When to Use Arrays](#12-when-to-use-arrays)

## 1. Key Characteristics

* Fixed or dynamic size (depending on language)
* Indexed (usually 0-based)
* Contiguous memory layout
* Fast random access
* Homogeneous elements (in statically typed languages)

## 2. Time Complexity

| Operation         | Time           |
| ----------------- | -------------- |
| Access (`arr[i]`) | O(1)           |
| Update            | O(1)           |
| Search (unsorted) | O(n)           |
| Insert (end)*     | O(1) amortized |
| Insert (middle)   | O(n)           |
| Delete (end)      | O(1)           |
| Delete (middle)   | O(n)           |

*For dynamic arrays like Python lists or JavaScript arrays.

## 3. Structure

Arrays store elements in **contiguous memory** locations.

If an array starts at memory address `A`, and each element takes `k` bytes:

Address of `arr[i] = A + (i × k)`

This is why arrays support **O(1) access time**.

Example layout in memory:

```
Index:   0    1    2    3
Value:  [10] [20] [30] [40]
```

This allows:

* Fast indexing
* Efficient cache usage

However, inserting or deleting elements in the middle requires shifting elements.

## 4. Common Operations

### Traversal

```
for i in range(len(arr)):
    print(arr[i])
```

### Insertion at End

```
arr.append(5)
```

Amortized O(1)

### Insertion at Index

```
arr.insert(2, 99)
```

Requires shifting → O(n)

### Deletion

```
arr.pop()      # O(1)
arr.pop(2)     # O(n)
```

## 5. Variants

### Static Arrays

* Fixed size
* Cannot grow

Example (C):

```c
int arr[5] = {1, 2, 3, 4, 5};
```

### Dynamic Arrays

* Resize automatically
* Copy elements to new memory when capacity exceeded

Examples:

* Python list
* JavaScript Array
* C++ vector
* Java ArrayList

## 6. Use Cases

* Storing collections of data
* Implementing stacks/queues
* Lookup tables
* Dynamic programming tables
* Matrices and grids
* DP tables

## 7. Advantages & Disadvantages

**Advantages**

* Fast random access
* Simple structure
* Memory efficient
* Cache friendly

**Disadvantages**

* Expensive insert/delete in middle
* Fixed size (static arrays)
* Requires contiguous memory

## 8. Interview Patterns

Common problem-solving patterns involving arrays:

* **Two pointers**: Used to compare or process elements from both ends
  * Example: https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/

* **Sliding window**: Used for subarrays or substrings with constraints
  * Example: https://leetcode.com/problems/longest-substring-without-repeating-characters/

* **Prefix sums**: Used for efficient range queries
  * Example: https://leetcode.com/problems/subarray-sum-equals-k/

* **Binary search**: Used on sorted arrays to find elements efficiently
  * Example: https://leetcode.com/problems/binary-search/

* **In-place reversal**: Modify array without extra space
  * Example: https://leetcode.com/problems/reverse-string/

## 9. Multidimensional Arrays

Arrays can store other arrays.

Example:
```
matrix = [
    [1, 2, 3],
    [4, 5, 6]
]
```
Access:

`matrix[row][column]`

Time complexity remains O(1).

## 10. Arrays vs Linked Lists

| Feature        | Array      | Linked List    |
| -------------- | ---------- | -------------- |
| Random Access  | O(1)       | O(n)           |
| Insert/Delete  | O(n)       | O(1)*          |
| Memory Layout  | Contiguous | Non-contiguous |
| Cache Friendly | Yes        | No             |

*If node reference is known

## 11. Important Concepts

### Amortized Analysis

Dynamic arrays grow by resizing (usually doubling capacity).

Resizing is expensive (O(n)), but happens infrequently.

This leads to amortized O(1) append time.

Amortized means:
Some operations are expensive, but averaged over many operations, cost per operation is constant.

### Bounds Checking

Bounds checking ensures an index is within valid range:

`0 ≤ index < length`

Prevents illegal memory access.

* Python, Java, C# → bounds checked
* C → not bounds checked

## 12. When to Use Arrays

Use arrays when:

* You need fast indexing
* Data size is known or stable
* You don’t need frequent middle insertions
* Cache performance matters