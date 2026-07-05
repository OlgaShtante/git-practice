# 🌿 Git Command Cheat Sheet

A personal, no-nonsense reference for everyday Git — plus a few plumbing commands most people never learn.
📖 Deep dive: [Pro Git book](https://git-scm.com/book/en/v2)

---

## 🧭 Navigation

| Command | What it does |
|---|---|
| `cd /disk/folder/folder` | Move into the target directory |
| `pwd` | Print the current working directory |

## 🌐 Remotes

| Command | What it does |
|---|---|
| `git clone <url>` | Clone a repository (SSH or HTTPS) |
| `git remote -v` | Show remotes with their URLs (`--verbose`) |
| `git remote add <name> <url>` | Add a remote |
| `git remote remove <name>` | Remove a remote |

## 📦 Staging & committing

| Command | What it does |
|---|---|
| `git status` | Show what's staged / unstaged before committing |
| `git add <file>` | Stage a file |
| `git commit -m "message"` | Commit staged changes with a message |
| `git commit --amend -m "New message"` | Rewrite the last commit message → then `git push -f origin <branch>` |
| `git cherry-pick <hash>` | Apply a commit from another branch onto the current one |

## 🔍 Inspecting history & internals

| Command | What it does |
|---|---|
| `git log` | Show commit history |
| `git show` | Show the last commit |
| `git push` | Sync local → remote |
| `git pull` | `git fetch` + `git merge` — pull remote changes |
| `git show -s --pretty=raw <hash>` | Show the tree and blob(s) of a commit (5+ chars of hash) |
| `git ls-tree <tree-hash>` | Show the contents of a tree |
| `git show <blob-hash>` | Show the content of a blob |

## ↩️ Undoing changes

| Command | What it does |
|---|---|
| `git checkout -- <file>` | Discard working-directory changes to a file |
| `git checkout .` | Discard **all** tracked changes ⚠️ (won't touch new files) |
| `git clean -xdf` | Remove new/untracked files and directories ⚠️ |
| `git reset -- <file>` | Unstage a file (Staged → Unstaged) |
| `git reset HEAD~1` (`HEAD^`) | Undo the last commit; `HEAD~2` for the last two |
| `git reset --soft HEAD~1` | Undo the last commit, **keep** changes staged |
| `git reset --hard HEAD~1` | Undo the last commit, **lose** the changes ⚠️ gone forever |
| `git reset --hard <hash>` | Roll back to a specific commit ⚠️ |
| `git revert <hash>` | Safely undo an **already-pushed** commit with a new commit |

## 🌿 Branches & merging

| Command | What it does |
|---|---|
| `git checkout -b <branch>` | Create a branch and switch to it |
| `git checkout master` | Switch back to master |
| `git branch --all` | List all branches |
| `git merge <branch>` | Merge a branch into the current one |
| `git merge --abort` | Undo an in-progress merge |
| `git checkout --theirs / --ours` | On conflict, pick their side or your side |

## 🏷️ Tags

| Command | What it does |
|---|---|
| `git tag <name>` | Tag the last commit |
| `git tag --list` | List your tags |
| `git push --tags` | Push tags to the remote |

## 📥 Stash

| Command | What it does |
|---|---|
| `git stash save "description"` | Save local changes + working state for later |
| `git stash list` | Show stashes |
| `git stash apply stash@{0}` | Re-apply a stash |

## 🖥️ GUI & helper tools

| Command | What it does |
|---|---|
| `git gui` | Open Git's portable graphical interface |
| `git gui&` | Same, but keep the terminal free |
| `gitk` | Open the Git repository browser |
| `gitk&` | Same, but keep the terminal free |
| `git --help` | Guess what 🙂 |

## ⌨️ Git Bash hotkeys

| Keys | Action |
|---|---|
| `Shift + Insert` | Paste into Git Bash from the clipboard |
| `Ctrl + Insert` | Copy from Git Bash to the clipboard |

## ✏️ Vi (visual editor) hotkeys

| Keys | Action |
|---|---|
| `Insert` | Enter editing mode |
| `Esc` | Leave editing mode |
| `:wq` | Write (save) and quit |
| `:q!` | Quit without saving |

---

<sub>⚠️ = destructive / irreversible — double-check before you run it.</sub>
