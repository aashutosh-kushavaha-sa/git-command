# Git Commands Cheat Sheet

## Table of Contents
- [Repository Management](#repository-management)
- [Basic Workflow](#basic-workflow)
- [Branching & Merging](#branching--merging)
- [Undoing Changes](#undoing-changes)
- [Remote Repositories](#remote-repositories)
- [Advanced Commands](#advanced-commands)

## Repository Management

### Initialize a New Repository
```bash
git init
```
Creates a new Git repository in the current directory.

### Clone a Repository
```bash
git clone <repository-url>
```
Creates a local copy of a remote repository.
- `git clone https://github.com/user/repo.git` - Clone via HTTPS
- `git clone git@github.com:user/repo.git` - Clone via SSH

---

## Basic Workflow

### Check Status
```bash
git status
```
Shows the working tree status, including modified files and staged changes.

### Stage Changes
```bash
git add <file>    # Stage specific file
git add .         # Stage all changes
git add -A        # Stage all changes including deletions
```

### Commit Changes
```bash
git commit -m "Descriptive commit message"
```
- `git commit -am "Message"` - Stage and commit all tracked files

### View Commit History
```bash
git log
```
- `git log --oneline` - Compact view
- `git log --graph` - Show branch graph
- `git log -p` - Show changes in each commit

---

## Branching & Merging

### Create and Switch to New Branch
```bash
git switch -c <branch-name>
```

### Switch Branches
```bash
git switch <branch-name>
```

### List Branches
```bash
git branch          # Local branches
git branch -a       # All branches (including remote)
```

### Merge Branches
```bash
git merge <branch-name>
```
Merges the specified branch into the current branch.

### Rebase
```bash
git rebase <base-branch>
```
Reapplies commits on top of another base tip.

---

## Undoing Changes

### Discard Changes in Working Directory
```bash
git restore <file>     # For Git 2.23+
git checkout -- <file> # Older Git versions
```

### Unstage Changes
```bash
git restore --staged <file>  # Git 2.23+
git reset HEAD <file>        # Older versions
```

### Reset to Previous Commit
```bash
git reset --hard HEAD^      # Undo last commit and discard changes
git reset --soft HEAD^      # Undo commit but keep changes staged
git reset --hard <commit>   # Reset to specific commit
```

### Revert a Commit
```bash
git revert <commit-hash>
```
Creates a new commit that undoes the changes from a previous commit.

---

## Remote Repositories

### Add Remote
```bash
git remote add origin <url>
```

### Push to Remote
```bash
git push -u origin <branch>  # First push
git push                    # Subsequent pushes
```

### Pull Latest Changes
```bash
git pull origin <branch>
```

### Fetch Changes
```bash
git fetch
```
Downloads objects and refs from another repository.

---

## Advanced Commands

### Stash Changes
```bash
git stash                 # Stash changes
git stash pop             # Apply and remove last stash
git stash list            # List stashed changes
git stash apply stash@{n} # Apply specific stash
```

### Cherry-pick
```bash
git cherry-pick <commit-hash>
```
Applies the changes from an existing commit to the current branch.

### View File History
```bash
git log --follow <file>
```

### Show Changes
```bash
git diff                  # Unstaged changes
git diff --staged         # Staged changes
git diff <branch1> <branch2>  # Between branches
```

### Tagging
```bash
git tag -a v1.0.0 -m "Version 1.0.0"  # Create annotated tag
git push origin --tags                 # Push tags to remote
```

### Clean Untracked Files
```bash
git clean -n  # Dry run
git clean -f  # Remove untracked files
```

---

## Best Practices
1. Write clear, descriptive commit messages
2. Make frequent, small commits
3. Create feature branches for new features
4. Test before pushing to main branch
5. Pull before pushing to avoid conflicts
6. Use `.gitignore` to exclude unnecessary files

## Common Issues
- **Merge conflicts**: Use `git status` to see conflicts, resolve them, then `git add` and `git commit`
- **Detached HEAD**: Use `git switch -` to return to previous branch
- **Accidental commits**: Use `git reset` or `git revert` to undo

---

*Remember to replace `<placeholders>` with actual values when using these commands.*
