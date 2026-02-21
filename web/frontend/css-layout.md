# CSS Layout

CSS layout determines how elements are positioned and arranged on a webpage.

Modern layout primarily relies on:

- Normal Flow
- Flexbox
- Grid
- Positioning
- Display properties

## 1. The Normal Document Flow

By default, elements follow **normal flow**:

- Block elements stack vertically
- Inline elements flow horizontally

Block elements take full width.

Inline elements only take the width of their content.

## 2. The Box Model

Every element is a rectangular box composed of:

```
+----------------------+
|      margin          |
|  +----------------+  |
|  |    border      |  |
|  |  +----------+  |  |
|  |  | padding  |  |  |
|  |  |  content |  |  |
|  |  +----------+  |  |
|  +----------------+  |
+----------------------+
```

Properties:

```css
width
height
padding
border
margin
```

### box-sizing
```css
box-sizing: content-box; /* default */
box-sizing: border-box;  /* recommended */
```

`border-box` includes padding and border inside width/height.

## 3. Display Property

Controls layout behavior.

```css
display: block;
display: inline;
display: inline-block;
display: flex;
display: grid;
display: none;
```
### inline-block

Allows width/height but stays inline.

## 4. Positioning

Controls how elements are positioned relative to other elements.

```css
position: static;   /* default */
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

| Position Value | Behavior Description |
|---------------|----------------------|
| `static` | Default positioning in normal document flow. |
| `relative` | Moves relative to its normal position. |
| `absolute` | Positioned relative to the nearest positioned ancestor. |
| `fixed` | Positioned relative to the viewport. |
| `sticky` | Switches between relative and fixed depending on scroll position. |

## 5. Flexbox (1-D Layout)

Used for layout in one direction (row OR column).

Enable:

```css
display: flex;
```

### Main Concepts

- Main axis
- Cross axis
- Flex container
- Flex items

### Common Properties

```css
justify-content: center;
align-items: center;
flex-direction: row | column;
gap: 1rem;
```

#### Example

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

Use Flexbox for:

- Navigation bars
- Centering content
- Row/column alignment

## 6. CSS Grid (2-D Layout)

Used for rows AND columns simultaneously.

Enable:

```css
display: grid;
Define Grid
grid-template-columns: 1fr 1fr 1fr;
grid-template-rows: auto;
gap: 1rem;
```

Example

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}
```

Use Grid for:

- Page layouts
- Dashboards
- Complex alignment systems

## 7. Width & Sizing Units

Common units:

- `px` — fixed pixels
- `%` — relative to parent
- `em` — relative to font-size
- `rem` — relative to root font-size
- `vh` / `vw` — viewport height/width
- `fr` — fraction (grid only)

## 8. Overflow

Controls what happens when content exceeds container.

```css
overflow: visible;
overflow: hidden;
overflow: scroll;
overflow: auto;
```

## 9. Z-Index & Stacking Context

Controls layering of positioned elements.

```css
z-index: 10;
```

Only works on positioned elements (not static).

## 10. Responsive Layout

Use:

- Flexbox
- Grid
- Percentage widths
- Media queries

Example:

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

## 11. Common Layout Patterns

- Centering with Flexbox
- Sidebar + Content layout (Grid or Flex)
- Responsive navigation bar
- Card grid layout

## When to Use What

| Tool        | Best For                   |
| ----------- | -------------------------- |
| Normal Flow | Basic documents            |
| Flexbox     | One-dimensional alignment  |
| Grid        | Two-dimensional layouts    |
| Position    | Overlays, popups, tooltips |

## Best Practices

- Use `box-sizing: border-box;`
- Prefer Flexbox and Grid over floats
- Avoid excessive absolute positioning
- Keep layout and spacing consistent
- Use responsive units