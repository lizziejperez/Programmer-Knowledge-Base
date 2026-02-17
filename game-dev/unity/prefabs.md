# Prefabs (Unity)

## Definition
A prefab is a reusable GameObject template.

## Why Use Prefabs
- Reuse objects across scenes
- Maintain consistency (update prefab → updates instances)
- Faster iteration for gameplay objects (enemies, items, UI)

## Common Workflow
1. Create GameObject in scene
2. Drag into `Prefabs/` folder to create prefab
3. Edit prefab to update all instances

## Notes
- Prefab instance overrides are changes made per-instance.
- Too many overrides can get messy; prefer configuring via scripts/data.