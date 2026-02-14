# R Basics
## Comments
```r
# this is a comment in R
```
## Variables
R uses `<-` for assignment (preferred style).
```r
x <- 5
```
`=` also works, but `<-` is conventional.

## Vectors
Create a numeric vector:
```r
y <- c(3, 5, 2)
```
Check length:
```r
length(y)
```

## Basic Operations
### Binary Operations
```r
4+3            # Sumation
2*7            # Product
6/3            # Division
2**3           # Power
2^3
65%%3          # Remainder
```
### Methods
```r
sqrt(9)        # Square root
mean(y)        # Mean
var(y)         # Sample variance
```
## Sampling
Simple random sample:
```r
sample(y, 1)
```

Default arguments:

- replace = FALSE

- prob = NULL

With replacement:
```r
sample(y, 1, replace = TRUE)
```

## Loops
### For Loop
```r
for (i in y) {
  print(i)
}
```
### While Loop
```r
while (condition) {
  # code to execute
}
```
## Conditionals
```r
if (x > 3) {
  print("Greater than 3")
} else {
  print("3 or less")
}
```

The condition must evaluate to `TRUE` or `FALSE`.

Use `==` for equality comparison.

Use `&` for AND.

Use `|` for OR.

Use `!` for NOT.

## Functions
```r
square <- function(x) {
  return(x^2)
}
```

## Concatenate and Print
Use:
- `print()` → debugging / inspecting objects
- `cat()` → user-friendly output formatting

### `print()`
Outputs text and variables to the console with quotes and output numbering (e.g. `[1]`).

```r
print("Hello")
# output: [1] "Hello"
```

### `cat()`
Outputs text and variables to the console without quotes or `[1]`.

```r
cat(..., sep = " ", end = "\n")
```
Arguments
- ... → values to print
- sep → separator between values (default = space)
- end → string appended at the end (default = newline)

Example:
```r
x <- 5
cat("The value of x is", x)
# output: The value of x is 5
```

## Histogram (`hist()`)

Creates a histogram of numeric data.

### Recall

A histogram shows the frequency distribution of continuous numerical data by grouping data points into equal ranges. It uses connected bars to display the shape, center, spread, and skewness of a dataset.

### Basic Syntax

```r
hist(x)
```
`x` must be a numeric vector.

## `qt()` - t-Distribution Quantile Function

Returns the quantile (critical value) from the t-distribution.

### Syntax

```r
qt(p, df)
```
Arguments
- `p` → probability (between 0 and 1)
- `df` → degrees of freedom

### What It Does
`qt(p, df)` returns the value `t` such that:
`P(T ≤ t) = p` where `T` follows a t-distribution with `df` degrees of freedom.

## `rep()` - Repeat Elements
Repeats values in a vector.
```r
x <- c(1, 2, 3)

rep(x, times=2) # times → number of times to repeat the entire vector
# output: 1 2 3 1 2 3

rep(x, each=2) # each → number of times to repeat each element
# output: 1 1 2 2 3 3

rep(x, length.out = 8) # length.out → desired total length of output
# output: 1 2 3 1 2 3 1 2
```