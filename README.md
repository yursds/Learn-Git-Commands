# 🛠️ Git Commands Guide

## 📜 Table of Contents  
1. ⚙️ [Setup & Configuration](#-setup--configuration)  
2. 🆕 [Repository Basics](#-repository-basics)  
3. 📦 [File Management](#-file-management)  
4. 🌿 [Branching & Merging](#-branching--merging)  
5. 🔄 [Remote Collaboration](#-remote-collaboration)  
6. ⏪ [Undoing Changes](#-undoing-changes)  
7. 🚀 [Advanced Operations](#-advanced-operations)  
8. 🚨 [Danger Zone](#-danger-zone)  

---  

## ⚙️ Setup & Configuration  
### Configure Global Identity  
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```  

### Verify Settings  
```bash
git config --global --list
```  

---  

## 🆕 Repository Basics  
### Initialize Repository  
```bash
git init
```  

### Basic Commands  
```bash
git status       # Show working tree status
git log          # Show commit history
git reflog       # Show ALL actions history
```  

### First Commit  
```bash
git add .
git commit -m "Initial commit"
```  

---  

## 📦 File Management  
### Stage Files  
```bash
git add <file>      # Stage specific file
git add .           # Stage all changes
```  

### Remove Files  
```bash
git rm <file>               # Delete file and stage removal
git rm --cached <file>      # Stop tracking but keep file
```  

---  

## 🌿 Branching & Merging  
### Branch Operations  
```bash
git branch                     # List local branches
git branch -vva                # List all branches with details
git branch <new-branch>        # Create new branch
git checkout <branch>          # Switch to branch
git checkout -b <new-branch>   # Create + switch branch
```  

### Merge Strategies  
```bash
# Fast-forward merge (linear history)
git checkout main
git merge feature

# Three-way merge (explicit merge commit)
git merge --no-ff feature
```  

### Rebase Branch  
```bash
git checkout feature
git rebase main          # Move feature commits on top of main
```  

### Delete Branches  
```bash
git branch -d <branch>    # Safe delete (checks merge status)
git branch -D <branch>    # Force delete unmerged branch
```  

---  

## 🔄 Remote Collaboration  
### Connect to Remote  
```bash
git remote add origin https://github.com/<user/repo.git>
```  

### Push/Pull Changes  
```bash
git push -u origin main     # First push (set upstream)
git push                    # Subsequent pushes
git pull                    # Fetch + merge
```  

### Sync Forked Repository  
```bash
git remote add upstream https://github.com/<original/repo.git>
git fetch upstream
git merge upstream/main
```  

---  

## ⏪ Undoing Changes  
### Safe Undo  
```bash
git restore <file>          # Discard uncommitted changes
git revert <commit>         # Create undo commit
```  

### Reset Options  
```bash
git reset --soft HEAD~1     # Undo commit, keep changes staged
git reset --mixed HEAD~1    # Undo commit, unstage changes (default)
git reset --hard HEAD~1     # 💥 Destroy commit + changes
```  

---  

## 🚀 Advanced Operations  
### Submodules  
```bash
git submodule add https://github.com/<lib/repo.git>
git submodule update --init --recursive
```  

### Stash Changes  
```bash
git stash                   # Save temporary changes
git stash pop               # Restore last stashed changes
```  

### Cherry-picking  
```bash
git cherry-pick <commit>    # Apply specific commit
```  

---  

## 🚨 Danger Zone  
### Irreversible Actions  
```bash
git clean -fd               # 💀 Delete untracked files
git push --force            # 🚩 Overwrite remote history
```  

### Recovery Tools  
```bash
git reflog                  # Find lost commits
git fsck                    # Check repository integrity
```  

---  

## 🏁 Workflow Example  
### Typical Feature Workflow  
```bash
git checkout -b new-feature
# Make changes...
git add .
git commit -m "Implement new feature"
git checkout main
git merge new-feature
git branch -d new-feature
git push origin main
```  

### Emergency Fix  
```bash
git checkout -b hotfix main
# Apply fix...
git commit -m "Critical security patch"
git checkout main
git merge hotfix
git push origin main
git branch -d hotfix
```  

---  
