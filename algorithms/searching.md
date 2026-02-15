# Searching Algorithms

1. [Linear Search](#linear-search)
2. [Binary Search](#binary-search)
3. [Binary Search Tree (BST) Search](#binary-search-tree-bst-search)
4. [Hash Lookup](#hash-lookup)

## Linear Search

### Pseudocode
- Looking for a value in a list, we loop through all the elements in the list
- If we find the element, we return its index in the list
- If never found the element, return -1

### Running Times
- Best Case: Find `x` at index `0 = θ(1)`
- Worst Case: `θ(n)`
- Average Case: `θ(n)`

## Binary Search

### Requirements
- The list must be sorted.
- Random access structure (like an array).

### Pseudocode
- Set low = 0 and high = n - 1
- While low ≤ high:
  - mid = (low + high) / 2
  - If list[mid] == x → return mid
  - If x < list[mid] → search left half (high = mid - 1)
  - Else → search right half (low = mid + 1)
- If not found → return -1

#### Example
```
binSearch( list, key )
  start = 0
	end = list.length - 1
	while( end >= start )
	  middle = ( start + end ) / 2
		if ( list[middle] == key )
		  return middle // key found
    else if ( list[middle] > key )
		  end = middle - 1; // search left
    else
		  start = middle + 1 // search right
  return -1 // key not found
```
		
### Running Times
- Best Case: Find value at the middle `= θ(1)`
- Worst Case: Value is never found `= θ(log⁡(n))`
- Average Case: `θ(log⁡(n))`

## Binary Search Tree (BST) Search

### Requirements
- Tree satisfies BST property:
  - Left subtree < root
  - Right subtree > root

### Pseudocode
- Start at root
- If `root` is null → return -1
- If `root.value == x` → return node
- If `x < root.value` → search left subtree
- Else → search right subtree

### Running Times
- Best Case: `θ(1)`
- Average Case: `θ(log n)`
- Worst Case: `θ(n)`  (unbalanced tree)


## Hash Lookup

### Requirements
- Data stored in a hash table.
- A hash function maps keys to indices.

### Pseudocode
- Compute hash index of key `x`
- Check bucket at that index
  - If key exists → return associated value / index
  - If not found → return -1

### Running Times
- Best Case: `θ(1)`
- Average Case: `θ(1)`
- Worst Case: `θ(n)`  (due to collisions)
