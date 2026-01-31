### Git Mistakes & Recovery

### [ 1 ] Committed to the Wrong Branch

You committed to main instead of feature-branch

```
git branch feature-branch
git reset --hard HEAD~1
git switch feature-branch
```

Commit is now on the correct branch

---

### [ 2 ] Forgot to Add a File to the Last Commit

```
git add <file>
git commit --amend
```

Updates the previous commit

---

### [ 3 ] Wrong Commit Message

```
git commit --amend -m "Correct message"
```

---

### [ 4 ] Accidentally Deleted Changes (Hard Reset)

Situation
```
git reset --hard
```

Recovery
```
git reflog
```

Find the old commit hash, then:
```
git reset --hard <hash>
```

Work recovered

### [ 5 ] Pulled and Got Merge Conflicts

```
git status
```

Open conflicted files --> fix manually --> then

```
git add .
git commit
```

OR 

Abort merge

```
git merge --abort
```

---


### [ 6 ] Want to Undo a Commit Already Pushed

Don't use reset

```
git revert <commit-hash>
```
Safe for shared branches

---

### [ 7 ] Staged Too Many Files

Unstage everything

```
git reset
```

Unstage specific file

```
git restore --staged <file>
```

### [ 8 ] Want to Save Work Without Committing

```
git stash
```

Restore later

```
git stash pop
```

### [ 9 ] Detached HEAD State

Situation

```
git checkout <commit-hash>
```

Fix

```
git switch -c new-branch
```


### [ 10 ] Merge Gone Wrong

Fix
```
git merge --abort
```
---

#### Golden Recovery Rule

If something goes wrong

```
git reflog
```