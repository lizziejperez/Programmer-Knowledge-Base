# Collision Basics

A collision occurs when two objects overlap in space based on their colliders.

Colliders define the collision shape (box, sphere, capsule, mesh).

## Table of Contents

* [Key Concepts](#key-concepts)
* [Why Collisions Matter](#why-collisions-matter)
* [Collider vs Trigger](#collider-vs-trigger)
* [Example](#example)
* [Unity Events](#unity-events)
* [Detection Concepts](#detection-concepts)
* [Use Cases](#use-cases)
* [Common Mistakes](#common-mistakes)
* [Notes](#notes)

## Key Concepts

Collisions are used to detect interactions between objects in a game world.

Each object uses a collider to define its physical shape.

## Why Collisions Matter

Used for:

* Player movement (ground detection)
* Damage and hit detection
* Physics interactions (bouncing, pushing)
* Triggers (entering zones, pickups)

## Collider vs Trigger

Collider (solid):
Objects collide physically and may block movement.

Trigger:
Detects overlap but does not physically block movement.

Unity setting:
Is Trigger

## Example

### JavaScript Example (Simple Collision Detection)

This example checks if two rectangles overlap.

```javascript
function isColliding(a, b) {
    return (
        a.x < b.x + b.width &&
        a.x + a.width > b.x &&
        a.y < b.y + b.height &&
        a.y + a.height > b.y
    );
}

// Example objects
const player = { x: 10, y: 10, width: 50, height: 50 };
const enemy = { x: 40, y: 30, width: 50, height: 50 };

if (isColliding(player, enemy)) {
    console.log("Collision detected!");
}
```

## Unity Events

### 3D

```csharp
void OnCollisionEnter(Collision collision) { }
void OnCollisionStay(Collision collision) { }
void OnCollisionExit(Collision collision) { }

void OnTriggerEnter(Collider other) { }
void OnTriggerStay(Collider other) { }
void OnTriggerExit(Collider other) { }
```

### 2D

```csharp
void OnCollisionEnter2D(Collision2D collision) { }
void OnTriggerEnter2D(Collider2D other) { }
```

### Example: Pickup Trigger

```csharp
void OnTriggerEnter(Collider other)
{
    if (other.CompareTag("Player"))
    {
        // give item to player
        Destroy(gameObject);
    }
}
```

## Detection Concepts

Discrete:
Checks collisions each frame. Fast but may miss fast-moving objects.

Continuous:
More accurate for fast objects. Helps prevent tunneling.

## Use Cases

* Ground detection for characters
* Hitboxes and damage systems
* Collectibles and pickups
* Zone triggers (enter/exit areas)

## Common Mistakes

* Forgetting a Rigidbody (required for many collision events)
* Using the wrong event type (2D vs 3D)
* Using triggers when solid collisions are needed (or vice versa)
* Tunneling: fast objects passing through thin colliders
* Not using tags or layers, leading to messy logic

## Notes

* Physics runs in FixedUpdate(), not Update()
* Apply forces in FixedUpdate() for stable behavior
* Use layers to control what objects can collide