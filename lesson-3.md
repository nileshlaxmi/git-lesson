# GIT Basic Overview

ADD, COMMIT, PULL & PUSH

```Bash
# ADD
git add .
# It will move file from local to staging area and it will start tracking it also.

# COMMIT
git commit -m "Hello World"
# O/P : [master 0ba5fo]
# master is branch while 0ba5fo is SHA-1 hash code which is a unique identifier.
# commit will move files from staging to git repo.

# PULL
git pull  # or
git pull origin branchname
# It will pull the latest version of file from remote repo to local system
# origin : name of the remote repo from which we cloned our files

# PUSH
git push origin branchname
# It will pull the latest version of file from local system to remote repo
```

**BEST Practices** : Always pull your branch before pushing it.

## Tracked Files

```bash
git commit -am "Adding more text"

# -am: it will add and commit your files but only the tracked ones.  
```

***Tracked files*** are those files which are already added and committed to the git repo.

## Editing Files

```bash
git add filename
git commit -m "Add text"
```

## Recursively Adding Files

```bash
mkdir -p l1/l2/l3
# p flag will help to create folders

git add . # period helps add files recursively
```

***git status*** will not all show all level files, only the directories

## Backing Out Changes

To back out the changes from staging area

```bash
git add f1.txt
git reset HEAD f1.txt
```

You want to discard the changes you have done to your committed file (f1.txt)

```bash
git checkout -- f1.txt
```

## Renaming or Moving files

### Renaming using git

```bash
git mv file1 file2
# It will rename and move it to staging area

mv file1 file2
# git will see that there is two operations
# 1st: We have deleted file1
# 2nd: We have created file2 with same content as file1
# so we use
git add -A
# it will add all files reccursively as well as updates any files that have been renamed, moved or deleted
```

### Moving using git

```bash
git mv file1 dir1

mv file1 ./dir1

git add -u # it will tell that files has been renamed outside Git using Explorer
```

## Deleting Files

```bash
touch dump.txt

git rm dump.txt # git will tell that there is no such files as it is not being tracked

# If it is tracked file:
git rm dump.txt
# It is not permanent so we need to commit it as well

git commit -m "Deleted files"
```

### To recover deleted files

```bash
git rm a.txt

git reset HEAD a.txt
# It will just unstaged the deletion but file is not present in working directory

git checkout -- a.txt
# It will bring the back deleted files in working directory
```

### Deleting using bash

```bash
rm a.txt
git status
# it is in staging area

git add -A
git status
# a.txt has been deleted

rm -rf dirName # all files will be deleted recursively and forcefully
git status
git add -A # to removed from staging area
git commit -m "files deleted"
```

## History

```bash
git help log # will show all details about log
# Output format
# commitTag SHA-1
# Author ...
# Date ...
# Commit Message

git log --abbrev -commit
# it will reduce commitTag to 6-8 characters

git log --oneline --graph --decorate
# --oneline: compress the entry into oneline
# --graph: will provide ASCII graph and depicting the branching graph
# --decorate: will add any labels or tags or anything that sort of annotates our commit

git log commTag1...commTag5
# It will only show the commits which you have asked

git log --since="3 days ago"
# show commits for last 3 days ago

git log -- fileName
# show log of that fileName only

git log --follow --fileName
# show commit history of that specific file only

git show commit tag
# show commit history of that tag only
```

## Git Alias

Git allows us to create custom commans which can be used wuth git.

```bash
git log --all --oneline --graph --decorate
# we want to create a custom command for above command, we mention it in .gitconfig

git config --global alias.hist "log --all --oneline --graph --decorate"
# --global: show that it is available globally
# alias: it helps us to create aliases or custom commands
```

## Ignoring Unwanted Files or Folders

With the help of **.gitignore** file, we can exclude the files which we don't want to ignore

Git Ignore Pattern Examples - One file/dir per line

* Specific file: myfile.txt
* File pattern: *.log
* Folder/Dir: node_modules/

