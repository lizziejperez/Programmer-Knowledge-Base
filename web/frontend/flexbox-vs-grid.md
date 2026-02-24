# Flexbox vs Grid

Flexbox and CSS Grid are modern layout systems used to control positioning and alignment in CSS.

They solve different layout problems.

# 1. Core Difference

| Flexbox | Grid |
|----------|------|
| One-dimensional layout | Two-dimensional layout |
| Controls rows OR columns | Controls rows AND columns |
| Content-driven | Layout-driven |
| Best for alignment | Best for structure |

# 2. When to Use Flexbox

Flexbox is ideal for:

- Navigation bars
- Centering content
- Horizontal or vertical alignment
- Small UI components
- Distributing space evenly

Example:

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

Flexbox works along:

- Main axis
- Cross axis

You control direction with:

```css
flex-direction: row;
flex-direction: column;
```

# 3. When to Use Grid

Grid is ideal for:

- Page layouts
- Dashboards
- Card systems
- Complex column/row structures
- Full-page design systems

Example:
```css
.container {
  display: grid;
  grid-template-columns: 250px 1fr;
  gap: 1rem;
}
```

Grid allows you to explicitly define:

- Rows
- Columns
- Areas
- Gaps

# 4. Conceptual Comparison

## Flexbox

Think:

    “Arrange items in a line.”

It handles:

- Alignment
- Distribution
- Spacing
- Reordering

It adapts naturally to content size.

## Grid

Think:

    “Design the page skeleton.”

You define:
- Exact columns
- Exact rows
- Named grid areas
- Overlapping elements

Grid is more structural and layout-first.

# 5. Alignment Comparison

| Feature              | Flexbox           | Grid               |
| -------------------- | ----------------- | ------------------ |
| Horizontal alignment | `justify-content` | `justify-content`  |
| Vertical alignment   | `align-items`     | `align-items`      |
| Gap spacing          | `gap`             | `gap`              |
| Item placement       | Order-based       | Explicit placement |

# 6. Combining Flexbox and Grid

They are not competitors — they are complementary.

Common pattern:

- Use **Grid** for page layout.
- Use **Flexbox** inside components.

Example:
```css
.page {
  display: grid;
  grid-template-columns: 250px 1fr;
}

.navbar {
  display: flex;
  justify-content: space-between;
}
```

# 7. Performance & Complexity

Both are performant and widely supported.

Grid may feel more complex initially because:

- You define explicit structure
- It has more properties

Flexbox is simpler for small layouts.

# 8. Decision Guide

Use Flexbox when:

- Layout is linear
- Content size drives structure
- You need quick alignment

Use Grid when:

- Layout is two-dimensional
- You need precise structure
- You’re building full page layouts

# Summary

| If You Need…              | Use     |
| ------------------------- | ------- |
| Align items in a row      | Flexbox |
| Center a component        | Flexbox |
| Create a full page layout | Grid    |
| Build a card grid         | Grid    |
| Sidebar + content layout  | Grid    |

**Flexbox** handles alignment well.

**Grid** handles structure well.

Modern CSS layout often uses both together.