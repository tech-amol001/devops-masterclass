# Git ignore

## Overview

- Git sees every file in your working copy as one of three things:

  1. **tracked** - a file which has been previously staged or committed.
  2. **untracked** - a file which has not been staged or committed.
  3. **ignored** - a file which Git has been explicitly told to ignore.

- Ignored files are tracked in a special file named .gitignore that is checked in at the root of your repository.
- There is no explicit git ignore command: instead the .gitignore file must be edited and committed by hand when you have new files that you wish to ignore.
- **.gitignore** files contain patterns that are matched against file names in your repository to determine whether or not they should be ignored.

## Examples:

- Some common examples are:
  - dependency caches, such as the contents of /node_modules or /packages
  - compiled code, such as .o, .pyc, and .class files
  - build output directories, such as /bin, /out, or /target
  - files generated at runtime, such as .log, .lock, or .tmp
  - hidden system files, such as .DS_Store or Thumbs.db
  - personal IDE config files, such as .idea/workspace.xml

## Hands-on Labs

### 01-Ignoring a file while commiting the changes
