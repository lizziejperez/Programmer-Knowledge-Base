# C# XML Documentation Comments Cheat Sheet

## Table of Contents

* [What Are XML Documentation Comments?](#what-are-xml-documentation-comments)
* [Basic Syntax](#basic-syntax)
* [Most Common Tags](#most-common-tags)

  * [`<summary>`](#summary)
  * [`<param>`](#param)
  * [`<returns>`](#returns)
  * [`<example>`](#example)
  * [`<remarks>`](#remarks)
  * [`<see>`](#see)
  * [`<seealso>`](#seealso)
* [Full Example](#full-example)
* [Best Practices](#best-practices)
* [When to Use XML Docs](#when-to-use-xml-docs)
* [When NOT to Use XML Docs](#when-not-to-use-xml-docs)
* [Pro Tips](#pro-tips)
* [Minimal Standard (Recommended)](#minimal-standard-recommended)
* [Quick Reference](#quick-reference)
* [Takeaways](#takeaways)

## What Are XML Documentation Comments?

XML documentation comments are structured comments in C# used to describe code elements such as classes, methods, and parameters.

They:

* Appear in IntelliSense tooltips
* Help other developers understand your code
* Can be used to generate documentation automatically

## Basic Syntax

```csharp
/// <summary>
/// Short description of what this code does.
/// </summary>
```

Use `///` (triple slash) directly above the code element.

## Most Common Tags

### `<summary>`

Describes what the method/class does.

```csharp
/// <summary>
/// Pauses the game and displays the pause menu.
/// </summary>
```

### `<param>`

Describes a parameter.

```csharp
/// <param name="sceneName">The name of the scene to load.</param>
```

### `<returns>`

Describes what the method returns.

```csharp
/// <returns>True if the game is paused, otherwise false.</returns>
```

### `<example>`

Provides an example usage.

```csharp
/// <example>
/// PauseMenuSystem.PauseGame();
/// </example>
```

### `<remarks>`

Adds additional notes or details.

```csharp
/// <remarks>
/// This method uses Time.timeScale to freeze gameplay.
/// </remarks>
```

### `<see>`

References another method, class, or type.

```csharp
/// <see cref="ResumeGame"/>
```

### `<seealso>`

Suggests related APIs.

```csharp
/// <seealso cref="PauseGame"/>
```

## Full Example

```csharp
/// <summary>
/// Toggles the pause state of the game.
/// </summary>
/// <remarks>
/// Uses Time.timeScale to freeze and resume gameplay.
/// </remarks>
/// <example>
/// pauseSystem.TogglePause();
/// </example>
public void TogglePause()
{
    if (isPaused)
        ResumeGame();
    else
        PauseGame();
}
```

## Best Practices

### ✅ Keep it concise

* One or two sentences is enough
* Focus on what the method does

### ✅ Use action-based descriptions

* “Pauses the game”
* “Loads the specified scene”

### ✅ Document public APIs

* Public methods
* Reusable systems
* Anything other developers will use

### ❌ Avoid over-documenting

* Don’t explain obvious code
* Don’t repeat the method name

Bad:

```csharp
/// <summary>
/// This method pauses the game.
/// </summary>
```

Better:

```csharp
/// <summary>
/// Pauses gameplay and shows the pause menu.
/// </summary>
```

## When to Use XML Docs

Use them when:

* Building reusable systems (like your Adventure Toolkit)
* Creating libraries or APIs
* Sharing code with others
* Preparing a professional portfolio

## When NOT to Use XML Docs

Avoid using XML documentation comments for:
- Private helper methods
- Obvious or self-explanatory code
- Internal implementation details

Use regular comments (`//`) instead.

## Pro Tips

* Write docs as if someone else will use your code
* Think: “What does someone need to know quickly?”
* Keep formatting consistent across your project

## Minimal Standard (Recommended)

At minimum, document:

* All public methods
* Any method with side effects (like pausing time)
* Systems intended for reuse

## Quick Reference

| Tag         | Purpose                  |
| ----------- | ------------------------ |
| `<summary>` | What it does             |
| `<param>`   | Parameter description    |
| `<returns>` | Return value description |
| `<remarks>` | Extra details            |
| `<example>` | Usage example            |
| `<see>`     | Inline reference         |
| `<seealso>` | Related references       |

## Takeaways

XML documentation comments:

* Improve usability of your code
* Make your projects look professional
* Help turn scripts into real tools

Use them consistently, but keep them simple.