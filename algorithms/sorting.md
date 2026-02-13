# Selection Sort
This sort keeps finding the smallest element and placing it in the growing sorted part (left side)

## Algorithm
- Find index of smallest element
- Swap w/ list[0] => now list[0] is sorted
- Repeat for following unsorted indexes

```
For i = 0 to n-2
  minIndex = i
  For j = i+1 to n-1
    if list[j] < list[minIndex]
      minIndex = j
  swap list[i] with list[minIndex]
```
## Stats
Memory Space | Running Time
--- | --- |
θ(1) | θ(n^2)

Stable? |  In-place?
--- | --- |
No | Yes

# Bubble Sort

## Algorithm
- Pass through the list (left to right), comparing adjacent elements
- If out of order, swap
- Repeat, but decrease the ending index by 1, until ending index is 0

Note: After each pass, the next largest value will bubble to the right most index

```
For i = 0 to n – 2, increasing by 1 each time
  For each j from 0 to n-2-i, increasing by 1 each time
	  If value at index j is greater than value at index j+1
		  Swap value at index j with value at index j+1
```

## Stats
Memory Space | Running Time
--- | --- |
θ(1) | Worst Case (need to sort through all sub-lists): θ(n^2)
-- | Best Case (list is already sorted): θ(n)

Stable? |  In-place?
--- | --- |
Yes | Yes

# Insertion Sort

## Algorithm
```
for i = 1 to list.len-1
  j = i
	temp = list[i]           
	while ( j != 0 and temp < list[j-1] )
    list[j] = list[j-1] // shift list[j-1] to the right
    j = j-1
    list[j] = temp
```

## Stats
Memory Space | Running Time
--- | --- |
θ(1) | Worst Case (swap every time): θ(n^2)
-- | Best Case (no swaps):  T(n)=θ(n)
-- | Average Case (half of possible swaps occur): θ(n^2)

Stable? |  In-place?
--- | --- |
Yes | Yes

# Merge Sort

### Pseudocode
- If the array has only one element (or is empty), it is already sorted
- Merge sort the left half of the array
- Merge sort the right half of the array
- Merge the two sorted half-arrays into one sorted array
		
```
function mergesort(A)
  if len(A) > 1
    m = len(A) // 2
    L = mergesort(A[0,…,m-1])
    R = mergesort(A[m,…,len(A)-1])
    // Merge L and R
    i,j,k = 0
    while i < len(L) and j < len(R)
      if L[i] <= R[j]
        A[k] = L[i]
        i+=1
        k+=1
      else
        A[k] = R[j]
        j+=1
        k+=1
    end
    while i < len(L)
      A[k] = L[i]
      i+=1
      k+=1
    end
		while j < len(R)
		  A[k] = R[j]
      j+=1
      k+=1
    end
  end
end
```

## Stats
Memory Space | Running Time
--- | --- |
Θ(n) | Merge operation: Θ(n)
-- | Merge sort: Θ(n∗lg⁡n) for all cases

Stable? |  In-place?
--- | --- |
Yes | No

# Quick Sort

## Pseudocode

### Partition
```
partition( array, start, end )
  pivot = arr[end], t = start
  for i = start to end –1
    if arr[i] <= pivot
      swap arr[i] and arr[t]
      t++
  swap arr[t] and arr[end]
  return t
```
### Quick Sort
```
quickSort( array, start, end )
  if start < end
    index = partition( array, start, end )
    quickSort( array, start, index -1 )
    quickSort( array, index + 1, end )
```

## Stats
Memory Space | Running Time
--- | --- |
Θ(1) | Best Case & Average Case: Θ(n*lg(n))
-- | Worst Case: Θ(n^2)
-- |  Partition: Θ(n)

Stable? |  In-place?
--- | --- |
No (b/c of swap at end of partition) | Yes

# Heap Sort

## Algorithm
```
Convert complete binary tree (CBT) to max heap
For 1 = n to 2:
  Swap node 1 (root) w/ node i
  Max heapify root node on tree ignoring index i and up
```
## Stats
Memory Space | Running Time
--- | --- |
Θ(1) | Best Case (all elements identical): Θ(n)
-- | Worst Case: Θ(n*lg(n))

Stable? |  In-place?
--- | --- |
No | Yes

# Counting Sort
Sorts a list `A` of non-negative integers

## Pseudocode
`A` is a list of length `n` with maximum value `k`
```
LOC = array of zeros of length k+1
ANEW = array of zeros of length n

// Count version of LOC
for i = 0 to n-1
  LOC[A[i]] = LOC[A[i]] + 1
end

// Make LOC cumulative
for i = 1 to k
  LOC[i] = LOC[i] + LOC[i-1]
end

// ANEW from LOC and A
for i = n-1 down to 0
  ANEW[LOC[A[i]]-1] = A[i]
  LOC[A[i]]= LOC[A[i]] -1
end

// Copy ANEW to A
for i = 0 to n-1
  A[i] = ANEW[i]
end
```

## Stats
Memory Space | Running Time
--- | --- |
Θ(n+k) | Average Case: Θ(n+k)
`k` = max value in list `A`
`n` = # element in list `A`

Stable? |  In-place?
--- | --- |
Yes | No

# Radix Sort

## Pseudocode
`A` is a list of integers
Each integer looks like x_d ... x_1
```
for i = 1 to d
  stable sort A using digit i
```

## Stats
Memory Space | Running Time
--- | --- |
? | Θ(d*f)
`d` = width of largest number
`f` is running time of helper sorting algorithm
