# 📋 Git Cheat Sheet

## 🌀 Git - Distributed Version Control System

## 🌐 GitHub - Git repository hosting service

## 🛠️ Basic Git Commands

```bash
git --version      # Show Git version
git --help         # Show help for Git commands
```

### ⚙️ Configure Git

```bash
git config --global user.name <name>     # Set global username
git config --global user.email <email>   # Set global email
git config --list                        # Show Git configuration
```

Example:

```bash
git config --global user.name "Dmytro Palahin"
git config --global user.email "dmytro.palahin@gmail.com"
```

### 🏁 Initialize a Git repository

```bash
git init                                # Initialize a Git repository in the project
git remote -v                           # Show remote repositories
git remote add origin <repository-url>  # Add a remote repository
git push -u origin master               # Push changes to the remote repository
```

### 📊 Check repository status

```bash
git status   # Show staging area and changes to be committed
```

### 📜 View commit history

```bash
git log    # View history of commits
```

### ➕ Adding and Removing Files

```bash
git add .       # Add all files from working directory to the staging area
git rm <file>   # Remove file from the staging area and working directory
```

### 💾 Commit Changes

```bash
git commit -m "<message>"  # Commit changes in the staging area with a message
```

### 🌿 Check Out Branches and Commits

```bash
git checkout <commit hash>       # Checkout a specific commit
git checkout <branch name>       # Switch to an existing branch
git checkout -b <branch name>    # Create a new branch and switch to it
git checkout main                # Switch back to the main branch
```

### 🌲 Branch Management

```bash
git branch <branch name>   # Create a new branch
git branch                 # List all branches
git branch -a              # List all branches, including remote ones
git branch -m <new name>   # Rename the current branch
git branch -d <branch>     # Delete a branch (can't delete the current branch)
git branch -vv             # List all branches with additional information
```

### 🔀 Merging Branches

```bash
git merge <feature branch>            # Merge a feature branch into the current branch
git merge -m "<message>" <branch>     # Merge with a custom message
```

### 🔍 Inspecting Commits

```bash
git cat-file -t <commit hash>    # Show type of an object (commit, blob, etc.)
git cat-file -p <commit hash>    # Show content of the object
```

### 🔄 Push and Pull Changes

```bash
git push                 # Push changes from the local repository to the remote
git pull                 # Apply changes from a remote repository into your current local branch
git clone <url>          # Clone a remote repository to the local machine
```

### 🌐 Remote Repository Management

```bash
git remote add origin <url>  # Connect a remote repository
git remote                   # List remote repositories
git remote -v                # Show URLs for remote repositories
```

### 🚀 Push Changes to Remote

```bash
git push -u origin <branch>   # Push changes to the remote repository and track the branch
git push -u origin main       # Push changes to the main branch
```

---

## 🔄 Typical Workflow

### 📊 Check the status of your working directory

```bash
git status
```

### ➕ Add or remove files

```bash
git add <file>      # Add a specific file to the staging area
git rm <file>       # Remove a specific file from the repository
git restore <file>  # Undo changes in the working directory for a specific file
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
git tag   # List all tags
```

### 🏷️ Create a Tag

```bash
git tag <tagname>                     # Create a lightweight tag
git tag -a <tagname> -m "<message>"   # Create an annotated tag with a message
```

### 🔍 Show Tag Details

```bash
git show <tagname>   # Show details of a specific tag
```

### 🚀 Push Tags to Remote

```bash
git push origin <tagname>   # Push a specific tag to the remote repository
git push origin --tags      # Push all tags to the remote repository
```

### 🗑️ Delete a Tag

```bash
git tag -d <tagname>                 # Delete a specific tag
git push origin --delete <tagname>   # Delete a tag from the remote repository
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
git tag <new-tag-name> <old-tag-name>   # Create a new tag with the old tag's commit
git tag -d <old-tag-name>               # Delete the old tag locally
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
