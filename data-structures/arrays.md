# Arrays

An array is a data structure that stores elements in **contiguous memory locations** and allows **indexed access**.

## Key Characteristics

- Fixed or dynamic size (depending on language)
- Indexed (usually 0-based)
- Contiguous memory layout
- Fast random access
- Homogeneous elements (in statically typed languages)

## Basic Concept

If an array starts at memory address `A`, and each element takes `k` bytes:

```
Address of arr[i] = A + (i × k)
```

This is why arrays support **`O(1)` access time**.

## Time Complexity

| Operation         | Time Complexity |
| ----------------- | --------------- |
| Access (`arr[i]`)   | `O(1)`            |
| Update            | `O(1)`            |
| Search (unsorted) | `O(n)`            |
| Insert (end)*     | `O(1)` amortized  |
| Insert (middle)   | `O(n)`            |
| Delete (end)           | `O(1)`            |
| Delete (middle)           | `O(n)`            |

* For dynamic arrays like Python lists or JavaScript arrays.

## Static vs Dynamic Arrays

### Static Arrays

- Fixed size
- Size determined at creation
- Cannot grow

Example (C):

```c
int arr[5] = {1, 2, 3, 4, 5};
```

### Dynamic Arrays

- Resize automatically
- Allocate new memory when capacity exceeded
- Copy elements to new larger array

Examples:

- Python `list`
- JavaScript `Array`
- C++ `vector`
- Java `ArrayList`

## Memory Model

Arrays are stored in contiguous memory:

```makefile
Index:   0    1    2    3
Value:  [10] [20] [30] [40]
```

This allows:

- Fast indexing
- Efficient cache usage

But makes:

- Insertions expensive (shifting required)

## Common Operations

### Traversal

```python
for i in range(len(arr)):
    print(arr[i])
```

### Insertion at End

```python
arr.append(5)
```

Amortized `O(1)`

### Insertion at Index

```python
arr.insert(2, 99)
```

Requires shifting → `O(n)`

### Deletion

```python
arr.pop()      # O(1)
arr.pop(2)     # O(n)
```
## Multidimensional Arrays

Arrays can store other arrays.

Example: 2D array (matrix)

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6]
]
```

Access:
```python
matrix[row][column]
```

Time complexity for access remains `O(1)`.

## Arrays vs Linked Lists

| Feature        | Array      | Linked List    |
| -------------- | ---------- | -------------- |
| Random Access  | `O(1)`       | `O(n)`           |
| Insert/Delete  | `O(n)`       | `O(1)`*          |
| Memory Layout  | Contiguous | Non-contiguous |
| Cache Friendly | Yes        | No             |

* If node reference is known.

## Common Use Cases

- Storing collections of data
- Implementing stacks/queues
- Lookup tables
- Dynamic programming tables
- Matrices and grids

## Advantages

- Fast random access
- Simple structure
- Memory efficient (no pointer overhead)
- Cache friendly

## Disadvantages

- Expensive insert/delete in middle
- Fixed size (static arrays)
- Requires contiguous memory block

## Important Concepts

### Amortized Analysis

Dynamic arrays grow by resizing (usually doubling capacity).

Resizing is expensive (`O(n)`), but happens infrequently.

This leads to **amortized `O(1)` append time**.

Amortized means:
Some operations are expensive, but when averaged over many operations, the cost per operation is constant.

### Bounds Checking

Bounds checking is the runtime verification that an index is within the valid range of an array (`0 ≤ index < length`), preventing illegal memory access.

Some languages:

- Python, Java, C# → bounds checked
- C → not bounds checked (can cause undefined behavior)

## When to Use Arrays

Use arrays when:

- You need fast indexing
- Data size is known or stable
- You don’t need frequent middle insertions
- Cache performance matters