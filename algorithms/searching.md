# Searching Algorithms

1. [Linear Search](#linear-search)
2. [Binary Search](#binary-search)

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

### Pseudocode
Precondition: list is sorted
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
- Worst Case: Value is never found `= θ(log⁡n )`
- Average Case: `θ(log⁡(n))`
