# Git Cheat Sheet
[Back](README.md) to README file
## Table of Contents
- [Getting Started](#getting-started)
- [Basic Commands](#basic-commands)
- [Branching](#branching)
- [Merging](#merging)
- [Remote Repositories](#remote-repositories)
- [Stashing](#stashing)
- [Undoing Changes](#undoing-changes)
-

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
- `git rebase <branch-name>`: Rebase the current branch onto another branch

## Remote Repositories
- `git remote -v`: List remote repositories
- `git remote add <name> <url>`: Add a new remote repository
- `git fetch <remote>`: Fetch changes from a remote repository
- `git pull <remote> <branch>`: Pull changes from a remote repository
- `git push <remote> <branch>`: Push changes to a remote repository

## Stashing
- `git stash`: Stash changes in a dirty working directory
- `git stash list`: List stashed changes
- `git stash apply`: Apply stashed changes

## Undoing Changes
- `git reset <file>`: Unstage a file
- `git checkout -- <file>`: Discard changes in a file
- `git revert <commit>`: Revert a commit by creating a new commit

## Recommended Workflow

1. Ensure your [working directory](#working-directory) is clean before start this steps.

2. **[Option 1]** Run *fetch* command to get last changes from remote in your [local repository](#local-repository). This command keep your changes on working directory:  
`git fetch`  

    **[Option 2]** Run *pull* command to get last changes from remote in your local repository and your working directory. Note that any change in working directory could be deleted.
    `git pull`

3.

1. Create and checkout a new branch (do this before start working on code changes):  
` git checkout -b new_branch_name `

2. Once you have code changes that you want add to a commit:  
` git add .`  To stage all files with changes
` git add <file> `  To stage specific file

3. Commit your changes:  
`git commit -m "message"`

4. Push changes to remote(apply if you are working with a remote project):  
`git push origin <branch>`

## Glossary

>#### Working directory: 
>Place where developer actively edits and updates files

>#### Local repository:
>Contain history of all commits across all branches

>#### Remote repository:
>The remote version of our local repostiory