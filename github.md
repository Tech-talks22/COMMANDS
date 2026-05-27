# Git & GitHub Commands Reference

A complete topic-wise reference of Git and GitHub CLI commands.

---

## Table of Contents
1. [Setup & Configuration](#1-setup--configuration)
2. [Repository Basics](#2-repository-basics)
3. [Staging & Committing](#3-staging--committing)
4. [Branching](#4-branching)
5. [Merging & Rebasing](#5-merging--rebasing)
6. [Remote Repositories](#6-remote-repositories)
7. [Log & Diff](#7-log--diff)
8. [Undo & Reset](#8-undo--reset)
9. [Stash](#9-stash)
10. [Tags](#10-tags)
11. [GitHub CLI (gh)](#11-github-cli-gh)

---

## 1. Setup & Configuration

| Command | Description |
|--------|-------------|
| `git config --global user.name "Your Name"` | Set global username |
| `git config --global user.email "you@email.com"` | Set global email |
| `git config --list` | Show all config settings |
| `git config --global core.editor "code --wait"` | Set VS Code as default editor |
| `git config --global alias.st status` | Create a command alias |
| `git config --global color.ui auto` | Enable colored output |
| `git config --global merge.tool vimdiff` | Set merge tool |
| `git config --global pull.rebase false` | Use merge strategy for git pull |

---

## 2. Repository Basics

| Command | Description |
|--------|-------------|
| `git init` | Initialize a new local repository |
| `git init <folder>` | Create repo in a specific folder |
| `git clone <url>` | Clone a remote repository |
| `git clone <url> <dir>` | Clone into a custom directory name |
| `git clone --depth 1 <url>` | Shallow clone (latest commit only) |
| `git status` | Show working tree status |
| `git status -s` | Short/compact status output |
| `git help <command>` | Open help for a command |

---

## 3. Staging & Committing

| Command | Description |
|--------|-------------|
| `git add <file>` | Stage a specific file |
| `git add .` | Stage all changes in current directory |
| `git add -p` | Interactively stage chunks of changes |
| `git add -A` | Stage all changes including deletions |
| `git commit -m "message"` | Commit with an inline message |
| `git commit -am "message"` | Stage tracked files and commit in one step |
| `git commit --amend` | Modify the most recent commit |
| `git commit --amend --no-edit` | Amend commit without changing message |
| `git commit --allow-empty -m "msg"` | Create an empty commit |
| `git rm <file>` | Remove a file and stage the deletion |
| `git rm --cached <file>` | Untrack a file but keep it locally |
| `git mv <old> <new>` | Rename or move a file |

---

## 4. Branching

| Command | Description |
|--------|-------------|
| `git branch` | List all local branches |
| `git branch -a` | List local and remote branches |
| `git branch -r` | List remote branches only |
| `git branch <name>` | Create a new branch |
| `git branch -d <name>` | Delete a branch (safe) |
| `git branch -D <name>` | Force delete a branch |
| `git branch -m <old> <new>` | Rename a branch |
| `git checkout <branch>` | Switch to an existing branch |
| `git checkout -b <name>` | Create and switch to new branch |
| `git switch <branch>` | Modern way to switch branch |
| `git switch -c <name>` | Modern way to create and switch |
| `git branch --merged` | List branches merged into HEAD |
| `git branch --no-merged` | List unmerged branches |

---

## 5. Merging & Rebasing

| Command | Description |
|--------|-------------|
| `git merge <branch>` | Merge a branch into current branch |
| `git merge --no-ff <branch>` | Merge with a merge commit always |
| `git merge --squash <branch>` | Squash all commits before merging |
| `git merge --abort` | Abort an in-progress merge |
| `git rebase <branch>` | Rebase current branch onto another |
| `git rebase -i HEAD~N` | Interactive rebase for last N commits |
| `git rebase --continue` | Continue rebase after resolving conflicts |
| `git rebase --skip` | Skip the current conflicting commit |
| `git rebase --abort` | Abort the rebase operation |
| `git cherry-pick <hash>` | Apply a specific commit to current branch |
| `git cherry-pick A..B` | Apply a range of commits |
| `git cherry-pick --no-commit <hash>` | Cherry-pick without auto-committing |

---

## 6. Remote Repositories

| Command | Description |
|--------|-------------|
| `git remote -v` | List remotes with URLs |
| `git remote add origin <url>` | Add a remote named origin |
| `git remote rename <old> <new>` | Rename a remote |
| `git remote remove <name>` | Remove a remote |
| `git remote set-url origin <url>` | Change the remote URL |
| `git fetch` | Download changes but don't merge |
| `git fetch --all` | Fetch from all remotes |
| `git fetch --prune` | Remove stale remote-tracking refs |
| `git pull` | Fetch and merge remote changes |
| `git pull --rebase` | Fetch and rebase instead of merge |
| `git push origin <branch>` | Push branch to remote |
| `git push -u origin <branch>` | Push and set upstream tracking |
| `git push --force-with-lease` | Safe force push |
| `git push --force` | Force push (overwrites remote history) |
| `git push origin --delete <branch>` | Delete a remote branch |
| `git push origin --tags` | Push all tags to remote |

---

## 7. Log & Diff

| Command | Description |
|--------|-------------|
| `git log` | Show full commit history |
| `git log --oneline` | Compact one-line commit history |
| `git log --oneline --graph --all` | Visual branch graph in terminal |
| `git log -n 5` | Show last 5 commits |
| `git log --author="name"` | Filter commits by author |
| `git log --since="2 weeks ago"` | Filter commits by date |
| `git log --grep="keyword"` | Search commit messages |
| `git log -- <file>` | Show history for a specific file |
| `git log -p -- <file>` | Show changes per commit for a file |
| `git diff` | Show unstaged changes |
| `git diff --staged` | Show staged changes |
| `git diff <branch1>..<branch2>` | Compare two branches |
| `git diff HEAD~1 HEAD` | Show changes in the last commit |
| `git show <hash>` | Show details of a specific commit |
| `git blame <file>` | Show who last changed each line |
| `git shortlog -sn` | Commit count per contributor |
| `git bisect start` | Start binary search for a bug |

---

## 8. Undo & Reset

| Command | Description |
|--------|-------------|
| `git restore <file>` | Discard unstaged changes in a file |
| `git restore --staged <file>` | Unstage a file (keep changes) |
| `git restore .` | Discard all unstaged changes |
| `git revert <hash>` | Create a new commit that undoes a commit |
| `git revert HEAD` | Safely undo the last commit |
| `git reset --soft HEAD~1` | Undo last commit, keep changes staged |
| `git reset --mixed HEAD~1` | Undo last commit, keep changes unstaged |
| `git reset --hard HEAD~1` | Undo last commit and discard all changes |
| `git reset --hard origin/main` | Reset local branch to match remote |
| `git clean -fd` | Delete untracked files and directories |
| `git clean -n` | Preview what clean would remove |
| `git reflog` | History of HEAD movements (recovery tool) |

---

## 9. Stash

| Command | Description |
|--------|-------------|
| `git stash` | Save uncommitted changes temporarily |
| `git stash push -m "label"` | Stash with a descriptive label |
| `git stash -u` | Stash including untracked files |
| `git stash list` | List all stash entries |
| `git stash pop` | Apply latest stash and remove it |
| `git stash apply stash@{N}` | Apply a specific stash entry |
| `git stash drop stash@{N}` | Delete a specific stash entry |
| `git stash clear` | Delete all stash entries |
| `git stash branch <name>` | Create a branch from a stash |
| `git stash show -p` | Show diff of the latest stash |

---

## 10. Tags

| Command | Description |
|--------|-------------|
| `git tag` | List all tags |
| `git tag <name>` | Create a lightweight tag |
| `git tag -a <name> -m "msg"` | Create an annotated tag |
| `git tag -a <name> <hash>` | Tag a specific past commit |
| `git tag -d <name>` | Delete a local tag |
| `git tag -l "v1.*"` | List tags matching a pattern |
| `git show <tag>` | Show tag details and commit info |
| `git push origin <tag>` | Push a specific tag to remote |
| `git push origin --tags` | Push all tags to remote |
| `git push origin --delete <tag>` | Delete a tag from remote |
| `git checkout <tag>` | Check out a tag (detached HEAD state) |

---

## 11. GitHub CLI (gh)

### Authentication
| Command | Description |
|--------|-------------|
| `gh auth login` | Authenticate with GitHub |
| `gh auth status` | Check authentication status |
| `gh auth logout` | Log out from GitHub |

### Repository
| Command | Description |
|--------|-------------|
| `gh repo create` | Create a new GitHub repository |
| `gh repo clone <owner/repo>` | Clone a GitHub repo |
| `gh repo fork` | Fork the current repository |
| `gh repo view` | View current repo in browser |
| `gh repo list` | List your GitHub repositories |

### Pull Requests
| Command | Description |
|--------|-------------|
| `gh pr create` | Open a new pull request |
| `gh pr list` | List open pull requests |
| `gh pr view <number>` | View a specific PR |
| `gh pr checkout <number>` | Check out a PR locally |
| `gh pr merge <number>` | Merge a pull request |
| `gh pr review` | Submit a review on a PR |
| `gh pr close <number>` | Close a pull request |
| `gh pr diff <number>` | Show diff of a PR |

### Issues
| Command | Description |
|--------|-------------|
| `gh issue create` | Create a new issue |
| `gh issue list` | List issues in the repo |
| `gh issue view <number>` | View a specific issue |
| `gh issue close <number>` | Close an issue |
| `gh issue reopen <number>` | Reopen a closed issue |

### Actions & Workflows
| Command | Description |
|--------|-------------|
| `gh workflow list` | List GitHub Actions workflows |
| `gh workflow run <name>` | Trigger a workflow manually |
| `gh run list` | List recent workflow runs |
| `gh run watch` | Watch a live workflow run |
| `gh run view <id>` | View details of a run |

### Releases & Gists
| Command | Description |
|--------|-------------|
| `gh release create <tag>` | Create a new release |
| `gh release list` | List all releases |
| `gh release view <tag>` | View a specific release |
| `gh gist create <file>` | Create a Gist from a file |
| `gh gist list` | List your Gists |
| `gh api <endpoint>` | Call the GitHub API directly |

---

*Reference covers Git 2.x and GitHub CLI (gh) 2.x*
