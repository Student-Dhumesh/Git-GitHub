### GITHUB
Basics

Remote repository service provider.

---

#### Connecting a Local Repository with a Remote Repository

```
Local Repository                    Remote Repositroy
project-x                           project-x
URL: file:///C:/Projects/project-x  URL: https://gihub.com/user-name/repo-name.git


```
#### Command

```
git remote add origin https://github.com/user-name/repo-name.git

```

**Here**

**git remote add** → command to add remote

**origin** → alias of URL

```pgsql
origin = https://github.com/user-name/repo-name.git
```

#### Check remote repository

```
git remote
```
> origin 

```
git remote -v
```
> origin https://github.com/user-name/repo-name.git (fetch)

> origin https://github.com/user-name/repo-name.git (push)

---

#### Create a branch on remote repository

```
git push -u origin main 
```

```
git push --set-upstream origin test
```

**Here**

```
-u == --set-upstream
```

---

### Practice

#### Clone Remote Repository to Local

You have a remote repository 

You want to download project in local repository

```
Remote repository   ---->   Local Repository
```

#### Command

```
git clone https://github.com/user-name/repo-name.git
```

```
cd repo-name
```

Check remote
```
git remote
```

```
git remote -v 
```

Push changes

```
git push
```

It will ask for authentication the first time

Creating and Pushing a Separate Branch 

```
git branch test
```

```
git switch test
```

Push changes 

If the branch does not exist on remote

```
git push -u origin test
```

If the branch already exists on remote

```
git push 
```


---


### Practice

#### Upload Existing Local Repository to Remote

You have a existing git repository

You want to upload it on remote repository


Inside your project folder
```
cd repo-name
```

Initialize git

```
git init
```
You can also set the initial branch name

```
git init --initial-branch=main
```
If you already initialized with master, rename it

```
git branch -M main
```
Add remote reposiotry 

```
git remote add origin https://github.com/user-name/repo-name.git

```

Add README.md file

```
touch README.md 

git add README.md

git commit -m "README.md added"
```

```
git push -u origin main
```

Future commits 

```
git push
```

If you want to create a seprate branch 

```
git branch test
```

```
git switch test
```

Push changes 

If branch does not exist
```
git push -u origin test
```

If branch exists
```
git push
```


### Branch Management

#### Create a new branch

```
git branch feature-branch
```

```
git switch feature-branch
```

### Push branch to remote

If branch does not exist
```
git push -u origin feature-branch
```

If branch exists
```
git push
```

#### Delete branch

Local branch

```
git branch -d feature-branch
```

Remote branch

```
git push origin --delete feature-branch
```

---


### Fetching and Pulling Changes

Fetch Changes (does not merge)
```
git fetch origin
```

Pull Changes (fetch + merge)
```
git pull origin main
```

Merging Branches
```
git switch main
git merge feature-branch
```

Resolve conflicts if any, then:

```
git add .
git commit -m "Merge feature-branch into main"
```

**Important**

### Local vs Remote Branches in Git

When you connect a local repository to a remote repository

Git maintains separate branches for local and remote

Example 

```
Local branches:

- main
- test
- feature-branch

Remote branches (remote-tracking branches):

- origin/main
- origin/test
- origin/feature-branch
```

Note: origin is the default alias for the remote repository


### How git sync works


Fetch

```
git fetch
```
Downloads updates from the remote repository

Updates remote-tracking branches (e.g., origin/main) but does not change your local branches


Merge

```
git merge origin/main
```

Merges changes from the remote-tracking branch (origin/main) into your local branch (main)

Pull

```
git pull
```

Equivalent to

```
git fetch
git merge
```

Updates your remote-tracking branches and merges them into the corresponding local branch in one step

---

#### GIT FETCH and GIT MERGE

```
Local main:        A --- B
Remote origin/main: A --- B --- C --- D
```

```
git fetch
```
Updates origin/main

```
Local main:        A --- B
Remote origin/main: A --- B --- C --- D
```

```
git merge origin/main
```
Merges remote changes into local main

```
Local main:        A --- B --- C --- D
Remote origin/main: A --- B --- C --- D
```


#### GIT PULL

```
Local main:        A --- B
Remote origin/main: A --- B --- C --- D
```

```
git pull
```
git pull → does fetch + merge automatically


```
Local main:        A --- B --- C --- D
Remote origin/main: A --- B --- C --- D
```

<!-- Ends Here -->