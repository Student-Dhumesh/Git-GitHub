## Git

### Git configuration 

```
git config --global user.name "Nothing"
git config --global user.email "nothing@gmail.com"

git config --global user.name
git config --global user.email
```

### basic commands
```
git init

git status

git add file.txt

git commit -m "message"

git log

```

### more about git init

```
git init
rm -rf .git 

git init --initial-branch=main

```

### more about git status

```
git status 
git status -v
git status -s

```

### more about git add

```
non-staging area 
    |
    +----------- git add -------+
                                |
                            staging area
                         (aware about file)
                            not tracking
``` 

```
to stage files

git add file.txt
git add file1.txt file2.txt file3.txt 
git add .

to unstage files

git rm --cached file.txt
git rm --cached file1.txt file2.txt file3.txt
git rm --cached .

```

### more about git commit


```
to commit files

git commit -m "message"

```

```
commit used to track files

commit contains information
    |
    +--- Who (user.name, user.email)
    |
    +--- When (Time)
    |
    +--- Message (at the commit time)
    |
    +--- Snapshot of files in staging area

snapshot techinque = SHA1 (Secure Hashing Algorithm)
SHA1 = having 40 alpha-numeric number 

branch is always created after first commit


C1 = initial commit

C2 = C1 + Extra files and modifications

C3 = C2 + Extra files and modifications

ans so on

commit stores in = .git/objects folder
```

### more about git log

```

to see logs

git log

git log shows information

commit 40_character_hash_value (HEAD -> branch)
Author: user.name <user.email> (who)
Date: (when)

    "commit message"
```

### about head

```
HEAD = Head is a pointer that points to latest commit
```