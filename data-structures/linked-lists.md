# Linked Lists

A **linked list** is a linear data structure where each node stores data and a reference to the next node.

## Table of Contents

* [Key Characteristics](#1-key-characteristics)
* [Time Complexity](#2-time-complexity)
* [Structure](#3-structure)
* [Common Operations](#4-common-operations)
* [Variants](#5-variants)
* [Use Cases](#6-use-cases)
* [Advantages & Disadvantages](#7-advantages--disadvantages)
* [Interview Patterns](#8-interview-patterns)
* [Memory Notes](#9-memory-notes)
* [Arrays vs Linked Lists](#10-arrays-vs-linked-lists)
* [Important Concepts](#11-important-concepts)
* [Common Bugs](#12-common-bugs)

## 1. Key Characteristics

* Non-contiguous memory
* Dynamic size
* Sequential access
* Uses pointers (references)

## 2. Time Complexity

| Operation       | Time         |
| --------------- | ------------ |
| Access by index | O(n)         |
| Search          | O(n)         |
| Insert at head  | O(1)         |
| Insert at tail  | O(1) or O(n) |
| Insert middle   | O(n)         |
| Delete at head  | O(1)         |
| Delete middle   | O(n)         |

Tail insertion is O(1) only if a tail pointer is maintained.

## 3. Structure

```
[Data | Next] → [Data | Next] → [Data | Next] → null
```

## 4. Common Operations

### Traversal

```
current = head
while current != null:
    current = current.next
```

### Insert at Head

```
newNode.next = head
head = newNode
```

### Delete at Head

```
head = head.next
```

## 5. Variants

### Singly Linked List

`head → A → B → C → null`

### Doubly Linked List

`null ← A ←→ B ←→ C → null`

### Circular Linked List

`A → B → C → A`

## 6. Use Cases

* Frequent insertions/deletions
* Dynamic data
* Implementing stacks/queues
* LRU cache internals
* Hash table chaining

## 7. Advantages & Disadvantages

ADD THIS (missing currently):

**Advantages**

* Efficient insert/delete
* Dynamic size

**Disadvantages**

* Slow access
* Memory overhead

## 8. Interview Patterns

Common problem-solving patterns involving linked lists:

* **Fast and slow pointers**: Used to detect cycles or find the middle
  * Example: https://leetcode.com/problems/linked-list-cycle/

* **Reversing a linked list**: Fundamental pointer manipulation problem
  * Example: https://leetcode.com/problems/reverse-linked-list/

* **Merging lists**: Combine sorted linked lists
  * Example: https://leetcode.com/problems/merge-two-sorted-lists/

* **Removing nth node from end**: Uses two-pointer technique
  * Example: https://leetcode.com/problems/remove-nth-node-from-end-of-list/

## 9. Memory Notes

* Extra memory overhead for pointers
* Not cache-friendly (nodes scattered in memory)

## 10. Arrays vs Linked Lists

| Feature           | Array      | Linked List    |
| ----------------- | ---------- | -------------- |
| Random access     | O(1)       | O(n)           |
| Insert/delete mid | O(n)       | O(1)*          |
| Memory layout     | Contiguous | Non-contiguous |
| Memory overhead   | Low        | Higher         |
| Cache friendly    | Yes        | No             |

*O(1) if node reference is known

## 11. Important Concepts

### Head and Tail

* Head = first node
* Tail = last node

Tracking tail allows O(1) append.

### Example Node (Python)

```python
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None
```

## 12. Common Bugs

* Losing references
* Incorrect pointer updates
* Off-by-one traversal errors