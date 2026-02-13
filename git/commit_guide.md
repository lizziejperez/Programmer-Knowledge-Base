# Conventional Commits Guide

Using a consistent commit style (like **Conventional Commits**) makes your history clean, easy to read, and useful if you ever automate changelogs later.

---

## Format
```
<type>(optional scope): <short description>
```

- **type** → what kind of change it is  
- **scope** → the part of the project it affects (optional, e.g. `readme`, `game`, `ui`)  
- **description** → short summary of the change  

---

## Common Commit Types
- **feat** → a new feature (e.g. new obstacle, new game mechanic)  
- **fix** → a bug fix (e.g. collision detection issue)  
- **docs** → documentation changes (README, comments, etc.)  
- **style** → code style (formatting, linting, not logic changes)  
- **refactor** → code restructuring (no new features or fixes)  
- **test** → adding or fixing tests  
- **chore** → maintenance (dependencies, configs, build tools)  

---

## Examples

**For a README update:**
```
docs(readme): add setup instructions and server shutdown note
```

**For a new game mechanic:**
```
feat(game): add jumping obstacle
```

**For a bug fix with collisions:**
```
fix(collision): correct hitbox detection for player
```

---

## Why Use This Convention?
This convention makes it easy to:
- Quickly scan commit history
- Understand the type of changes without reading more
- Automate versioning & changelogs if needed
