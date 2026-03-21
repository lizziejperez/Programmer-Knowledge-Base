# Searching Algorithms

Searching algorithms determine whether a value exists in a data set and, if so, where it is located.

## Table of Contents

* [Overview](#1-overview)
* [Linear Search](#2-linear-search)
* [Binary Search](#3-binary-search)
* [Binary Search Tree (BST) Search](#4-binary-search-tree-bst-search)
* [Hash Lookup](#5-hash-lookup)
* [When to Use What](#6-when-to-use-what)

## 1. Overview

The best search algorithm depends on:

* whether the data is sorted
* whether random access is available
* how the data is stored
* whether preprocessing is allowed

## 2. Linear Search

Linear search checks each element one by one.

### Requirements

* No sorting required
* Works on arrays, linked lists, or general sequences

### Pseudocode

```
for i = 0 to n - 1
    if list[i] == x
        return i
return -1
```

### Running Times

* Best case: O(1)
* Worst case: O(n)
* Average case: O(n)

## 3. Binary Search

Binary search repeatedly halves the search space.

### Requirements

* Data must be sorted
* Random access structure required (such as an array)

### Pseudocode

```
binSearch(list, key)
    start = 0
    end = list.length - 1
    while end >= start
        middle = (start + end) / 2
        if list[middle] == key
            return middle
        else if list[middle] > key
            end = middle - 1
        else
            start = middle + 1
    return -1
```

### Running Times

* Best case: O(1)
* Worst case: O(log n)
* Average case: O(log n)

## 4. Binary Search Tree (BST) Search

BST search uses the tree ordering property.

### Requirements

* Tree must satisfy BST property
  * left subtree values < root
  * right subtree values > root

### Pseudocode

```
search(root, x)
    if root is null
        return -1
    if root.value == x
        return root
    if x < root.value
        return search(root.left, x)
    return search(root.right, x)
```

### Running Times

* Best case: O(1)
* Average case: O(log n)
* Worst case: O(n)

## 5. Hash Lookup

Hash lookup uses a hash function to map keys to positions.

### Requirements

* Data stored in a hash table
* Hash function maps keys to indices

### Pseudocode
```
compute hash index of key x
check bucket at that index
    if key exists
        return associated value
    otherwise
        return -1
```
### Running Times

* Best case: O(1)
* Average case: O(1)
* Worst case: O(n) due to collisions

## 6. When to Use What

* Use **Linear Search** when data is small or unsorted
* Use **Binary Search** when data is sorted and random access is available
* Use **BST Search** when data is stored in a binary search tree
* Use **Hash Lookup** when fast average-case access is the priority