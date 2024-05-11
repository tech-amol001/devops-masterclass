# Git 101

## What is `Git`?

- Git is most widely used version control system in the world.
- Git is a mature, actively maintained open source project originally developed in 2005 by Linus Torvalds.
- Having a distributed architecture, Git is an example of a DVCS (Distributed Version Control System).
- Rather than have only one single place for the full version history of the software as is common in once-popular version control systems like CVS or Subversion (also known as SVN), in Git, every developer's working copy of the code is also a repository that can contain the full history of all changes.

## What can you do with the `Git`?

Developers can review project history to find out:

- Which changes were made?
- Who made the changes?
- When were the changes made?
- Why were changes needed?

## Why `Git` for Version control?

- Git has the functionality, performance, security and flexibility that most teams and individual developers need.
- Significant numbers of developers already have Git experience.
- Git is a quality open source project.

## How `git` works?

## Hands-on Labs

### Step-01: Download and Install Git

- Download the git from here: https://git-scm.com/downloads
- Select the operating system of your choice (in this lab select _Windows_)
- Under **Standalone Installer** section, select **64-bit Git for Windows Setup**
- Once download, install the git
- Open command prompt/git bash and run below command to confirm the git installation:

```
git --version
```

### Step-02: Configure git

- Open command prompt/git bash and run below command to update the name and email parameters

```
git config --global user.name "KBindesh“
git config --global user.email "test@email.com"
```

- In order to see the git config parameter values, run:

```
git config -l
```

### Step-03: Setting up a git repository

- Create a new folder/directory on your local machine
- Open command prompt/shell >> change the directory to newly created directory
- Run below command to initialize the directory as git dir:

```
# Initializing a new Git repo
git init

```

### Steps-04: Working with other git commands

```
# Cloning an existing Git repo
git clone <remote_git_repo_url>

# Moving the changes to the staging area
git add

# Committing the changes
git commit -m "commit_msg"

# Configuring a Git repo for remote collaboration

```

```

```
