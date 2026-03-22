# Animation Basics

Animations change visual properties over time (position, rotation, scale, sprite frames, etc.).

## Table of Contents

* [Key Concepts](#key-concepts)
* [Core Components](#core-components)
* [Setup (Unity)](#setup-unity)
* [Examples](#examples)
* [Use Cases](#use-cases)
* [Common Mistakes](#common-mistakes)
* [Notes](#notes)

## Key Concepts

Animations control how objects visually change over time.

They are often used to represent movement, actions, and feedback in a game.

## Core Components

Animation systems typically include:

* **Animation Clip**: recorded animation data (the motion)
* **Animator Controller**: state machine that plays animations
* **Parameters**: variables that control transitions (bool, int, float, trigger)
* **Blend Trees**: blend animations smoothly based on values (e.g., speed)

## Setup (Unity)

Basic animation setup:

1. Create animation clips (Idle, Walk, Jump)
2. Create an Animator Controller
3. Add states (Idle, Walk, Jump)
4. Add transitions between states
5. Add parameters (e.g., speed, isGrounded, jump trigger)

## Examples

### Unity Example (C#)

```
public class PlayerAnim : MonoBehaviour
{
    Animator animator;

    void Awake()
    {
        animator = GetComponent<Animator>();
    }

    void Update()
    {
        float speed = Mathf.Abs(Input.GetAxisRaw("Horizontal"));
        animator.SetFloat("speed", speed);

        if (Input.GetKeyDown(KeyCode.Space))
            animator.SetTrigger("jump");
    }
}
```

When to Use What
- `SetBool("isGrounded", true/false)` → persistent state
- `SetTrigger("jump")` → one-time action
- `SetFloat("speed", value)` → blending / movement speed

### JavaScript Example (Simple Animation Loop)

```
let x = 0;

function update() {
    x += 2;
    document.getElementById("player").style.transform =
        "translateX(" + x + "px)";

    requestAnimationFrame(update);
}

update();
```

This moves an element smoothly across the screen using a frame loop.

## Use Cases

* Character movement (idle, walk, jump)
* UI animations (buttons, transitions)
* Visual feedback (damage, effects)
* Camera movement and transitions

## Common Mistakes

* Using too many triggers (hard to debug)
* Conflicting transition conditions
* Not managing animation state properly
* Forgetting to handle transitions like landing
* Coupling animation logic too tightly with gameplay

## Notes

* Gameplay logic should decide state, animation should reflect it
* Animation events can call functions, but should be used sparingly
* Use Blend Trees for smooth movement transitions