# Queues

A **queue** is a linear data structure that follows **First In, First Out (FIFO)**.

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

* FIFO (First In, First Out)
* Enqueue at rear
* Dequeue from front

## 2. Time Complexity

| Operation | Time |
| --------- | ---- |
| Enqueue   | O(1) |
| Dequeue   | O(1) |
| Peek      | O(1) |
| Search    | O(n) |

## 3. Structure

```
Front → [1][2][3] ← Rear
```

## 4. Common Operations

### Enqueue

Add an element to the rear.

```
queue = [1, 2]
queue.append(3) → [1, 2, 3]
```

### Dequeue

Remove the front element.

```
queue = [1, 2, 3]
queue.pop(0) → [2, 3]
```

### Peek

View the front element.

```
queue[0]
```

## 5. Variants

* Circular queue
* Priority queue
* Deque (double-ended queue)

## 6. Use Cases

* Task scheduling
* BFS traversal
* Message queues
* Buffers

## 7. Advantages & Disadvantages

**Advantages**

* Fair ordering
* Efficient insert/remove

**Disadvantages**

* No random access

## 8. Interview Patterns

Common problem-solving patterns involving queues:

* **Breadth-first search (BFS)**: Traverse level-by-level

  * Example: https://leetcode.com/problems/binary-tree-level-order-traversal/

* **Sliding window (queue-based)**: Track elements within a window

  * Example: https://leetcode.com/problems/sliding-window-maximum/

* **Task scheduling / queue simulation**: Process items in order

  * Example: https://leetcode.com/problems/task-scheduler/