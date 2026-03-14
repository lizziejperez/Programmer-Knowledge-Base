# Git Commands

Git is a distributed version control system used to track changes in code and collaborate with others.

## 1. Typical Workflow

Most development follows this pattern:

```bash
git pull
git add .
git commit -m "message"
git push
```

Steps involved:

1. Modify files
2. Stage changes
3. Commit a snapshot
4. Push changes to the remote repository

## 2. Repository Setup

### Initialize a Repository

```bash
git init
```

Creates a new Git repository in the current directory.

### Clone an Existing Repository

```bash
git clone <repository-url>
```

Downloads the repository and its history.

## 3. Basic Workflow

### Check Repository Status

```bash
git status
```

Shows:

- modified files
- staged files
- untracked files
- current branch

### Stage Files

Stage a specific file:

```bash
git add file.txt
```

Stage all changes:

```bash
git add .
```

### Commit Changes

```bash
git commit -m "message describing changes"
```

A commit represents a snapshot of the staged files.

### View Commit History

```bash
git log
```

Common variations:

```bash
git log --oneline
git log --graph
git log --stat
```

## 4. Inspecting Changes
```bash
git status
git diff
git log
```
## 5. Working with Remotes

### Add a Remote Repository

```bash
git remote add origin <repository-url>
```

### View Remotes

```bash
git remote -v
```

### Push Changes

```bash
git push origin branch-name
```

Example:

```bash
git push origin main
```

### Pull Latest Changes

```bash
git pull
```

Equivalent to:

```bash
git fetch
git merge
```

## 6. Branching

Branches allow parallel development.

| Command | Purpose |
|------|------|
| `git branch` | List branches |
| `git branch feature-name` | Create a branch |
| `git checkout branch-name` | Switch branches |
| `git switch branch-name` | Modern branch switching |
| `git checkout -b feature-name` | Create and switch branch |
| `git switch -c feature-name` | Modern create + switch |

## 7. Merging

Merge another branch into the current branch.

```bash
git merge branch-name
```

## 8. Undoing Changes

| Command | Purpose |
|------|------|
| `git restore --staged file.txt` | Unstage a file |
| `git restore file.txt` | Discard local changes |
| `git reset --soft HEAD~1` | Undo last commit but keep changes |
| `git reset --hard HEAD~1` | Undo last commit and discard changes |

⚠️ **Caution**: `--hard` deletes changes permanently.

## 9. Helpful Commands

| Command | Purpose |
|------|------|
| `git branch --show-current` | Show current branch |
| `git fetch` | Download remote updates |
| `git blame file.txt` | Show who last modified each line |

## 10.  Best Practices

- Write clear commit messages
- Commit small logical changes
- Use branches for features
- Pull before pushing
- Never commit secrets (e.g., `.env`, API keys)