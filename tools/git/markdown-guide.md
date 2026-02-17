# Formatting Guidelines

## Table of Content
1. [Headers](#headers)
2. [Links](#links)
3. [Code](#code)
5. [File Naming](#file-naming)
6. [Math](#math)
7. [Font Styles](#font-styles)
8. [Lists](#lists)
9. [Tables](#tables)

## Headers
- Use `#` for file title
- Use `##` for main sections
- Use `###` for subsections
- Use `####` for minor subsections (avoid going deeper)

## Links
Links to headers:
```markdown
[Headers link](#headers)

[File Naming link](#file-naming)
```
[Headers link](#headers)

[File Naming link](#file-naming)

Links to websites: 
```markdown
[Google link](https://www.google.com/)
```
[Google link](https://www.google.com/)

## Code
### Blocks
Use triple backticks with language specified.
### In-line
```markdown
The `code` is in-line.
```
The `code` is in-line.

## File Naming
- lowercase
- hyphen-separated
- no spaces

## Math

### Block math:

Use `$$ ... $$` for block equations

Example:
```markdown
$$
\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i
$$
```
$$
\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i
$$

## Font Styles

### Bold
```markdown
**Bold**
```
**Bold**

### Italic
```markdown
*Italic*
```
*Italic*

### Bold & Italic
```markdown
***Bold & Italic***
```
***Bold & Italic***

## Lists

### Ordered
```markdown
1. item one
2. item two
    1. item three
```
1. item one
2. item two
    1. item three

### Unordered
```markdown
- A
- B
    - C
```
- A
- B
    - C

## Tables
```markdown
| column 1 | column 2 |
| --- | --- |
| A  |  B |
```
| column 1 | column 2 |
| --- | --- |
| A |  B |
