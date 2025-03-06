# Git Cheat Sheet
[Back](README.md) to README file
## Table of Contents
1. [Getting Started](#getting-started)
2. [Basic Commands](#basic-commands)
3. [Branching](#branching)
4. [Merging](#merging)
5. [Remote Repositories](#remote-repositories)
6. [Stashing](#stashing)
7. [Undoing Changes](#undoing-changes)

## Getting Started
- `git init`: Initialize a new Git repository
- `git clone <repository>`: Clone an existing repository

## Basic Commands
- `git status`: Show the working directory status
- `git add <file>`: Add a file to the staging area
- `git commit -m "message"`: Commit changes with a message
- `git log`: Show commit logs

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
