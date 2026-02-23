## What is Git
    It  is a version control system and tracks changes in files over time.
    It allows developers to:
      - Save project history
      - Work in branches
      - Collaborate safely
      - Recover previous versions


## What is GitHub?
    it is a cloud platform that hosts Git repositories.
    it allows you to:
    - Store your project online
    - Share your code with others
    - Collaborate with a team
    - Manage pull requests and reviews
    - Automate workflows using GitHub Actions.

    
    - Git works locally.
    - GitHub works online.

# Basic Commands
## Initialize project:
     git init
    
## Check status
     git status
    
## Add files
     git add .
    
## Commit changes
     git commit -m "message"
    
## View history
     git log

# Branching
## Create new branch
    git checkout -b feature-name

## Merge branch
    git checkout main
    git merge feature-name

---

# Merge vs Rebase
    Merge keeps history structure.
    Rebase rewrites history to make it linear.

    Rebase example:
    
    git checkout feature
    git rebase main


## Handling Conflicts
    When conflict appears:
      1. Edit the file manually
      2. Remove conflict markers
      3. Run:
    
    git add .
    git commit
    
    If rebasing:
    
    git rebase --continue
    


# Advanced Commands
##   Rebase Overview
  Rebase moves the current branch to start from another branch.
  main:
  A — B — C
  
  feature:
  A — B — D — E
  Result:
  A — B — C — D — E
    
    Command:
          git checkout feature  
          git rebase main  
    
  
## Interactive Rebase
  Manually edit the last 3 commits.

    Command:
    git rebase -i HEAD~3

## Continue Rebase
  Used after fixing conflict.
  Rebase resumes and applies remaining commits.

    commands:
    git rebase --continue

## Skip Current Commit
  Used when:
  The current commit is not needed.

  Result:
  Commit is ignored and not included after rebase.

    commands:
    git rebase --skip
    
## Abort Rebase
  Used when:
  You want to cancel the entire rebase process.
  
  Result:
  Branch returns to original state before rebase started.

    commands:
    git rebase --abort

## CHERRY-PICK
  Cherry-pick copies a specific commit from one branch to another.

    commands:
    git cherry-pick 6ffcb95


## SQUASH
  Squash combines multiple commits into one.
  You made:
      Fix typo
      Fix spacing
      Fix variable
      Final fix
  Instead of 4 commits,
  you combine into one clean commit.

    commands:
    git rebase -i HEAD~4

    Then mark commits as squash.

## GIT HOOKS
  Hooks are scripts that run automatically at certain Git events.
  Examples:
  
        pre-commit
        pre-push
        post-merge
        .git/hooks

        Example use:
      Prevent commit if tests fail.
      
## TAGS
  Tags mark specific commits as versions.
  
    commands:
    git tag v1.0
    git push origin v1.0

## STASH
  it is used to save changes without committing
  Useful when switching branches quickly.
  
    commands:
    git stash    
    git stash pop



## RESET
  Dangerous command.

### Soft
  Removes commit, keeps changes staged.

    commands:
    git reset --soft HEAD~1
    
### Mixed (default)
  Removes commit, keeps changes unstaged.

     commands:
      git reset HEAD~1
      
### Hard
  Removes commit, changes permanently.

     commands:
      git reset --hard HEAD~1


## SUBMODULES
  Submodule allows you to include another Git repository inside your repository.
  You have shared library project.
  
    commands:
    git submodule add https://repo.git


## REFLOG
Reflog shows ALL actions in repository. Even deleted commits.

Commands:
        git reflog



## FORK
Fork = Copy someone else's repository into your account.
    You don’t have write access. So you fork. Then create a Pull Request.

## GIT FLOW
Git Flow is a branching strategy.

    Main branches:
        main (production)
        develop
        Support branches:

        feature/*
        release/*
        hotfix/*

        Professional team structure.


## 9. Professional Workflow

Feature Branch Strategy:

- Create branch per feature
- Push branch
- Open Pull Request
- Review
- Merge to main

---

## 10. Conclusion

Git is not just commands.
It is a system to manage project history safely and professionally.
