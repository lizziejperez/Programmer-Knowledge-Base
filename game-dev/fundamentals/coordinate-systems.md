# Coordinate Systems

A **coordinate system** defines how positions in space are represented using numeric values.

In game development, coordinate systems are used to determine:

- object positions
- movement
- collisions
- camera placement
- physics calculations

Most games represent positions using **vectors of coordinates**.

# 2D Coordinate System

In 2D games, positions are usually represented using **two coordinates**:

```
(x,y)
```

This means:

- `x` → horizontal position
- `y` → vertical position

### Typical Layout

```
y ↑
|
|
|
+------------→ x
```

# Screen Coordinate System

Game engines often use a **screen coordinate system** where the origin is at the **top-left corner**.

```
(0,0) ----------------→ x
|
|
|
↓
y
```

Key characteristics:

- `x` increases to the **right**
- `y` increases **downward**

This is common in:

- Unity UI
- HTML Canvas
- many 2D frameworks

#  World Coordinate System

Games also use a **world coordinate system**.

This represents positions in the **game world**, not the screen.

Example:

```
Player position: (10, 4)
Enemy position: (15, 4)
```

World coordinates are used for:

- physics
- object movement
- collision detection

The camera then determines **what portion of the world is visible**.

# 3D Coordinate System

3D games use **three coordinates**:

```
(x, y, z)
```

Axes represent:

| Axis | Meaning |
|-----|------|
| x | horizontal (left / right) |
| y | vertical (up / down) |
| z | depth (forward / backward) |

## Right-Handed vs Left-Handed Systems

3D engines use different coordinate conventions.

### Right-Handed System

Common in:

- OpenGL
- Blender

```
x → right
y → up
z → toward viewer
```

### Left-Handed System

Used by:

- Unity
- DirectX

```
x → right
y → up
z → forward
```

# Local vs World Coordinates

Objects often have two coordinate systems.

## World Coordinates

Position relative to the **entire game world**.

Example:

```
Player position = (10, 3, 5)
```

## Local Coordinates

Position relative to the **object’s parent**.

Example:

```
Sword attached to player
local position = (0.5, 0, 0)
```

If the player moves, the sword moves with it.

# Coordinate Transformations

Game engines constantly convert between coordinate systems:

Examples:

- world → screen
- local → world
- camera space → world space

These transformations are performed using:

- matrices
- vector math

# Common Game Dev Uses

Coordinate systems are used for:

- player movement
- camera positioning
- physics simulation
- rendering objects
- collision detection
- animation