# 🛠️ Essential Git Command Cheat Sheet

## 1. Branching & Navigation
* **Create a new branch:**
  `git checkout -b branch-name`
* **Switch to an existing branch:**
  `git checkout branch-name`
* **List all branches:**
  `git branch`
* **Delete a local branch:**
  `git branch -d branch-name`
  *(Use `-D` for a forced delete if the branch has unmerged changes)*

## 2. Merging & Rebasing
* **Merge a branch into your current branch:**
  1. `git checkout main`
  2. `git merge branch-name`
* **Rebase your current branch onto another (Cleaner history):**
  1. `git checkout feature-branch`
  2. `git rebase main`
  *(If conflicts arise, fix the files, then `git add .` and `git rebase --continue`)*

## 3. Modifying & Undoing
* **Check current status:**
  `git status`
* **Undo staged changes (unstage a file):**
  `git restore --staged filename`
* **Discard local changes in a file:**
  `git restore filename`
* **Rename a file (Git-tracked):**
  `git mv old-name new-name`
* **Remove a file from Git (but keep it on disk):**
  `git rm --cached filename`

## 4. Working with Remotes
* **View all configured remotes:**
  `git remote -v`
* **Update local branch with remote changes:**
  `git pull origin main`
* **Delete a remote branch:**
  `git push origin --delete branch-name`

## 5. Log & History
* **See a clean, one-line commit history:**
  `git log --oneline --graph --all`
* **Undo the last commit (keep your changes staged):**
  `git reset --soft HEAD~1`
* **Undo the last commit (delete changes forever):**
  `git reset --hard HEAD~1`