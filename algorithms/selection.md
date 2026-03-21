# Selection Algorithms

Selection algorithms are used to find the k-th smallest or k-th largest element without fully sorting the data.

## Table of Contents

* [Overview](#1-overview)
* [Why Selection Matters](#2-why-selection-matters)
* [Approaches](#3-approaches)
* [Quickselect](#4-quickselect)
* [Median of Medians](#5-median-of-medians)
* [Use Cases](#6-use-cases)
* [Interview Patterns](#7-interview-patterns)

## 1. Overview

Selection problems ask for values like:

* minimum
* maximum
* median
* k-th smallest
* k-th largest

These are related to sorting, but full sorting is often unnecessary.

## 2. Why Selection Matters

If you only need one ranked element, sorting the whole array may do extra work.

Example:
To find the 3rd smallest value, you do not necessarily need the fully sorted list.

## 3. Approaches

Common approaches include:

* Full sort, then choose
* Partial selection
* Heap-based selection
* Partition-based selection

## 4. Quickselect

Quickselect is a partition-based algorithm related to quicksort.

### Idea

* Choose a pivot
* Partition the list
* Decide whether the target lies left, right, or at the pivot
* Recurse only into the relevant side

### Pseudocode

```
selectKth(A, L, R, k)
    index = choosePivot(A, L, R)
    swap A[index] and A[R]
    pivotIndex = partition(A, L, R)

    if k - 1 < pivotIndex
        return selectKth(A, L, pivotIndex - 1, k)
    else if k - 1 > pivotIndex
        return selectKth(A, pivotIndex + 1, R, k)
    else
        return A[pivotIndex]
```

### Running Time

* Best/Average case: O(n)
* Worst case: O(n²)

## 5. Median of Medians

Median of Medians is a pivot-selection strategy that guarantees good worst-case behavior.

### Idea

* Divide elements into groups of 5
* Sort each group
* Find each group median
* Recursively find the median of those medians
* Use that value as pivot

### Running Time

* Worst case: O(n)

This improves worst-case guarantees compared to naive quickselect.

## 6. Use Cases

* Finding medians
* Finding percentile cutoffs
* Top-k style problems
* Order statistics

## 7. Interview Patterns

Common problem-solving patterns involving selection algorithms:

* **K-th element problems**: Find ranked values without sorting everything
  * Example: https://leetcode.com/problems/kth-largest-element-in-an-array/

* **Top K problems**: Return the most frequent or largest/smallest K values
  * Example: https://leetcode.com/problems/top-k-frequent-elements/

* **Median problems**: Find middle values efficiently
  * Example: https://leetcode.com/problems/find-median-from-data-stream/