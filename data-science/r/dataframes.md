# Data Frames & Datasets

A data frame is a table-like structure where:
- Columns represent variables
- Rows represent observations

## Built-in Dataset Example

```r
head(trees)
```

Columns in trees:

- Girth
- Height
- Volume

## Accessing the Rows and Columns
### Columns
Select columns
1. using `$`:
    ```r
    trees$Girth
    ```
2. Using brackets
    ```r
    trees[["Girth"]]
    trees[, "Girth"]
    trees[, 1]     # by column index
    ```
### Rows
Select rows using brackets
```
trees[1, ]     # first row
trees[1:5, ]   # first 5 rows
```

### Both
Format:
```
dataframe[rows, columns]
```
Example:
```r
trees[1:5, "Volume"]
trees[1:5, 3]
```