# Git & GitHub Complete Guide

---

# What is Git

Git is a distributed version control system that tracks changes in files over time.

It allows developers to:

- Save project history
- Work in branches
- Collaborate safely
- Recover previous versions

---

# What is GitHub

GitHub is a cloud platform that hosts Git repositories.

It allows you to:

- Store your project online
- Share your code with others
- Collaborate with a team
- Manage pull requests and reviews
- Automate workflows using GitHub Actions

Key difference:

- Git works locally.
- GitHub works online.

---

# Basic Commands

## Initialize Project

```bash
git init
```

## Check Status

```bash
git status
```

## Add Files

```bash
git add .
```

## Commit Changes

```bash
git commit -m "message"
```

## View History

```bash
git log
```

---

# Branching

## Create New Branch

```bash
git checkout -b feature-name
```

## Merge Branch

```bash
git checkout main
git merge feature-name
```

---

# Merge vs Rebase

- Merge keeps the original history structure.
- Rebase rewrites history to make it linear.

Rebase example:

```bash
git checkout feature
git rebase main
```

---

# Handling Conflicts

When a conflict appears:

1. Edit the file manually.
2. Remove conflict markers.
3. Run:

```bash
git add .
git commit
```

If rebasing:

```bash
git rebase --continue
```

---

# Advanced Commands

---

## Rebase Overview

Rebase moves the current branch to start from another branch.

Example structure:

main:

A — B — C  

feature:

A — B — D — E  

After rebase:

A — B — C — D — E  

Command:

```bash
git checkout feature
git rebase main
```

---

## Interactive Rebase

Used to manually edit previous commits.

Command:

```bash
git rebase -i HEAD~3
```

---

## Continue Rebase

Used after fixing a conflict.

```bash
git rebase --continue
```

Rebase resumes and applies remaining commits.

---

## Skip Current Commit

Used when the current commit is not needed.

```bash
git rebase --skip
```

Result:  
The commit is ignored and not included after rebase.

---

## Abort Rebase

Used to cancel the entire rebase process.

```bash
git rebase --abort
```

Result:  
The branch returns to its original state before rebase started.

---

## Cherry-pick

Copies a specific commit from one branch to another.

```bash
git cherry-pick 6ffcb95
```

---

## Squash

Combines multiple commits into one.

Example:

- Fix typo
- Fix spacing
- Fix variable
- Final fix

Instead of four commits, combine them into one clean commit.

Command:

```bash
git rebase -i HEAD~4
```

Then mark commits as `squash`.

---

## Git Hooks

Hooks are scripts that run automatically at certain Git events.

Examples:

- pre-commit
- pre-push
- post-merge

Location:

```
.git/hooks
```

Example use:  
Prevent commit if tests fail.

---

## Tags

Tags mark specific commits as versions.

```bash
git tag v1.0
git push origin v1.0
```

---

## Stash

Used to save changes temporarily without committing.

Useful when switching branches quickly.

```bash
git stash
git stash pop
```

---

## Reset

Dangerous command used to modify commit history.

### Soft

Removes commit but keeps changes staged.

```bash
git reset --soft HEAD~1
```

### Mixed (default)

Removes commit but keeps changes unstaged.

```bash
git reset HEAD~1
```

### Hard

Removes commit and deletes changes permanently.

```bash
git reset --hard HEAD~1
```

---

## Submodules

Allows you to include another Git repository inside your repository.

Example:

```bash
git submodule add https://repo.git
```

---

## Reflog

Shows all actions in the repository, including deleted commits.

```bash
git reflog
```

---

## Fork

Fork means copying someone else's repository into your account.

Used when you do not have write access.  
After forking, you can create a Pull Request.

---

## Git Flow

Git Flow is a branching strategy.

Main branches:

- main (production)
- develop

Support branches:

- feature/*
- release/*
- hotfix/*

Used in professional team environments.

---

## CI/CD

CI = Continuous Integration  
CD = Continuous Deployment  

When you push code:

- Tests run automatically
- Build runs
- Deployment runs

Common tools:

- GitHub Actions
- GitLab CI
- Jenkins

---

# Professional Workflow

Feature Branch Strategy:

- Create a branch per feature
- Push branch to remote
- Open Pull Request
- Review changes
- Merge into main

---

# Conclusion

Git is not just a collection of commands.

It is a complete system for managing project history safely and professionally.
