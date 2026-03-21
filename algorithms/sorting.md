# Sorting Algorithms

Sorting algorithms re-arrange data into a specific order, usually ascending or descending.

## Table of Contents

* [Overview](#1-overview)
* [Comparison Summary](#2-comparison-summary)
* [Selection Sort](#3-selection-sort)
* [Bubble Sort](#4-bubble-sort)
* [Insertion Sort](#5-insertion-sort)
* [Merge Sort](#6-merge-sort)
* [Quick Sort](#7-quick-sort)
* [Heap Sort](#8-heap-sort)
* [Counting Sort](#9-counting-sort)
* [Radix Sort](#10-radix-sort)
* [When to Use What](#11-when-to-use-what)

## 1. Overview

Sorting is used to:

* organize data
* support efficient searching
* prepare data for display or further processing

Important comparison points:

* running time
* memory usage
* stability
* whether the algorithm is in-place

## 2. Comparison Summary

| Algorithm      | Best Case    | Average Case | Worst Case  | Stable | In-Place |
| -------------- | ------------ | ------------ | ----------- | ------ | -------- |
| Selection Sort | O(n²)        | O(n²)        | O(n²)       | No     | Yes      |
| Bubble Sort    | O(n)         | O(n²)        | O(n²)       | Yes    | Yes      |
| Insertion Sort | O(n)         | O(n²)        | O(n²)       | Yes    | Yes      |
| Merge Sort     | O(n log n)   | O(n log n)   | O(n log n)  | Yes    | No       |
| Quick Sort     | O(n log n)   | O(n log n)   | O(n²)       | No     | Yes      |
| Heap Sort      | O(n)         | O(n log n)   | O(n log n)  | No     | Yes      |
| Counting Sort  | O(n + k)     | O(n + k)     | O(n + k)    | Yes    | No       |
| Radix Sort     | O(d · f)     | O(d · f)     | O(d · f)    | Depends on helper sort | No |

## 3. Selection Sort

Selection sort repeatedly finds the smallest element in the unsorted portion and places it at the next sorted position.

### Algorithm

* Find the index of the smallest remaining element
* Swap it into the next sorted position
* Repeat until the list is sorted

Pseudocode:

```
for i = 0 to n - 2
    minIndex = i
    for j = i + 1 to n - 1
        if list[j] < list[minIndex]
            minIndex = j
    swap list[i] with list[minIndex]
```
### Notes

* Time: O(n²)
* Space: O(1)
* Stable: No
* In-place: Yes

## 4. Bubble Sort

Bubble sort repeatedly compares adjacent elements and swaps them if they are out of order.

### Algorithm

* Pass through the array left to right
* Swap adjacent out-of-order values
* After each pass, the largest remaining value moves to the end

Pseudocode:

```
for i = 0 to n - 2
    for j = 0 to n - 2 - i
        if list[j] > list[j + 1]
            swap list[j] with list[j + 1]
```
### Notes

* Time
  * Best case: O(n)
  * Worst case: O(n²)
* Space: O(1)
* Stable: Yes
* In-place: Yes

## 5. Insertion Sort

Insertion sort builds a sorted section from left to right by inserting each new element into its correct position.

### Algorithm

Pseudocode:
```
for i = 1 to n - 1
    temp = list[i]
    j = i
    while j > 0 and temp < list[j - 1]
        list[j] = list[j - 1]
        j = j - 1
    list[j] = temp
```
### Notes

* Time
  * Best case: O(n)
  * Average case: O(n²)
  * Worst case: O(n²)
* Space: O(1)
* Stable: Yes
* In-place: Yes

## 6. Merge Sort

Merge sort uses divide and conquer.

### Algorithm

* Split the list into two halves
* Recursively sort each half
* Merge the sorted halves

Pseudocode:

```
function mergesort(A)
    if len(A) > 1
        m = len(A) // 2
        L = mergesort(A[0...m-1])
        R = mergesort(A[m...len(A)-1])

        merge L and R back into A
```
### Notes

* Time
  * O(n log n) in all cases
  * Merge operation: O(n)  
* Space: O(n)
* Stable: Yes
* In-place: No

## 7. Quick Sort

Quick sort partitions the array around a pivot, then recursively sorts the left and right sides.

### Partition

```
partition(array, start, end)
    pivot = array[end]
    t = start
    for i = start to end - 1
        if array[i] <= pivot
            swap array[i] and array[t]
            t++
    swap array[t] and array[end]
    return t
```

### Quick Sort

```
quickSort(array, start, end)
    if start < end
        index = partition(array, start, end)
        quickSort(array, start, index - 1)
        quickSort(array, index + 1, end)
```

### Notes

* Time
  * Best/Average: O(n log n)
  * Worst: O(n²)
  * Partition: O(n)
* Space: O(1)
* Stable: No
* In-place: Yes

## 8. Heap Sort

Heap sort converts the data into a heap, then repeatedly extracts the root.

### Algorithm

* Build a max heap
* Swap the root with the last element
* Heapify the reduced heap
* Repeat until sorted

Pseudocode:

```
Convert complete binary tree (CBT) to max heap
For 1 = n to 2:
  Swap node 1 (root) w/ node i
  Max heapify root node on tree ignoring index i and up
```

### Notes

* Time
  * Best case (all elements identical): O(n) for heap construction
  * Average/Worst: O(n log n)
* Space: O(1)
* Stable: No
* In-place: Yes

## 9. Counting Sort

Counting sort works for non-negative integers in a known range.

### Algorithm

* Count occurrences of each value
* Convert counts into cumulative positions
* Place elements into output array
* Copy back if needed

Pseudocode:

`A` is a list of length `n` with maximum value `k`.

```
LOC = array of zeros of length k+1
ANEW = array of zeros of length n

// Count version of LOC
For i = 0 to n-1:
  LOC[A[i]] = LOC[A[i]] + 1

// Make LOC cumulative
For i = 1 to k:
  LOC[i] = LOC[i] + LOC[i-1]

// ANEW from LOC and A
For i = n-1 down to 0:
  ANEW[LOC[A[i]]-1] = A[i]
  LOC[A[i]]= LOC[A[i]] -1

// Copy ANEW to A
For i = 0 to n-1:
  A[i] = ANEW[i]
```

### Notes

* Time: O(n + k)
* Space: O(n + k)
* Stable: Yes
* In-place: No

## 10. Radix Sort

Radix sort sorts values digit by digit using a stable helper sort.

### Algorithm

* Sort by least significant digit
* Move to the next digit
* Repeat until all digits are processed

Pseudocode:

`A` is a list of integers

Each integer looks like: `x_d ... x_1`

```
For i = 1 to d:
  stable sort A using digit i
```

### Notes

* Time: O(d · f)
  * d = number of digits
  * f = running time of helper stable sort

## 11. When to Use What

* Use **Insertion Sort** for very small or nearly sorted inputs
* Use **Merge Sort** when stable O(n log n) behavior matters
* Use **Quick Sort** when average-case speed is important
* Use **Heap Sort** when in-place O(n log n) is needed
* Use **Counting Sort** or **Radix Sort** when the input format allows non-comparison sorting