# Git & GitHub Commands — Complete Reference

A comprehensive topic-wise reference of Git and GitHub CLI commands.

---

## Table of Contents
1. [Setup & Configuration](#1-setup--configuration)
2. [Repository Basics](#2-repository-basics)
3. [Staging & Committing](#3-staging--committing)
4. [Branching](#4-branching)
5. [Merging & Rebasing](#5-merging--rebasing)
6. [Remote Repositories](#6-remote-repositories)
7. [Log & History](#7-log--history)
8. [Diff & Comparison](#8-diff--comparison)
9. [Undo & Reset](#9-undo--reset)
10. [Stash](#10-stash)
11. [Tags](#11-tags)
12. [Submodules](#12-submodules)
13. [Worktrees](#13-worktrees)
14. [Bisect (Bug Hunting)](#14-bisect-bug-hunting)
15. [Grep & Search](#15-grep--search)
16. [Archive & Export](#16-archive--export)
17. [Hooks](#17-hooks)
18. [Reflog & Recovery](#18-reflog--recovery)
19. [Patch & Apply](#19-patch--apply)
20. [Sparse Checkout & Partial Clone](#20-sparse-checkout--partial-clone)
21. [Performance & Maintenance](#21-performance--maintenance)
22. [GitHub CLI — Repos & Auth](#22-github-cli--repos--auth)
23. [GitHub CLI — Pull Requests](#23-github-cli--pull-requests)
24. [GitHub CLI — Issues](#24-github-cli--issues)
25. [GitHub CLI — Actions & Workflows](#25-github-cli--actions--workflows)
26. [GitHub CLI — Releases & Gists](#26-github-cli--releases--gists)
27. [GitHub CLI — SSH & GPG Keys](#27-github-cli--ssh--gpg-keys)
28. [Advanced Git Internals](#28-advanced-git-internals)

---

## 1. Setup & Configuration

| Command | Description |
|---------|-------------|
| `git config --global user.name "Your Name"` | Set global username |
| `git config --global user.email "you@email.com"` | Set global email |
| `git config --local user.name "Name"` | Set username for current repo only |
| `git config --list` | Show all config settings |
| `git config --list --show-origin` | Show all configs with file locations |
| `git config --global core.editor "code --wait"` | Set VS Code as default editor |
| `git config --global core.editor "vim"` | Set Vim as default editor |
| `git config --global alias.st status` | Create alias: `git st` = `git status` |
| `git config --global alias.co checkout` | Create alias: `git co` = `git checkout` |
| `git config --global alias.br branch` | Create alias: `git br` = `git branch` |
| `git config --global alias.lg "log --oneline --graph --all"` | Create pretty log alias |
| `git config --global color.ui auto` | Enable colored output |
| `git config --global merge.tool vimdiff` | Set merge tool |
| `git config --global pull.rebase false` | Use merge for git pull |
| `git config --global pull.rebase true` | Use rebase for git pull |
| `git config --global init.defaultBranch main` | Set default branch name to main |
| `git config --global core.autocrlf true` | Auto-convert CRLF on Windows |
| `git config --global core.autocrlf input` | Normalize line endings on Mac/Linux |
| `git config --global push.default current` | Push current branch by default |
| `git config --global credential.helper cache` | Cache credentials in memory |
| `git config --global credential.helper store` | Store credentials on disk |
| `git config --global http.proxy http://proxy:port` | Set HTTP proxy |
| `git config --unset <key>` | Remove a specific config entry |
| `git config --global --edit` | Open global config in editor |

---

## 2. Repository Basics

| Command | Description |
|---------|-------------|
| `git init` | Initialize a new local repository |
| `git init <folder>` | Create repo in a specific folder |
| `git init --bare` | Create a bare repo (no working tree) |
| `git clone <url>` | Clone a remote repository |
| `git clone <url> <dir>` | Clone into a custom directory name |
| `git clone --depth 1 <url>` | Shallow clone (latest commit only) |
| `git clone --branch <name> <url>` | Clone a specific branch |
| `git clone --single-branch <url>` | Clone only the default branch |
| `git clone --recurse-submodules <url>` | Clone including all submodules |
| `git clone --mirror <url>` | Full mirror clone of a repo |
| `git status` | Show working tree status |
| `git status -s` | Short/compact status output |
| `git status -sb` | Short status with branch info |
| `git help <command>` | Open help for a command |
| `git <command> --help` | Show help for any command |
| `git version` | Show installed Git version |

---

## 3. Staging & Committing

| Command | Description |
|---------|-------------|
| `git add <file>` | Stage a specific file |
| `git add .` | Stage all changes in current directory |
| `git add -A` | Stage all changes including deletions |
| `git add -p` | Interactively stage hunks of changes |
| `git add -i` | Interactive staging menu |
| `git add *.js` | Stage all JS files |
| `git add src/` | Stage all files in a folder |
| `git commit -m "message"` | Commit with an inline message |
| `git commit -am "message"` | Stage tracked files and commit |
| `git commit --amend` | Modify the most recent commit |
| `git commit --amend --no-edit` | Amend commit without changing message |
| `git commit --amend -m "new msg"` | Amend with a new message |
| `git commit --allow-empty -m "msg"` | Create an empty commit |
| `git commit --no-verify -m "msg"` | Commit skipping pre-commit hooks |
| `git commit -S -m "msg"` | GPG sign the commit |
| `git rm <file>` | Remove a file and stage the deletion |
| `git rm --cached <file>` | Untrack a file but keep it locally |
| `git rm -r --cached <folder>` | Untrack a whole folder |
| `git mv <old> <new>` | Rename or move a file |
| `git ls-files` | List all tracked files |
| `git ls-files --others` | List untracked files |
| `git ls-files --ignored` | List ignored files |
| `git update-index --assume-unchanged <file>` | Ignore local changes to a tracked file |
| `git update-index --no-assume-unchanged <file>` | Re-track a file |

---

## 4. Branching

| Command | Description |
|---------|-------------|
| `git branch` | List all local branches |
| `git branch -a` | List local and remote branches |
| `git branch -r` | List remote branches only |
| `git branch -v` | List branches with last commit |
| `git branch -vv` | List branches with tracking info |
| `git branch <name>` | Create a new branch |
| `git branch <name> <hash>` | Create a branch from a commit |
| `git branch -d <name>` | Delete a branch (safe) |
| `git branch -D <name>` | Force delete a branch |
| `git branch -m <old> <new>` | Rename a branch |
| `git branch -M <new>` | Rename current branch forcefully |
| `git branch --merged` | List branches merged into HEAD |
| `git branch --no-merged` | List branches not yet merged |
| `git branch --merged | grep -v "\*" | xargs git branch -d` | Delete all merged branches |
| `git checkout <branch>` | Switch to an existing branch |
| `git checkout -b <name>` | Create and switch to new branch |
| `git checkout -b <name> origin/<name>` | Create local branch tracking remote |
| `git checkout -` | Switch to previous branch |
| `git switch <branch>` | Modern way to switch branch |
| `git switch -c <name>` | Modern way to create and switch |
| `git switch -` | Switch to previous branch (modern) |
| `git push origin --delete <branch>` | Delete a remote branch |
| `git remote prune origin` | Remove stale local remote-tracking refs |

---

## 5. Merging & Rebasing

| Command | Description |
|---------|-------------|
| `git merge <branch>` | Merge a branch into current branch |
| `git merge --no-ff <branch>` | Merge with a merge commit always |
| `git merge --squash <branch>` | Squash all commits before merging |
| `git merge --abort` | Abort an in-progress merge |
| `git merge --continue` | Continue merge after resolving conflicts |
| `git merge -s ours <branch>` | Merge but keep current branch content |
| `git merge -X theirs <branch>` | Auto-resolve conflicts with theirs |
| `git merge -X ours <branch>` | Auto-resolve conflicts with ours |
| `git rebase <branch>` | Rebase current branch onto another |
| `git rebase -i HEAD~N` | Interactive rebase for last N commits |
| `git rebase -i --root` | Interactive rebase from the first commit |
| `git rebase --continue` | Continue rebase after resolving conflicts |
| `git rebase --skip` | Skip the current conflicting commit |
| `git rebase --abort` | Abort the rebase |
| `git rebase --autosquash` | Auto squash fixup! commits |
| `git rebase --autostash` | Stash changes before rebasing |
| `git cherry-pick <hash>` | Apply a specific commit to current branch |
| `git cherry-pick A..B` | Apply a range of commits |
| `git cherry-pick --no-commit <hash>` | Cherry-pick without auto-committing |
| `git cherry-pick --abort` | Abort a cherry-pick |
| `git cherry-pick --continue` | Continue after resolving conflicts |
| `git mergetool` | Open visual merge conflict tool |

---

## 6. Remote Repositories

| Command | Description |
|---------|-------------|
| `git remote -v` | List remotes with URLs |
| `git remote add origin <url>` | Add a remote named origin |
| `git remote add upstream <url>` | Add upstream remote for forks |
| `git remote rename <old> <new>` | Rename a remote |
| `git remote remove <name>` | Remove a remote |
| `git remote set-url origin <url>` | Change the remote URL |
| `git remote set-url --add origin <url>` | Add a second push URL |
| `git remote show origin` | Show detailed info about origin |
| `git remote update` | Fetch updates from all remotes |
| `git fetch` | Download changes but don't merge |
| `git fetch --all` | Fetch from all remotes |
| `git fetch --prune` | Remove stale remote-tracking refs |
| `git fetch origin <branch>` | Fetch a specific remote branch |
| `git pull` | Fetch and merge remote changes |
| `git pull --rebase` | Fetch and rebase instead of merge |
| `git pull --no-commit` | Fetch and merge but don't auto-commit |
| `git pull origin <branch>` | Pull a specific remote branch |
| `git push origin <branch>` | Push branch to remote |
| `git push -u origin <branch>` | Push and set upstream tracking |
| `git push --force-with-lease` | Safe force push |
| `git push --force` | Force push (overwrites remote history) |
| `git push origin --delete <branch>` | Delete a remote branch |
| `git push origin --tags` | Push all tags to remote |
| `git push --all origin` | Push all local branches to remote |
| `git push --dry-run` | Simulate a push without sending |

---

## 7. Log & History

| Command | Description |
|---------|-------------|
| `git log` | Show full commit history |
| `git log --oneline` | Compact one-line commit history |
| `git log --oneline --graph --all` | Visual branch graph in terminal |
| `git log --oneline --decorate` | Show refs alongside commits |
| `git log -n 5` | Show last 5 commits |
| `git log --author="name"` | Filter commits by author |
| `git log --since="2 weeks ago"` | Filter commits since a date |
| `git log --until="2024-01-01"` | Filter commits until a date |
| `git log --grep="keyword"` | Search commit messages |
| `git log -S "string"` | Find commits that added/removed a string |
| `git log -G "regex"` | Find commits matching a regex |
| `git log -- <file>` | History of a specific file |
| `git log -p -- <file>` | Show changes per commit for a file |
| `git log --follow -- <file>` | Follow file history through renames |
| `git log --stat` | Show files changed per commit |
| `git log --name-only` | Show only filenames changed |
| `git log --name-status` | Show files with change type (A/M/D) |
| `git log --pretty=format:"%h %s"` | Custom log format |
| `git log --merges` | Show only merge commits |
| `git log --no-merges` | Exclude merge commits |
| `git log branch1..branch2` | Commits in branch2 not in branch1 |
| `git log branch1...branch2` | Commits unique to each branch |
| `git shortlog -sn` | Commit count per contributor |
| `git shortlog -sne` | Commit count with emails |
| `git show <hash>` | Show details of a specific commit |
| `git show <hash>:<file>` | Show a file at a specific commit |
| `git show HEAD` | Show the latest commit details |
| `git show HEAD~3` | Show 3 commits ago |
| `git blame <file>` | Show who last changed each line |
| `git blame -L 10,20 <file>` | Blame only lines 10–20 |
| `git whatchanged` | Show what files changed per commit |

---

## 8. Diff & Comparison

| Command | Description |
|---------|-------------|
| `git diff` | Show unstaged changes |
| `git diff --staged` | Show staged changes |
| `git diff HEAD` | All changes since last commit |
| `git diff <hash1> <hash2>` | Diff between two commits |
| `git diff <branch1>..<branch2>` | Diff between two branches |
| `git diff <branch1>...<branch2>` | Diff from common ancestor |
| `git diff HEAD~1 HEAD` | Changes in the last commit |
| `git diff --stat` | Summary of changes (files + lines) |
| `git diff --name-only` | List only changed file names |
| `git diff --name-status` | Files changed with status (A/M/D) |
| `git diff --word-diff` | Show word-level differences |
| `git diff --color-words` | Highlight changed words in color |
| `git diff -w` | Ignore whitespace changes |
| `git diff -- <file>` | Diff for a specific file |
| `git diff origin/main` | Compare local with remote main |
| `git difftool` | Open diff in visual diff tool |

---

## 9. Undo & Reset

| Command | Description |
|---------|-------------|
| `git restore <file>` | Discard unstaged changes in a file |
| `git restore --staged <file>` | Unstage a file (keep changes) |
| `git restore .` | Discard all unstaged changes |
| `git restore --source=HEAD~2 <file>` | Restore file from 2 commits ago |
| `git revert <hash>` | New commit that undoes a commit |
| `git revert HEAD` | Safely undo the last commit |
| `git revert HEAD~3..HEAD` | Revert last 3 commits |
| `git revert --no-commit <hash>` | Revert without auto-committing |
| `git revert --abort` | Abort an in-progress revert |
| `git reset --soft HEAD~1` | Undo last commit, keep staged |
| `git reset --mixed HEAD~1` | Undo last commit, keep unstaged |
| `git reset --hard HEAD~1` | Undo last commit, discard changes |
| `git reset --hard origin/main` | Reset local branch to match remote |
| `git reset HEAD <file>` | Unstage a file (old syntax) |
| `git clean -fd` | Delete untracked files and dirs |
| `git clean -fX` | Delete only ignored files |
| `git clean -fdx` | Delete all untracked + ignored files |
| `git clean -n` | Preview what clean would remove |
| `git clean -i` | Interactive clean mode |

---

## 10. Stash

| Command | Description |
|---------|-------------|
| `git stash` | Save uncommitted changes temporarily |
| `git stash push -m "label"` | Stash with a descriptive label |
| `git stash -u` | Stash including untracked files |
| `git stash -a` | Stash including ignored files too |
| `git stash -p` | Interactively pick what to stash |
| `git stash list` | List all stash entries |
| `git stash show` | Show summary of latest stash |
| `git stash show -p` | Show full diff of latest stash |
| `git stash show stash@{N}` | Show summary of a specific stash |
| `git stash pop` | Apply latest stash and remove it |
| `git stash apply` | Apply latest stash but keep it |
| `git stash apply stash@{N}` | Apply a specific stash entry |
| `git stash drop stash@{N}` | Delete a specific stash entry |
| `git stash clear` | Delete all stash entries |
| `git stash branch <name>` | Create a branch from the latest stash |
| `git stash branch <name> stash@{N}` | Create branch from a specific stash |

---

## 11. Tags

| Command | Description |
|---------|-------------|
| `git tag` | List all tags |
| `git tag -l "v1.*"` | List tags matching a pattern |
| `git tag <name>` | Create a lightweight tag |
| `git tag -a <name> -m "msg"` | Create an annotated tag |
| `git tag -a <name> <hash>` | Tag a specific past commit |
| `git tag -s <name> -m "msg"` | Create a GPG-signed tag |
| `git tag -d <name>` | Delete a local tag |
| `git tag -f <name>` | Move an existing tag to current HEAD |
| `git show <tag>` | Show tag details and commit info |
| `git describe` | Show the most recent tag reachable |
| `git describe --tags --abbrev=0` | Show the latest tag name only |
| `git checkout <tag>` | Check out a tag (detached HEAD) |
| `git push origin <tag>` | Push a specific tag to remote |
| `git push origin --tags` | Push all tags to remote |
| `git push origin --delete <tag>` | Delete a tag from remote |
| `git fetch --tags` | Fetch all tags from remote |

---

## 12. Submodules

| Command | Description |
|---------|-------------|
| `git submodule add <url>` | Add a submodule to the repo |
| `git submodule add <url> <path>` | Add submodule at a specific path |
| `git submodule init` | Initialize submodule config |
| `git submodule update` | Fetch and checkout submodule commits |
| `git submodule update --init` | Init and update in one step |
| `git submodule update --init --recursive` | Update all nested submodules |
| `git submodule update --remote` | Update submodules to latest remote |
| `git submodule status` | Show current status of all submodules |
| `git submodule foreach git pull` | Run git pull in every submodule |
| `git submodule foreach --recursive git status` | Status check in all submodules |
| `git submodule sync` | Sync submodule remote URLs |
| `git submodule deinit <path>` | Unregister a submodule |
| `git rm <submodule-path>` | Remove a submodule |
| `git clone --recurse-submodules <url>` | Clone with all submodules |

---

## 13. Worktrees

| Command | Description |
|---------|-------------|
| `git worktree add <path> <branch>` | Check out a branch in a new folder |
| `git worktree add -b <name> <path>` | Create new branch in new folder |
| `git worktree list` | List all linked worktrees |
| `git worktree remove <path>` | Remove a worktree |
| `git worktree prune` | Remove stale worktree references |
| `git worktree lock <path>` | Prevent a worktree from being pruned |
| `git worktree unlock <path>` | Unlock a locked worktree |

---

## 14. Bisect (Bug Hunting)

| Command | Description |
|---------|-------------|
| `git bisect start` | Start binary search for a bug |
| `git bisect bad` | Mark current commit as bad |
| `git bisect good <hash>` | Mark a known good commit |
| `git bisect bad <hash>` | Mark a specific commit as bad |
| `git bisect skip` | Skip the current commit |
| `git bisect reset` | End bisect and return to HEAD |
| `git bisect log` | Show the bisect log |
| `git bisect run <script>` | Automate bisect with a test script |
| `git bisect visualize` | Visualize remaining commits to check |

---

## 15. Grep & Search

| Command | Description |
|---------|-------------|
| `git grep "pattern"` | Search for a pattern in tracked files |
| `git grep -n "pattern"` | Search with line numbers |
| `git grep -i "pattern"` | Case-insensitive search |
| `git grep -l "pattern"` | List filenames with matches only |
| `git grep -c "pattern"` | Count matches per file |
| `git grep "pattern" -- "*.js"` | Search only in JS files |
| `git grep "pattern" <hash>` | Search in a specific commit |
| `git grep -e "pat1" --and -e "pat2"` | Match both patterns |
| `git log -S "string"` | Find commits that changed a string |
| `git log -G "regex"` | Find commits matching a regex pattern |

---

## 16. Archive & Export

| Command | Description |
|---------|-------------|
| `git archive --format=zip HEAD > out.zip` | Export repo as ZIP |
| `git archive --format=tar HEAD > out.tar` | Export repo as TAR |
| `git archive --prefix=proj/ HEAD | gzip > proj.tar.gz` | Export with folder prefix |
| `git archive HEAD -- <folder> > out.tar` | Archive only a specific folder |
| `git archive <tag> --format=zip > v1.zip` | Archive a specific tag as ZIP |
| `git bundle create repo.bundle HEAD` | Bundle entire repo into one file |
| `git bundle create repo.bundle --all` | Bundle all branches |
| `git clone repo.bundle <dir>` | Restore a repo from a bundle |
| `git bundle verify repo.bundle` | Verify a bundle file is valid |

---

## 17. Hooks

| Command / File | Description |
|---------------|-------------|
| `.git/hooks/pre-commit` | Runs before every commit |
| `.git/hooks/commit-msg` | Validates commit message format |
| `.git/hooks/post-commit` | Runs after every commit |
| `.git/hooks/pre-push` | Runs before pushing to remote |
| `.git/hooks/pre-rebase` | Runs before a rebase begins |
| `.git/hooks/post-merge` | Runs after a merge completes |
| `.git/hooks/post-checkout` | Runs after checkout or branch switch |
| `.git/hooks/post-receive` | Server-side hook after receiving push |
| `.git/hooks/prepare-commit-msg` | Pre-fills the commit message editor |
| `chmod +x .git/hooks/<hookname>` | Make a hook executable |

> Tip: Use tools like **Husky** (`npx husky init`) for managing hooks in Node.js projects.

---

## 18. Reflog & Recovery

| Command | Description |
|---------|-------------|
| `git reflog` | Show history of all HEAD movements |
| `git reflog show <branch>` | Reflog for a specific branch |
| `git reflog expire --all` | Expire all reflog entries |
| `git checkout <hash>` | Check out any commit by hash |
| `git branch <name> <hash>` | Create a branch from a lost commit |
| `git reset --hard <hash>` | Restore to a specific reflog state |
| `git cherry-pick <hash>` | Recover a specific dropped commit |
| `git fsck --lost-found` | Find dangling/unreachable objects |
| `git gc` | Clean up and optimize the repo |
| `git prune` | Remove unreachable objects |

---

## 19. Patch & Apply

| Command | Description |
|---------|-------------|
| `git format-patch -1 <hash>` | Create a patch from a commit |
| `git format-patch HEAD~3` | Create patches for last 3 commits |
| `git format-patch <branch>` | Patches for commits not in branch |
| `git apply <patch-file>` | Apply a patch file |
| `git apply --check <patch-file>` | Check if patch would apply cleanly |
| `git am <patch-file>` | Apply patch and keep commit info |
| `git am --skip` | Skip a failing patch |
| `git am --abort` | Abort patch application |
| `git diff > changes.patch` | Save diff as a patch file |
| `git apply changes.patch` | Apply a saved diff patch |

---

## 20. Sparse Checkout & Partial Clone

| Command | Description |
|---------|-------------|
| `git sparse-checkout init` | Enable sparse checkout mode |
| `git sparse-checkout set <folder>` | Check out only a specific folder |
| `git sparse-checkout add <folder>` | Add another folder to sparse set |
| `git sparse-checkout list` | List current sparse paths |
| `git sparse-checkout disable` | Disable sparse checkout |
| `git clone --filter=blob:none <url>` | Partial clone (no file blobs) |
| `git clone --filter=tree:0 <url>` | Treeless partial clone |
| `git fetch --filter=blob:none` | Fetch without file content |

---

## 21. Performance & Maintenance

| Command | Description |
|---------|-------------|
| `git gc` | Run garbage collection |
| `git gc --aggressive` | Aggressive optimization (slower) |
| `git prune` | Remove unreachable loose objects |
| `git repack -a -d` | Repack objects into a single pack |
| `git count-objects -v` | Show object storage stats |
| `git fsck` | Verify integrity of the repo |
| `git maintenance start` | Enable background maintenance tasks |
| `git maintenance stop` | Disable background maintenance |
| `git maintenance run` | Manually run maintenance |
| `git commit-graph write` | Speed up log/graph traversal |
| `git multi-pack-index write` | Write multi-pack index for speed |
| `git lfs install` | Set up Git Large File Storage |
| `git lfs track "*.psd"` | Track large files with LFS |
| `git lfs ls-files` | List LFS-tracked files |
| `git lfs fetch` | Fetch LFS files from remote |
| `git lfs pull` | Pull LFS content |

---

## 22. GitHub CLI — Repos & Auth

| Command | Description |
|---------|-------------|
| `gh auth login` | Authenticate with GitHub |
| `gh auth login --with-token` | Authenticate with a token from stdin |
| `gh auth status` | Check authentication status |
| `gh auth logout` | Log out from GitHub |
| `gh auth refresh` | Refresh stored credentials |
| `gh repo create` | Create a new GitHub repository |
| `gh repo create <name> --public` | Create a public repo |
| `gh repo create <name> --private` | Create a private repo |
| `gh repo create <name> --clone` | Create and clone immediately |
| `gh repo clone <owner/repo>` | Clone a GitHub repo |
| `gh repo fork` | Fork the current repository |
| `gh repo fork --clone` | Fork and clone in one step |
| `gh repo view` | View current repo in terminal |
| `gh repo view --web` | Open current repo in browser |
| `gh repo list` | List your GitHub repositories |
| `gh repo list <org>` | List repos in an organization |
| `gh repo rename <name>` | Rename the current repo |
| `gh repo delete <name>` | Delete a repository |
| `gh repo archive <name>` | Archive a repository |
| `gh repo sync` | Sync a fork with its upstream |
| `gh repo set-default` | Set the default remote repo |
| `gh browse` | Open repo in browser |
| `gh browse <file>` | Open a file on GitHub in browser |
| `gh api <endpoint>` | Call the GitHub API directly |
| `gh api graphql -f query='...'` | Call the GitHub GraphQL API |

---

## 23. GitHub CLI — Pull Requests

| Command | Description |
|---------|-------------|
| `gh pr create` | Open a new pull request |
| `gh pr create --title "T" --body "B"` | Create PR with title and body |
| `gh pr create --draft` | Create a draft pull request |
| `gh pr create --base <branch>` | Create PR targeting a specific base |
| `gh pr create --label "bug"` | Create PR with a label |
| `gh pr create --reviewer <user>` | Request a reviewer |
| `gh pr list` | List open pull requests |
| `gh pr list --state closed` | List closed pull requests |
| `gh pr list --author <user>` | Filter PRs by author |
| `gh pr list --label "bug"` | Filter PRs by label |
| `gh pr view <number>` | View a specific PR in terminal |
| `gh pr view <number> --web` | Open a PR in browser |
| `gh pr checkout <number>` | Check out a PR locally |
| `gh pr merge <number>` | Merge a pull request |
| `gh pr merge <number> --squash` | Squash merge a PR |
| `gh pr merge <number> --rebase` | Rebase merge a PR |
| `gh pr merge --auto` | Enable auto-merge when checks pass |
| `gh pr review` | Submit a review on a PR |
| `gh pr review --approve` | Approve a PR |
| `gh pr review --request-changes -b "msg"` | Request changes on a PR |
| `gh pr review --comment -b "msg"` | Leave a comment on a PR |
| `gh pr close <number>` | Close a pull request |
| `gh pr reopen <number>` | Reopen a closed PR |
| `gh pr diff <number>` | Show the diff of a PR |
| `gh pr edit <number>` | Edit PR title, body, labels |
| `gh pr checks <number>` | Show CI check statuses for a PR |
| `gh pr comment <number> -b "msg"` | Add a comment to a PR |
| `gh pr ready <number>` | Mark a draft PR as ready |
| `gh pr lock <number>` | Lock conversation on a PR |

---

## 24. GitHub CLI — Issues

| Command | Description |
|---------|-------------|
| `gh issue create` | Create a new issue |
| `gh issue create --title "T" --body "B"` | Create issue with title and body |
| `gh issue create --label "bug"` | Create issue with a label |
| `gh issue create --assignee <user>` | Assign the issue to a user |
| `gh issue create --milestone "v1"` | Attach issue to a milestone |
| `gh issue list` | List open issues |
| `gh issue list --state closed` | List closed issues |
| `gh issue list --author <user>` | Filter by author |
| `gh issue list --label "bug"` | Filter by label |
| `gh issue list --assignee <user>` | Filter by assignee |
| `gh issue view <number>` | View a specific issue |
| `gh issue view <number> --web` | Open issue in browser |
| `gh issue close <number>` | Close an issue |
| `gh issue reopen <number>` | Reopen a closed issue |
| `gh issue edit <number>` | Edit issue title, body, labels |
| `gh issue comment <number> -b "msg"` | Add a comment to an issue |
| `gh issue pin <number>` | Pin an issue to the repo |
| `gh issue transfer <number> <repo>` | Transfer issue to another repo |
| `gh issue delete <number>` | Delete an issue |
| `gh issue lock <number>` | Lock conversation on an issue |

---

## 25. GitHub CLI — Actions & Workflows

| Command | Description |
|---------|-------------|
| `gh workflow list` | List GitHub Actions workflows |
| `gh workflow view <name>` | View details of a workflow |
| `gh workflow enable <name>` | Enable a workflow |
| `gh workflow disable <name>` | Disable a workflow |
| `gh workflow run <name>` | Trigger a workflow manually |
| `gh workflow run <name> -f key=val` | Trigger workflow with inputs |
| `gh run list` | List recent workflow runs |
| `gh run list --workflow <name>` | Filter runs by workflow |
| `gh run view <id>` | View details of a specific run |
| `gh run view <id> --log` | Show full logs of a run |
| `gh run view <id> --log-failed` | Show only failed step logs |
| `gh run watch <id>` | Watch a live workflow run |
| `gh run cancel <id>` | Cancel a running workflow |
| `gh run rerun <id>` | Re-run a workflow |
| `gh run rerun --failed <id>` | Re-run only failed jobs |
| `gh run download <id>` | Download run artifacts |
| `gh secret list` | List repo secrets |
| `gh secret set <name>` | Set a secret value |
| `gh secret delete <name>` | Delete a secret |
| `gh variable list` | List Actions variables |
| `gh variable set <name>` | Set an Actions variable |
| `gh variable delete <name>` | Delete an Actions variable |

---

## 26. GitHub CLI — Releases & Gists

| Command | Description |
|---------|-------------|
| `gh release create <tag>` | Create a new release |
| `gh release create <tag> --title "T"` | Create release with a title |
| `gh release create <tag> --notes "N"` | Create release with notes |
| `gh release create <tag> --draft` | Create a draft release |
| `gh release create <tag> --prerelease` | Mark release as pre-release |
| `gh release create <tag> file.zip` | Attach a file to the release |
| `gh release list` | List all releases |
| `gh release view <tag>` | View a specific release |
| `gh release view <tag> --web` | Open release in browser |
| `gh release edit <tag>` | Edit an existing release |
| `gh release delete <tag>` | Delete a release |
| `gh release download <tag>` | Download all release assets |
| `gh release download <tag> -A zip` | Download only ZIP asset |
| `gh release upload <tag> <file>` | Upload an asset to a release |
| `gh gist create <file>` | Create a Gist from a file |
| `gh gist create <file> --public` | Create a public Gist |
| `gh gist create <file> -d "desc"` | Create a Gist with description |
| `gh gist list` | List your Gists |
| `gh gist view <id>` | View a specific Gist |
| `gh gist view <id> --web` | Open Gist in browser |
| `gh gist edit <id>` | Edit a Gist |
| `gh gist delete <id>` | Delete a Gist |
| `gh gist clone <id>` | Clone a Gist locally |

---

## 27. GitHub CLI — SSH & GPG Keys

| Command | Description |
|---------|-------------|
| `gh ssh-key list` | List SSH keys on your GitHub account |
| `gh ssh-key add <file>` | Add an SSH key to GitHub |
| `gh ssh-key add <file> --title "T"` | Add SSH key with a title |
| `gh ssh-key delete <id>` | Delete an SSH key from GitHub |
| `gh gpg-key list` | List GPG keys on your account |
| `gh gpg-key add <file>` | Add a GPG key to GitHub |
| `gh gpg-key delete <id>` | Delete a GPG key from GitHub |

---

## 28. Advanced Git Internals

| Command | Description |
|---------|-------------|
| `git cat-file -t <hash>` | Show the type of an object |
| `git cat-file -p <hash>` | Print the content of an object |
| `git hash-object <file>` | Compute the hash of a file |
| `git ls-tree HEAD` | List tree structure at HEAD |
| `git ls-tree -r HEAD` | Recursively list all tree files |
| `git rev-parse HEAD` | Get the full SHA of HEAD |
| `git rev-parse --short HEAD` | Get the short SHA of HEAD |
| `git rev-parse --abbrev-ref HEAD` | Get the current branch name |
| `git rev-list --count HEAD` | Count total number of commits |
| `git rev-list HEAD` | List all commit hashes |
| `git symbolic-ref HEAD` | Show what HEAD points to |
| `git update-ref refs/heads/<b> <h>` | Manually move a branch pointer |
| `git pack-refs --all` | Pack all refs into a single file |
| `git var GIT_AUTHOR_IDENT` | Show current author identity |
| `git count-objects` | Count unpacked objects |
| `git rerere` | Reuse recorded resolution of conflicts |
| `git rerere status` | Show rerere-tracked conflicts |
| `git notes add -m "note" <hash>` | Add a note to a commit |
| `git notes show <hash>` | Show notes for a commit |
| `git notes remove <hash>` | Remove notes from a commit |
| `git replace <old> <new>` | Replace one object with another |
| `git filter-branch` | Rewrite history (use with caution) |
| `git filter-repo` | Modern rewrite tool (preferred) |

---

*Covers Git 2.x and GitHub CLI (gh) 2.x — Reference compiled for developers of all levels*
