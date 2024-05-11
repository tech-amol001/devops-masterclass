# Understanding GitHub

## What is GitHub?

- You can use GitHub and Git to collaborate on work.
- GitHub is a cloud-based vcs platform where you can store, share, and work together with others to write code.
- GitHub is built on top of git.
- It intelligently tracks changes in files present in git repo.
- Storing your code in a "repository" on GitHub allows you to:
  1. Showcase or share your work.
  2. Track and manage changes to your code over time.
  3. Let others review your code, and make suggestions to improve it.
  4. Collaborate on a shared project, without worrying that your changes will impact the work of your collaborators before you're ready to integrate them.

## Step-01: Create a GitHub Account

- Navigate to https://github.com/
- Click Sign up
- Follow the prompts to create your personal account
- During sign up, you'll be asked to verify your email address.
- _Note_: Without a verified email address, you won't be able to complete some basic GitHub tasks, such as creating a repository.

## Step-02: Create a GitHub Repository (remote)

- Sign-in to your [Github](https://github.com/) account.
- Navigate to **Repositories** tab >> Click on **New** button
- Repository Name: <repo_name>
- Description: <some_description_about_repo>
- Scope: Private
- Add a readme file: Unchecked
- Add .gitignore file: None
- Choose a License: None
- Click on **Create** button

## Step-03: Connect a local (git) and remote (Github) repository

### 3.1 In case you have not yet created any local git repository yet

```
# create a new repository on the command line
echo "# test-repos" >> README.md

# Initialize the directory
git init

# Add some contents to your git repo
git add README.md

# commit the changes
git commit -m "first commit"

# Rename a branch to main
git branch -M main

# Add info about the remote repos (here origin)
git remote add origin https://github.com/your_username/your_repos_name.git

# Push the commited changes to remote repos (here origin is Github repos)
git push -u origin main

```

### 3.2 Push an existing repository from the command line

```
# Add info about the remote repos (here origin)
git remote add origin https://github.com/your_username/your_repos_name.git

# Rename a branch to main
git branch -M main

# Push the new changes to origin on main branch
git push -u origin main

```

## Step-04: Commit the changes locally and check-in (push) the code to GitHub repo

## Step-05: Understanding the workflow between local and remote repositories

## Step-06: Understanding the git remote tracking branches

## Step-07: Cloning a remote repository on local system

## Step-08: Understanding the `git upstream`

## Step-09: Deleting the branches
