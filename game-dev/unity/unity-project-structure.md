# Unity Project Structure

## Creating a New Unity Project

1. Open Unity Hub
2. Click New Project
3. Select a template:
    - 2D (URP or Built-in) → for 2D games
    - 3D (URP or Built-in) → for 3D games
    - HDRP → high-end visuals (PC/console)
4. Name your project
5. Choose a location
6. Click Create

### Choosing 2D vs 3D

| 2D                   | 3D                         |
| -------------------- | -------------------------- |
| Sprites              | Meshes                     |
| Orthographic camera  | Perspective camera         |
| Simpler lighting     | Advanced lighting          |
| Good for platformers | Good for FPS / open worlds |

Note: You can technically mix 2D and 3D, but choose based on your main gameplay style.

## Default Unity Project Structure

When created, Unity generates:

- `Assets/` → Your game content
- `Packages/` → Package dependencies
- `ProjectSettings/` → Engine settings

Most of your work happens inside `Assets/`.

## Recommended Folder Organization

Inside `Assets`, create these folders:

| Folder | Purpose |
| --- | --- |
| `Scenes/` | Game scenes|
| `Scripts/` | C# scripts |
| `Prefabs/` | Reusable objects |
| `Materials/` | Materials/Shaders |
| `Textures/` | Textures |
| `Audio/` | Sound/Music |
| `Animations/` | Animation clips/controllers |
| `UI/` | UI prefabs/assets |

## Scene Management

- Always save your first scene as `SampleScene`
- Add scenes to Build Settings

## Script Naming Conventions

- File name must match class name
- Use PascalCase
- One class per file

Example:
```csharp
public class PlayerController : MonoBehaviour
{
}
```

## General Tips
- Name scenes clearly (e.g., `MainMenu`, `Level01`)
- Keep prefabs reusable (avoid scene-specific hard references)
- Use consistent naming (PascalCase for scripts/classes)
- Separate art from logic
- Use version control (Git + .gitignore for Unity)