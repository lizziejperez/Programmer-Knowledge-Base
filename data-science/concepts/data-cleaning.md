<!-- Focus on:

null handling
duplicates
validation
transformation -->

# Data Cleaning

Data cleaning is the process of identifying and fixing issues in a dataset to improve its quality and usability.

## Table of Contents

* [Key Concepts](#key-concepts)
* [Common Issues](#common-issues)
* [Cleaning Techniques](#cleaning-techniques)
* [Examples](#examples)
* [Use Cases](#use-cases)
* [Best Practices](#best-practices)
* [Interview Relevance](#interview-relevance)

## Key Concepts

Data cleaning ensures that data is:

* Accurate
* Consistent
* Complete
* Usable for analysis

Poor data quality leads to incorrect insights and bad decisions.

## Common Issues

### Missing Values

Data fields may be empty or null.

Examples:

* Missing age values
* Blank categories

---

### Duplicates

The same record appears multiple times.

Example:

* Duplicate customer entries

---

### Inconsistent Formatting

Data is stored in different formats.

Examples:

* Dates: "01/02/2024" vs "2024-02-01"
* Text: "NY" vs "New York"

---

### Invalid Data

Values that do not make sense.

Examples:

* Negative age
* Future dates in past records

---

### Outliers

Values that are unusually high or low.

Example:

* A salary that is far outside the normal range

## Cleaning Techniques

### Handling Missing Values

Options:

* Remove rows with missing data
* Fill with default values (mean, median, mode)
* Use interpolation or estimation

---

### Removing Duplicates

Keep only unique records.

Example (Python):

```
df = df.drop_duplicates()
```

---

### Standardizing Formats

Convert data into a consistent format.

Examples:

* Standardize date formats
* Normalize text (lowercase, trimming spaces)

---

### Filtering Invalid Data

Remove or correct incorrect values.

Example:

* Remove negative values where not allowed

---

### Handling Outliers

Options:

* Remove extreme values
* Cap values within a range
* Investigate before removing

## Examples

### Python (Pandas)

```
df = df.dropna()
df = df.drop_duplicates()
df["date"] = pd.to_datetime(df["date"])
```

---

### SQL

```
SELECT DISTINCT *
FROM table;

DELETE FROM table
WHERE value IS NULL;
```

---

### Excel

* Remove duplicates tool
* Filter for blanks
* Use formulas to clean text (TRIM, LOWER)

## Use Cases

* Preparing datasets for analysis
* Cleaning survey or user data
* Financial and business reporting
* Machine learning preprocessing

## Best Practices

* Always inspect data before cleaning
* Keep a copy of raw data
* Document cleaning steps
* Validate results after cleaning
* Avoid removing data without understanding why

## Interview Relevance

Data cleaning is one of the most common tasks in data roles.

Common interview topics:

* Handling missing data
* Removing duplicates
* Data validation techniques
* Cleaning workflows

Typical question:

"How would you clean a messy dataset?"

Strong answer:

* Identify issues (missing, duplicates, invalid)
* Apply appropriate cleaning methods
* Validate the results
* Document the process