# State Machines

A state machine is a way to organize behavior by switching between a small set of named states.

## Table of Contents

* [Key Concepts](#key-concepts)
* [Why Use State Machines](#why-use-state-machines)
* [Core Idea](#core-idea)
* [Example](#example)
* [Use Cases](#use-cases)
* [Common Mistakes](#common-mistakes)
* [Related Topics](#related-topics)

## Key Concepts

A state machine models behavior using a limited set of states.

Example states:

* Idle
* Walk
* Run
* Jump
* Attack

At any moment, the system is in one state, and specific conditions determine when it can move to another.

## Why Use State Machines

* Keeps logic organized
* Avoids large if/else chains
* Makes transitions explicit
* Makes behavior easier to debug
* Scales better as features grow

## Core Idea

A state machine has:

* States: modes of behavior
* Transitions: rules for switching between states
* State actions: behavior performed while in a state

Example logic:

```
state = "Idle"

loop:
    input = readInput()

    if state == "Idle":
        if input.move:
            state = "Walk"
        if input.jump:
            state = "Jump"

    if state == "Walk":
        if not input.move:
            state = "Idle"
        if input.jump:
            state = "Jump"
```

## Example

### Unity Example (C# Enum State Machine)

```csharp
public enum PlayerState { Idle, Walk, Jump }

public class PlayerController : MonoBehaviour
{
    public PlayerState state = PlayerState.Idle;

    void Update()
    {
        switch (state)
        {
            case PlayerState.Idle:
                HandleIdle();
                break;

            case PlayerState.Walk:
                HandleWalk();
                break;

            case PlayerState.Jump:
                HandleJump();
                break;
        }
    }

    void HandleIdle()
    {
        if (Input.GetKey(KeyCode.A) || Input.GetKey(KeyCode.D))
            state = PlayerState.Walk;

        if (Input.GetKeyDown(KeyCode.Space))
            state = PlayerState.Jump;
    }

    void HandleWalk()
    {
        if (!(Input.GetKey(KeyCode.A) || Input.GetKey(KeyCode.D)))
            state = PlayerState.Idle;

        if (Input.GetKeyDown(KeyCode.Space))
            state = PlayerState.Jump;
    }

    void HandleJump()
    {
        // Example condition: return to Idle when grounded
        // if (isGrounded) state = PlayerState.Idle;
    }
}
```

## Use Cases

* Character movement states
* Enemy AI behavior
* Game flow states (menu, pause, gameplay)
* Animation control
* UI interaction flows

## Common Mistakes

* Mixing too many responsibilities into one state
* Allowing unclear or conflicting transitions
* Forgetting to define what happens when entering or leaving a state
* Tightly coupling input, animation, and gameplay logic
* Letting the number of states grow without structure

## Related Topics

* Animation state machines
* Behavior trees
* Scene and game state management