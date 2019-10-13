# Branching

```bash
git branch
# list all branches local
git branch -a
# list all branches remote and local

# To create new branch:
# 1st way:
git branch newBranch
git checkout newBranch
# it will create new branch but will not be checked out.

# 2nd way:
git checkout -b newBranch1
# it will create new branch & will be checked out.

# Rename branch
git branch -m "branch1"

# Delete branch
git branch -d branch1 # will delete local branch which has not been pushed to remote repo

git branch -D branch1 # will delete remote + local branch 
```

## Merging

```bash
git merge branch1 # will merge branch1 to master

git diff master branch1 # difference b/w master & branch1
```

### Fast Forward Merge

It means that merging is done fast as there is no commit on target branch.

#### Disabling Fast Forward Merge

```bash
git merge branch1 --no-ff
```

### Automatic Merge

```bash
git merge branch1 -m "Merging changes"
# merging + committing
```

### Conflicting & Resolutions

We have to manually resolve the conflicts.

(master|Merging) : Merging means that we are in merging state.

### Cleaning & Pushing

```bash
git branch
git pull origin master
git push origin master
```
