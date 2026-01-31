## GIT

Basics 

Distributed Version Control System

---

### Git Configuration

Set global username and email

Used in commits

``` 
git config --global user.name "Nothing" 
```
```
git config --global user.email "nothing@gmail.com"
```

**Check configuration**

```
git config --list
```
---


#### Git Initialization 

Initialize a Git repository
```
git init
```

Initialize with a specific branch name

```
git init --initial-branch=main
```

---

#### Git Status

Check the current state of the working directory

```
git status
```

Verbose output

```
git status -v
```

Short format

```
git status -s 
```

---

#### Git add 

Add files to Git tracking

Untracked / Modified --> Staged


Single File

```
git add <file>
```

Multiple Files

```
git add <file> <file> ...
```
All Files

```
git add .
```

---

#### Git Remove

Remove files from staging area

keep file locally

Staged -> Unstaged

```
git rm --cached <file>
```

---

#### Git commit 

Create a commit

```
git commit -m "message"
```

Commit only modified files

Skips untracked files

```
git commit -a -m "message"
```

Multiple commit messages title + description

```
git commit -m "title" -m "description"
```

Modify the latest commit message or content

```
git commit --amend -m "message"
```

Amend without changing commit message

```
git commit --amend --no-edit
```

Create an empty commit

```
git commit --allow-empty -m "message"
```

Add Signed-off-by line

```
git commit -s -m "message"
```

---

#### Git log

View commit history

```
git log
```

Limit number of commits

```
git log -n 5
```

Pretty formats

```
git log --pretty=short
```

```
git log --pretty=full
```

```
git log --pretty=fuller
```

```
git log --pretty=oneline
```

```
git log --oneline
```

Show file changes per commit

```
git log -p
```

Custom format

```
git log --pretty-format:"%h %s %an %ae"

```

Format keys

```
%h - hash_code_value
%s - message
%an - author_name
%ae - author_email
```

Filter logs by time

```
git log --since="yesterday"
```

```
git log --since="1 week ago"
```

```
git log --since="1 month ago"
```

```
git log --since="2025-12-25" --until="2026-01-01"
```

Filter by author

```
git log --author="Nothing"
```

Search commit messages

```
git log --grep="Modified"
```

---

#### Git Reset

Undo commits

Move HEAD to a previous commit

**Soft reset** keeps changes staged

```
git reset --soft hash-code
```

**Mixed reset** keeps changes unstaged

```
git reset --mixed hash-code
```

**Hard reset** discards all changes

```
git reset --hard hash-code
```

---

#### Git restore

Undo file changes 

Unstage a file

```
git restore --staged <file>
```

Discard local changes

```
git restore <file>
```

Restore from a specific commit

```
git restore --source=<commit-hash> <file>
```

---


### Git Branch

List branches

```
git branch
```

Create a new branch

```
git branch <branch-name>
```

Switch branch

```
git switch <branch-name>
```

Create and switch

```
git switch -c <branch-name>
```

Rename branch

```
git branch -m <new-name>
```

Delete branch

```
git branch -d <branch-name>
```

Force delete

```
git branch -D <branch-name>
```

### Git Merge

Merge another branch into current branch

```
git merge <branch-name>
```

Abort merge (if conflict happens):

```
git merge --abort
```

### Git Rebase

Reapply commits on top of another branch:

```
git rebase main
```

Abort rebase

```
git rebase --abort
```

Do not rebase shared branches.


### Git Stash

Temporarily save uncommitted changes:

```
git stash
```

Apply stash

```
git stash apply
```

Apply and remove stash

```
git stash pop
```

List stashes

```
git stash list
```

### Git Revert

Undo a commit safely 

Creates new commit

```
git revert <commit-hash>
```

### Git Reflog | Recovery

View all HEAD movements:

```
git reflog
```

### Recover lost commits

```
git checkout <hash>
```


### .gitignore

Ignore files from being tracked:

```
node_modules/
.env
dist/
*.log
.DS_Store
.vscode/
.idea/
```