# Game Loop

## Idea
A game repeatedly:
1. Reads input
2. Updates game state
3. Renders output

This repeats many times per second (frames).

## Typical Loop (Concept)
```
while (gameIsRunning) {
    input();
    update();
    render();
}
```

## Why It Matters
- Enables real-time interaction
- Determines timing and consistency
- Separates logic from drawing

## Common Variations
- Fixed timestep update (stable physics)
- Variable timestep update (simpler, can be unstable)

## Common Bugs
- Frame-rate dependent movement (fix with delta time)