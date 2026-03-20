# Heaps

A **heap** is a specialized tree-based data structure that satisfies the **heap property**.

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

* Complete binary tree
* Parent-child ordering property
* Efficient access to the minimum or maximum element

## 2. Time Complexity

| Operation  | Time     |
| ---------- | -------- |
| Insert     | O(log n) |
| Extract    | O(log n) |
| Peek       | O(1)     |
| Build Heap | O(n)     |

## 3. Structure

Min Heap example:

```
  10
 /  \
20   30
```

In a min heap, each parent is less than or equal to its children.

Heaps are commonly implemented using arrays.

For a node at index `i`:

* Parent = `(i - 1) // 2`
* Left child = `2i + 1`
* Right child = `2i + 2`

## 4. Common Operations

### Insertion

Insert a new value while maintaining the heap property.

Steps:

* Add the new value at the end
* Compare it with its parent
* Swap upward until the heap property is restored

Python example:

```
import heapq

heap = []
heapq.heappush(heap, 10)
heapq.heappush(heap, 5)
heapq.heappush(heap, 20)
```

### Extract

Remove the root element (minimum in a min heap or maximum in a max heap).

Steps:

* Replace the root with the last element
* Remove the last element
* Swap downward until the heap property is restored

Python example:

```
heapq.heappop(heap)
```

### Peek

Access the root element without removing it.

Python example:

```
heap[0]
```

### Build Heap

Convert an unordered array into a valid heap.

Python example:

```
heap = [20, 5, 30, 10]
heapq.heapify(heap)
```

## 5. Variants

### Min Heap

The smallest element is always at the root.

Properties:

* Parent ≤ children
* Useful when repeatedly accessing the minimum element

### Max Heap

The largest element is always at the root.

Properties:

* Parent ≥ children
* Useful when repeatedly accessing the maximum element

Python note:

Python’s `heapq` module provides a min heap by default. A max heap can be simulated by inserting negative values.

### Binary Heap

The most common heap implementation.

Properties:

* Complete binary tree
* Usually stored in an array
* Supports efficient insert and extract operations

### Priority Queue

A priority queue is an abstract data structure often implemented using a heap.

Properties:

* Elements are processed by priority instead of insertion order
* Common in scheduling and pathfinding algorithms

## 6. Use Cases

* Priority queues
* Scheduling systems
* Dijkstra’s algorithm
* Heap sort

## 7. Advantages & Disadvantages

**Advantages**

* Efficient priority access
* Good for dynamic datasets

**Disadvantages**

* No fast search
* Not ideal for ordered traversal

## 8. Interview Patterns

Common problem-solving patterns involving heaps:

* **Top K elements**: Find largest or smallest K elements efficiently

  * Example: https://leetcode.com/problems/top-k-frequent-elements/

* **Heap as priority queue**: Always process highest or lowest priority first

  * Example: https://leetcode.com/problems/kth-largest-element-in-an-array/

* **Merging sorted structures**: Combine multiple sorted inputs

  * Example: https://leetcode.com/problems/merge-k-sorted-lists/

* **Streaming / running median**: Maintain the median of dynamic data

  * Example: https://leetcode.com/problems/find-median-from-data-stream/