# Working with `Git Branches`

## What are git branches?

- Git branches are basically a pointer to a snapshot of your changes.
- When you want to add a new feature or fix a bug, no matter how big or how small—you spawn a new branch to encapsulate your changes.

## How it works?

- A branch represents an independent line of development.
- Branches serve as an abstraction for the edit/stage/commit process.
- You can think of them as a way to request a brand new working directory, staging area, and project history.
- New commits are recorded in the history for the current branch, which results in a fork in the history of the project.

- The `git branch` command lets you create, list, rename, and delete branches.

## Git Branch Commands

```
# List all of the branches in your repository
git branch --list
OR
git branch

# Create a new branch called ＜newbranch＞. This does not check out the new branch
git branch <new_branch_name>

# Rename an existing branch
git branch -m <branch_name>

# List all remote branches
git branch -a

# Switch from one branch to another one
git checkout <branch_name>
OR
git checkout ＜remote_branch_name＞

# Deletes a branch | Git prevents you from deleting the branch if it has unmerged changes
git branch -d <branch_name>

# Force delete the specified branch, even if it has unmerged changes
git branch -D <branch_name>

# Checkout a new local branch and reset it to the remote branches last commit
git checkout -b ＜branch_name＞
git reset --hard origin/＜branch_name＞

```

## Hands-on Labs

### Step-01: Create a new Branch

### Step-02: Checkout to a Branch

### Step-03: Committing the changes to a particular branch

### Step-04: Deleting a branch

### Step-07: Merge a git branch into another branch

## `Merging` the git branches

- The git merge command lets you take the independent lines of development created by git branch and integrate them into a single branch.
- Note that all of the commands presented below merge into the current branch.
- The current branch will be updated to reflect the merge, but the target branch will be completely unaffected.

```
# Start a new feature
git checkout -b new-feature main

# Edit some files
git add <file>
git commit -m "Start a feature"

# Edit some files
git add <file>
git commit -m "Finish a feature"

# Merge in the new-feature branch
git checkout main
git merge new-feature
git branch -d new-feature

```

### Fast forward merge

### Three-way merge

### Resolving Conflict
