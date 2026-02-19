# `.gitignore` Guide

A **`.gitignore`** file tells Git which files and folders to **exclude from version control**.

This prevents committing:
- build outputs
- dependency folders
- secrets
- OS/editor clutter
- large generated files

---

## Where `.gitignore` Lives

Place `.gitignore` in the **root** of your repository:

```
my-project/
├── .gitignore
├── README.md
└── src/
```

You can also have additional `.gitignore` files in subfolders, but most projects use a single root file.

## Basic Syntax Rules

### Comments

Lines starting with `#` are comments:

```gitignore
# Ignore Python cache files
__pycache__/
```

### Ignore a File
```gitignore
.env
notes.txt
```
### Ignore a Folder
```gitignore
node_modules/
dist/
```

Trailing slash means “directory”.

### Wildcards (`*`)
```gitignore
*.log
*.tmp
```

- `*` matches any characters
- `*.log` ignores all `.log` files

### Match in Any Folder (`**`)
```gitignore
**/node_modules/
**/*.log
```

Useful when you might have nested folders.

### Ignore Specific Path
```gitignore
build/output.txt
```

## Negation (!) — “Unignore” Something

Use `!` to re-include a file that was ignored:

```gitignore
*.log
!important.log
```

Note: If the parent folder is ignored, you may need to unignore the folder too.

Example:
```gitignore
logs/
!logs/important.log
```

This works only if Git can “see” the file path.

## Common .gitignore Patterns
### Secrets
```gitignore
.env
.env.*
*.key
*.pem
```

### OS / System Files
```gitignore
.DS_Store
Thumbs.db
```

### Editor / IDE
```gitignore
.vscode/
.idea/
*.swp
```

## Language / Framework Examples
### Node / JavaScript
```gitignore
node_modules/
dist/
build/
*.log
.env
```

### Python
```gitignore
__pycache__/
*.py[cod]
.venv/
venv/
.env
.pytest_cache/
```

### C# / Visual Studio
```gitignore
bin/
obj/
.vs/
*.user
*.suo
```

### Unity
```gitignore
Library/
Temp/
Obj/
Build/
Builds/
Logs/
UserSettings/
```

## Important Behavior: `.gitignore` Does NOT Remove Tracked Files

If you already committed a file, adding it to `.gitignore` will not automatically remove it from Git.

To stop tracking a file (but keep it locally):
```bash
git rm --cached path/to/file
```

Then commit the change.

## How to Check What’s Being Ignored

### See ignored files:
```bash
git status --ignored
```

### Explain why a file is ignored:
```bash
git check-ignore -v path/to/file
```

#### Example

Suppose the .gitignore contains: `*.log` and you need the explination for why the file `error.log` is being ignored.

If you run:
```bash
git check-ignore -v error.log
```

You might see:
```
.gitignore:3:*.log    error.log
```

This means:

- Line 3 of `.gitignore`
- Rule `*.log`
- Is the reason `error.log` is ignored

## Best Practices

- Ignore secrets (`.env`, API keys) always
- Ignore build/dependency folders (`dist/`, `node_modules/`)
- Keep `.gitignore` short and readable
- Use language/framework templates when starting a new repo
- Prefer ignoring generated files over manually deleting them

## Quick .gitignore Starter Template
```gitignore
# OS
.DS_Store
Thumbs.db

# Editor
.vscode/
.idea/

# Logs
*.log

# Secrets
.env
.env.*

# Build output
dist/
build/
```