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
### Memory Space
θ(1)

### Running Time
T(n)= θ(n^2)

### Stable? No

### In-Place? Yes

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

### Memory Space
θ(1)

###	Running Time
- Worst Case (need to sort through all sub-lists): T(n)=θ(n^2 )
- Best Case (list is already sorted): T(n)=θ(n)

### Stable? Yes

### In-Place? Yes

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
### Memory Space
θ(1)
### Running Time
- Worst Case (swap every time): T(n)=θ(n^2 )
- Best Case (no swaps):  T(n)=θ(n)
- Average Case (half of possible swaps occur): T(n)=θ(n^2)
### Stable? Yes
### In-Place? Yes


# Merge Sort

### Algorithm
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
###	Running Times
- Merge operation: Θ(n)
- Merge sort: Θ(n∗lg⁡n) for all cases
		
### Space: Θ(n)
### In place? No
### Stable? Yes


# Quick Sort
# Heap Sort
# Counting Sort
# Radix Sort
