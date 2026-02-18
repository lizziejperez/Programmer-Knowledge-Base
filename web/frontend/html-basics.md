# HTML Basics

HTML (HyperText Markup Language) defines the **structure** of a webpage.

## Basic Structure

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

Key Parts

- `<!DOCTYPE html>` → Declares HTML5
- `<html>` → Root element
- `<head>` → Metadata (not visible)
- `<body>` → Visible page content

## How HTML Works

- HTML uses elements
- Elements are made of tags

Most elements have:
1. Opening tag
2. Content
3. Closing tag

```html
<p>This is a paragraph.</p>
```

Some elements are **self-closing (void elements)**:

```html
<img src="image.jpg" alt="description">
<input type="text">
```

## Anatomy of an Element

```html
<a href="https://example.com" target="_blank">Visit</a>
```

- `<a>` → tag name
- `href`, `target` → attributes
- `"https://example.com"` → attribute value
- `Visit` → content

## Block vs Inline Elements

### Block Elements

These elements: 

- Take full width
- Start on a new line

Examples:
- `<div>`
- `<p>`
- `<h1>–<h6>`
- `<section>`

### Inline Elements

These elements:

- Only take as much width as needed
- Do NOT start on a new line

Examples:
- `<span>`
- `<a>`
- `<strong>`
- `<em>`

## Semantic HTML

Semantic elements describe **meaning**, not just layout.

| Tag         | Purpose             |
| ----------- | ------------------- |
| `<header>`  | Top section         |
| `<nav>`     | Navigation          |
| `<main>`    | Main content        |
| `<section>` | Group of content    |
| `<article>` | Independent content |
| `<footer>`  | Bottom section      |

Example:
```html
<header>
  <h1>My Website</h1>
</header>

<main>
  <section>
    <article>
      <h2>Blog Post</h2>
      <p>Content here...</p>
    </article>
  </section>
</main>
```

Semantic HTML improves:

- Accessibility
- SEO
- Code readability

## Attributes

Attributes add extra information to elements.

Common attributes:

| Attribute | Used For          |
| --------- | ----------------- |
| `id`      | Unique identifier |
| `class`   | Grouping elements |
| `src`     | File source       |
| `href`    | Link destination  |
| `alt`     | Image description |
| `type`    | Input type        |

Example:

```html
<p id="intro" class="highlight">
  Welcome!
</p>
```

## Common Tags

| Tag           | Purpose          |
| ------------- | ---------------- |
| `<h1>`–`<h6>` | Headings         |
| `<p>`         | Paragraph        |
| `<a>`         | Link             |
| `<img>`       | Image            |
| `<div>`       | Block container  |
| `<span>`      | Inline container |
| `<ul>`        | Unordered list   |
| `<ol>`        | Ordered list     |
| `<li>`        | List item        |
| `<input>`     | User input       |
| `<button>`    | Button           |

## Lists

### Unordered List

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

### Ordered List

```html
<ol>
  <li>First</li>
  <li>Second</li>
</ol>
```

### Description List

```html
<dl>
  <dt>HTML</dt>
  <dd>Markup language</dd>
</dl>
```

## Links

```html
<a href="https://example.com">Visit</a>
```

## Images

```html
<img src="image.jpg" alt="description">
```

`alt` is required for accessibility.

## Forms

```html
<form action="/submit" method="POST">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">

  <input type="email" name="email">
  <input type="password" name="password">

  <textarea name="message"></textarea>

  <select name="choice">
    <option value="1">Option 1</option>
    <option value="2">Option 2</option>
  </select>

  <button type="submit">Submit</button>
</form>
```

Key concepts:
- `action` → where data goes
- `method` → GET or POST
- `name` → how backend reads values

## Tables

```html
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Lizzie</td>
      <td>27</td>
    </tr>
  </tbody>
</table>
```

## Meta Tags

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Page description">
```

## Accessibility Basics

- Always use `alt` for images
- Use `<label>` with inputs
- Use semantic elements
- Don’t rely only on color

Example:

```html
<label for="email">Email</label>
<input type="email" id="email">
```

## Comments
```html
<!-- single line comment -->

 <!--
    multi-line
    comment
 -->
```

## Best Practices

- Indent consistently
- Use semantic HTML
- Close all tags
- Keep structure separate from styling (CSS)
- Keep behavior separate (JavaScript)