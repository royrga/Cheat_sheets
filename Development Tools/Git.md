---
tags:
  - DevelopmentTools
---

# Git Cheat Sheet
## Table of Contents
- [Recommended workflow](#recommended%20workflow)
- [Getting Started](#getting%20started)
- [Basic Commands](#basic%20commands)
- [Branching](#branching)
- [Merging](#merging)
- [Remote Repositories](#remote%20repositories)
- [Stashing](#stashing) 
- [Undoing Changes](#undoing%20changes)

## Recommended Workflow

1. If you don't want to lose changes ensure that your [working directory](#^working-directory)  is clean before start this steps.


2. **Option 1** Run *fetch* command to get last changes from [remote](#^remote-repository) in your [local repository](#^local-repository). This command keep your changes on working directory:  
`git fetch`  
or **Option 2** Run *pull* command to get last changes from remote in your local repository and your working directory. Note that any change in working directory could be deleted.
	`git pull`

3. Create and checkout a new branch (do this before start working on code changes):  
` git checkout -b new_branch_name `

4. Once you have code changes that you want add to a commit:  
` git add .`  To stage all files with changes
` git add <file> `  To stage specific file

5. Commit your changes:  
`git commit -m "message"`

6. Push changes to remote(apply if you are working with a remote project):  
`git push origin <branch>`


## Getting Started
- `git init`: Initialize a new Git repository
- `git clone <repository>`: Clone an existing repository

## Basic Commands
- `git status`: Show the working directory status
- `git add <file>`: Add a file to the staging area
- `git commit -m "message"`: Commit changes with a message
- `git log`: Show commit logs
- `git diff`: Show changes between commits, commit and working tree, etc.

## Branching
- `git branch`: List branches
- `git branch <branch-name>`: Create a new branch
- `git checkout <branch-name>`: Switch to a branch
- `git checkout -b <branch-name>`: Create and switch to a new branch

## Merging
- `git merge <branch-name>`: Merge a branch into the current branch
  - **Description**: Combines the changes from one branch into another. It creates a new commit that represents the merge.
  - **When to Use**: 
    - When you want to preserve the complete history of changes, including the branch structure.
    - When working in a team and you want to maintain a clear record of how branches have diverged and merged.
    - When you want to avoid rewriting commit history.

- `git rebase <branch-name>`: Rebase the current branch onto another branch
  - **Description**: Moves or combines a sequence of commits to a new base commit. It rewrites the commit history.
  - **When to Use**:
    - When you want to maintain a linear project history without branches.
    - When you want to clean up a feature branch before merging it into the main branch.
    - When you want to incorporate changes from another branch without creating a merge commit.

## Remote Repositories
- `git remote -v`: List remote repositories
- `git remote add <name> <url>`: Add a new remote repository
- `git fetch <remote>`: Fetch changes from a remote repository
- `git pull <remote> <branch>`: Pull changes from a remote repository
- `git push <remote> <branch>`: Push changes to a remote repository

## Stashing
- `git stash`: Stash changes in a dirty working directory
- `git stash push -m "message"`: Allows you to add a descriptive message to your stash for easier identification later.
- `git stash list`: List stashed changes
-  `git stash apply [stash@{n}]`: Applies the changes from a specified stash to your current working directory, leaving the stash in the stash list. If no `stash@{n}` is provided, it applies the most recent stash (`stash@{0}`).
- `git stash pop [stash@{n}]`: Applies the changes from a specified stash to your current working directory and then removes that stash from the stash list. If no `stash@{n}` is provided, it applies and removes the most recent stash.
- `git stash drop [stash@{n}]`: Deletes a specific stash from the stash list.
- `git stash clear`: Removes all stashes from the stash list.

## Undoing Changes
- `git reset <file>`: Unstage a file
- `git checkout -- <file>`: Discard changes in a file
- `git revert <commit>`: Revert a commit by creating a new commit



## Glossary

>Working directory  
>Place where developer actively edits and updates files ^working-directory

>Local repository:
>Contain history of all commits across all branches ^local-repository

>Remote repository:
>The remote version of the local repostiory ^remote-repository


