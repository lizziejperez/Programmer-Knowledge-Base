# Delta Time

**Delta time** (`dt`) is the time elapsed between frames.

## Why Use It
Without `dt`, movement depends on FPS.

## Example
```
If speed = 5 units/second:
    position += speed * dt
```

## Unity
- `Time.deltaTime` (time since last frame)
- `Time.fixedDeltaTime` (fixed update step)

## Common Mistakes
- Forgetting dt (movement faster on high FPS)
- Using `deltaTime` in `FixedUpdate` (usually use `fixedDeltaTime`)