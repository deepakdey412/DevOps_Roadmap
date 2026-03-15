# Day 02 – Git Basics, Branching & Collaboration 🌿

## 📌 Objective

Understand the core Git workflow used in real development environments.

This task includes:

* Learning **Git basics**
* Performing **init, clone, commit, push**
* Understanding **branching workflow**
* Learning **Pull Requests**
* Understanding **GitHub protection rules**

---

# Step 1: Initialize a Git Repository

Create a new Git repository in a project folder.

```bash
git init
# Initializes an empty Git repository in the current directory
```

Check repository status:

```bash
git status
# Shows current branch, staged files, and untracked files
```

---

# Step 2: Clone a Repository

Clone an existing repository from GitHub.

```bash
git clone <repository-url>
# Downloads the remote repository to your local machine
```

Example:

```bash
git clone https://github.com/username/project.git
# Creates a local copy of the GitHub repository
```

Move into the project directory:

```bash
cd project
# Navigate into the cloned repository
```

---

# Step 3: Add Files to Staging Area

Stage files before committing.

```bash
git add file.txt
# Adds a specific file to staging
```

Add all files:

```bash
git add .
# Stages all modified and new files
```

---

# Step 4: Commit Changes

Save changes in the repository history.

```bash
git commit -m "Add initial project files"
# Creates a snapshot of the current changes
```

Check commit history:

```bash
git log
# Displays commit history with commit IDs
```

---

# Step 5: Connect Local Repository to GitHub

Add remote repository.

```bash
git remote add origin https://github.com/username/repository.git
# Links local repository to GitHub
```

Verify remote:

```bash
git remote -v
# Shows configured remote repositories
```

---

# Step 6: Push Code to GitHub

Upload local commits to GitHub.

```bash
git push origin main
# Pushes commits to the main branch
```

First push (if branch not set):

```bash
git push -u origin main
# Sets upstream branch for future pushes
```

---

# Step 7: Branching Basics

Branches allow parallel development.

Create a new branch:

```bash
git branch feature-login
# Creates a new branch
```

Switch to branch:

```bash
git checkout feature-login
# Moves working directory to the new branch
```

Create and switch in one command:

```bash
git checkout -b feature-login
# Creates and switches to branch
```

List branches:

```bash
git branch
# Displays all local branches
```

---

# Step 8: Merge Branch

Merge feature branch into main branch.

```bash
git checkout main
# Switch to main branch
```

```bash
git merge feature-login
# Merges feature branch into main
```

---

# Step 9: Pull Latest Changes

Fetch and merge updates from GitHub.

```bash
git pull origin main
# Updates local repository with remote changes
```

---

# Step 10: Pull Requests (PR)

Pull Requests are used for **code review before merging changes**.

Typical workflow:

1. Create feature branch
2. Push branch to GitHub
3. Open Pull Request
4. Code review
5. Merge into main

Push feature branch:

```bash
git push origin feature-login
# Upload feature branch to GitHub
```

Then open PR on GitHub interface.

---

# Step 11: GitHub Protection Rules

Branch protection helps maintain code quality.

Common protection rules:

* Require **Pull Request before merging**
* Require **Code reviews**
* Prevent **direct pushes to main**
* Require **status checks before merging**

Example rule:

```
main branch → protected
All changes → must go through Pull Request
```

---

# Useful Git Commands (Quick Reference)

```bash
git status
# Shows repository status

git add .
# Stage all files

git commit -m "message"
# Save changes

git push
# Upload commits

git pull
# Get latest updates

git branch
# List branches

git checkout -b new-branch
# Create and switch branch
```

---

# Recommended Git Cheat Sheets

GitHub Official Git Cheat Sheet
https://education.github.com/git-cheat-sheet-education.pdf

Git SCM Documentation
https://git-scm.com/docs

Atlassian Git Tutorials
https://www.atlassian.com/git/tutorials

---

# Final Outcome

By completing **Day 02**, I successfully:

* Practiced **core Git commands**
* Managed repositories using **Git workflow**
* Learned **branch-based development**
* Understood **Pull Requests and collaboration workflow**
* Explored **GitHub protection rules**

This workflow is used in **professional software development teams and DevOps pipelines.**

---

# Next Step

**Day 03**
   
✅ Launch EC2 instance (Amazon Linux)    
✅ Connect via SSH and install essential packages
