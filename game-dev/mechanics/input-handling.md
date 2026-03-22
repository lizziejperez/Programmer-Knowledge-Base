# Input Handling

Input handling converts player input into game actions.

## Table of Contents

* [Key Concepts](#key-concepts)
* [Common Approaches](#common-approaches)
* [Examples](#examples)
* [Use Cases](#use-cases)
* [Notes](#notes)

## Key Concepts

Input systems take raw input (keyboard, mouse, controller) and translate it into actions such as movement, jumping, or interaction.

Good input systems:

* Separate input from gameplay logic
* Map inputs to actions (Jump, Move, Interact)
* Support multiple input devices

## Common Approaches

### 1. Polling

Check input every frame.

* Simple and common in games
* Used in update loops

### 2. Event-Based Input

Respond to input events instead of checking continuously.

* More efficient
* Common in UI systems and modern frameworks

## Examples

### Unity (C# Polling Example)

```csharp
void Update() {
  float x = Input.GetAxis("Horizontal");

  if (Input.GetKeyDown(KeyCode.Space)) {
    Jump();
  }

}
```

### JavaScript Example (Event-Based)

```javascript
document.addEventListener("keydown", function(event) {
  if (event.code === "Space") {
    jump();
  }

  if (event.code === "ArrowLeft") {
    moveLeft();
  }

  if (event.code === "ArrowRight") {
    moveRight();
  }

});
```

## Use Cases

* Player movement and controls
* Jumping, attacking, and abilities
* UI interaction (buttons, menus)
* Camera control

## Notes

* Keep input handling separate from movement and physics logic
* Map inputs to actions instead of hardcoding keys
* Avoid mixing input logic with game state logic
* Consider supporting multiple input types (keyboard, controller)