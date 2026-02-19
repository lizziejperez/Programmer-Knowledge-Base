# Linked Lists

A **linked list** is a linear data structure where each element (**node**) stores:

- **data**
- a **reference (pointer)** to the next node (and sometimes the previous node)

Unlike arrays, linked lists do **not** require contiguous memory.

## Key Idea

Nodes are connected like a chain:

```
[Data | Next] -> [Data | Next] -> [Data | Next] -> null
```

Because nodes can live anywhere in memory, insertion/removal can be efficient (no shifting).

## Types of Linked Lists

### Singly Linked List

Each node points to the next node.

```
head -> A -> B -> C -> null
```

### Doubly Linked List

Each node points to both next and previous nodes.

```
null <- A <-> B <-> C -> null
```

### Circular Linked List

Last node points back to the head.

```
A -> B -> C -> A
```

## Time Complexity

Let `n` be the number of nodes.

| Operation                    | Time |
|-----------------------------|------|
| Access by index (`get(i)`)  | `O(n)` |
| Search (unsorted)           | `O(n)` |
| Insert at head              | `O(1)` |
| Insert at tail*             | `O(1)` or `O(n)` |
| Insert in middle            | `O(n)` |
| Delete at head              | `O(1)` |
| Delete in middle            | `O(n)` |

\* Tail insertion is `O(1)` **only if** you store a tail pointer; otherwise you must traverse to the end (`O(n)`).

## Memory Notes

- Linked lists have **extra memory overhead** for pointers.
- Not cache-friendly compared to arrays (nodes are scattered in memory).

## Common Operations

### Traversal

Walk from head node to end:

```
current = head
while current != null:
    current = current.next
```

### Insert at Head (Singly)

New node becomes the head:

1. newNode.next = head
2. head = newNode

### Delete at Head

1. head = head.next

## Arrays vs Linked Lists

| Feature           | Array         | Linked List     |
|------------------|--------------|-----------------|
| Random access     | `O(1)`        | `O(n)`          |
| Insert/delete mid | `O(n)`        | `O(1)`*         |
| Memory layout     | Contiguous    | Non-contiguous  |
| Memory overhead   | Low           | Higher (pointers) |
| Cache friendly    | Yes           | No              |

\* `O(1)` only if you already have the node reference; finding it still costs `O(n)`.

## When to Use a Linked List

### Use a linked list when:

- You do many insertions/deletions near the front
- You don’t need random access by index
- The data size changes frequently

### Avoid linked lists when:

- You need fast indexing
- Performance and cache locality matter
- You can use a dynamic array instead (often better in practice)

## Real-World Uses

- Implementing stacks/queues (sometimes)
- Separate chaining in hash tables
- Undo/redo lists (doubly linked list)
- LRU cache internals (often doubly linked list + hashmap)

## Example Node (Conceptual)

Singly linked list node:

```python
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None
```

## Important Concepts

### Head and Tail

- **Head**: first node
- **Tail**: last node (tail.next = null)

Tracking a tail pointer can make appending `O(1)`.

### Common Bugs

- Losing references (node becomes unreachable)
- Not updating pointers correctly during insert/delete
- Off-by-one errors when traversing