🇬🇧 [English](README.md) | 🇫🇷 [Français](README.fr.md)

# 📋 Git Cheat Sheet

## 🌀 Git - Distributed Version Control System

## 🌐 GitHub - Git repository hosting service

## 🛠️ Basic Git Commands

```bash
git --version      # show Git version
git --help         # show help for Git commands
```

### ⚙️ Configure Git

```bash
git config --global user.name <name>     # set global username
git config --global user.email <email>   # set global email
git config --list                        # show Git configuration
```

Example:

```bash
git config --global user.name "Dmytro Palahin"
git config --global user.email "dmytro.palahin@gmail.com"
```

### 🏁 Initialize a Git repository

```bash
git init                                # initialize a Git repository in the project
git remote -v                           # show remote repositories
git remote add origin <repository-url>  # add a remote repository
git push -u origin master               # push changes to the remote repository
```

### 📊 Check repository status

```bash
git status                              # show staging area and changes to be committed
```

### 📜 View commit history

```bash
git log                                 # view history of commits
```

### ➕ Adding and Removing Files

```bash
git add .                               # add all files from working directory to the staging area
git add -f environment.yml              # add a specific file with force
git rm <file>                           # remove file from the staging area and working directory
```

### 💾 Commit Changes

```bash
git commit -m "<message>"               # commit changes in the staging area with a message
```

### 🌿 Check Out Branches and Commits

```bash
git checkout <commit hash>              # checkout a specific commit
git checkout <branch name>              # switch to an existing branch
git checkout -b <branch name>           # create a new branch and switch to it
git checkout main                       # switch back to the main branch
```

### 🌲 Branch Management

```bash
git branch <branch name>                # create a new branch
git branch                              # list all branches
git branch -a                           # list all branches, including remote ones
git branch -m <new name>                # rename the current branch
git branch -d <branch>                  # delete a branch (can't delete the current branch)
git branch -vv                          # list all branches with additional information
```

### 🔀 Merging Branches

```bash
git merge <feature branch>              # merge a feature branch into the current branch
git merge -m "<message>" <branch>       # merge with a custom message
```

### 🔍 Inspecting Commits

```bash
git cat-file -t <commit hash>           # show type of an object (commit, blob, etc.)
git cat-file -p <commit hash>           # show content of the object
```

### 🔄 Push and Pull Changes

```bash
git push                                # push changes from the local repository to the remote
git pull                                # apply changes from a remote repository into your current local branch
git clone <url>                         # clone a remote repository to the local machine
```

### 🌐 Remote Repository Management

```bash
git remote add origin <url>             # connect a remote repository
git remote                              # list remote repositories
git remote -v                           # show URLs for remote repositories
```

### 🚀 Push Changes to Remote

```bash
git push -u origin <branch>             # push changes to the remote repository and track the branch
git push -u origin main                 # push changes to the main branch
```

---

## 🔄 Typical Workflow

### 📊 Check the status of your working directory

```bash
git status
```

### ➕ Add or remove files

```bash
git add <file>              # add a specific file to the staging area
git rm <file>               # remove a specific file from the repository
git restore <file>          # undo changes in the working directory for a specific file
```

### 💾 Commit your changes

```bash
git commit -m "<message>"
```

### 🚀 Push changes to the remote

```bash
git push
git push --set-upstream origin <branch-name>
```

---

## 🌟 First-Time Setup for a New Remote Repository

### 🌐 Add the remote repository

```bash
git remote add origin <url>
```

### ✅ Verify the remote is set correctly

```bash
git remote -v
```

### 🌿 Rename the current branch to `main`

```bash
git branch -M main
```

### 🚀 Push changes to the remote repository

```bash
git push -u origin main
```

---

## 🏷️ Adding and Managing Tags

### 📜 List Tags

```bash
git tag   # list all tags
```

### 🏷️ Create a Tag

```bash
git tag <tagname>                       # create a lightweight tag
git tag -a <tagname> -m "<message>"     # create an annotated tag with a message
```

### 🔍 Show Tag Details

```bash
git show <tagname>                      # show details of a specific tag
```

### 🚀 Push Tags to Remote

```bash
git push origin <tagname>               # push a specific tag to the remote repository
git push origin --tags                  # push all tags to the remote repository
```

### 🗑️ Delete a Tag

```bash
git tag -d <tagname>                    # delete a specific tag
git push origin --delete <tagname>      # delete a tag from the remote repository
```

---

## 🔄 Rename a Branch Locally and Remotely

### 🌿 Rename the branch locally

```bash
git branch -m <old-branch-name> <new-branch-name>
```

### 🚀 Push the renamed branch to the remote

```bash
git push origin <new-branch-name>
```

### 🗑️ Delete the old branch from the remote

```bash
git push origin --delete <old-branch-name>
```

### 🌐 Reset the upstream branch for the new branch

```bash
git push --set-upstream origin <new-branch-name>
```

---

## 🏷️ Rename a Tag Locally and Remotely

### 🏷️ Rename the tag locally

```bash
git tag <new-tag-name> <old-tag-name>       # create a new tag with the old tag's commit
git tag -d <old-tag-name>                   # delete the old tag locally
```

### 🚀 Push the new tag to the remote

```bash
git push origin <new-tag-name>
```

### 🗑️ Delete the old tag from the remote

```bash
git push origin --delete <old-tag-name>
```

---
