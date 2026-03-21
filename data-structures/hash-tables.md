# Hash Tables

A **hash table** stores key-value pairs using a **hash function** to map keys to indices.

## Table of Contents

* [Key Characteristics](#1-key-characteristics)
* [Time Complexity](#2-time-complexity)
* [Structure](#3-structure)
* [Collision Handling](#4-collision-handling)
* [Common Operations](#5-common-operations)
* [Use Cases](#6-use-cases)
* [Advantages & Disadvantages](#7-advantages--disadvantages)
* [Interview Patterns](#8-interview-patterns)

## 1. Key Characteristics

* Key-value mapping
* Fast average lookup
* Uses a hash function

## 2. Time Complexity

| Operation | Time |
| --------- | ---- |
| Insert    | O(1) |
| Search    | O(1) |
| Delete    | O(1) |

Worst case: O(n)

## 3. Structure

A hash table stores data in an **array of buckets**, where each key is mapped to an index using a hash function.

Steps:

1. Compute hash of the key
2. Convert hash to an index (using modulo)
3. Store the value at that index

Example:

```id="hash-structure"
key = "cat"
hash(key) → 12345
index = 12345 % size → 5
```

Internal layout:

```
Index → Value
0     → null
1     → null
2     → (dog, 7)
3     → null
4     → null
5     → (cat, 3)
```

A good hash function should:

* Distribute keys evenly
* Minimize collisions
* Be fast to compute

## 4. Collision Handling

Collisions occur when two keys map to the same index.

Common methods:

* Chaining (linked lists)
* Open addressing (probing)

### Chaining

Store multiple elements at the same index using a list (or linked list).

Example:

```
Index 5 → [(cat, 3), (bat, 8)]
```

Advantages:

* Simple to implement
* Handles many collisions well

Disadvantages:

* Slower lookups if many elements collide

### Open Addressing

Find another empty slot using a probing strategy.

Common methods:

* **Linear probing**: Check next index
* **Quadratic probing**: Jump by increasing steps
* **Double hashing**: Use a second hash function

Example (linear probing):

```
Index 5 occupied → try 6 → try 7 → insert
```

Advantages:

* No extra memory for lists

Disadvantages:

* Clustering can occur
* Performance degrades as table fills

## 5. Common Operations

### Insert

Steps:

1. Compute hash and index
2. Handle collision if needed
3. Store key-value pair

Example:

```python
d = {}
d["cat"] = 3
```

### Search

Steps:

1. Compute hash and index
2. Check value at index
3. If collision, search through bucket

Example:

```python
value = d["cat"]
```

### Delete

Steps:

1. Locate key using hash
2. Remove entry

Example:

```python
del d["cat"]
```

### Resize (Rehashing)

When the table becomes too full:

1. Create a larger table
2. Recompute indices for all keys
3. Insert into new table

This keeps operations efficient (amortized O(1))

## 6. Use Cases

* Dictionaries / maps
* Caching systems
* Database indexing
* Frequency counting

## 7. Advantages & Disadvantages

**Advantages**

* Very fast average access
* Flexible key types

**Disadvantages**

* Collisions can degrade performance
* Memory overhead

## 8. Interview Patterns

Common problem-solving patterns involving hash tables:

* **Frequency counting**: Count occurrences of elements efficiently

  * Example: https://leetcode.com/problems/two-sum/

* **Hash set lookup**: Fast existence checking

  * Example: https://leetcode.com/problems/contains-duplicate/

* **Mapping relationships**: Store and retrieve key-value relationships

  * Example: https://leetcode.com/problems/group-anagrams/

* **Prefix sums with hashmap**: Optimize subarray problems

  * Example: https://leetcode.com/problems/subarray-sum-equals-k/