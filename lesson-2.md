# GIT Basic Overview

1. Starting a project:
    * Fresh project
    * Existing source locally
    * GitHub project (fork and clone)

* Fresh Project:

```Bash
git init fresh-project # it will create a new file and initialize with git folder

git add filename
# When files are not added, it means that files are not being tracked by git.

# By adding, file is being tracked and moved to staging area.
```

root-commit : It means that this is the first commit

* Existing source locally

```bash
mkdir dirname # it will create a dir
cd dirname

git init # it will create a .git repo with dirname as its current working directory

git add . # it will add all files, i.e. move it to staging area recursively

git commit -m "commit message" # it will commit all files to git repo
```

* GitHub project (fork and clone)
  * Fork : It is used to copy a repo from another Github account
  * Clone : It is used to clone a remote repo to local system

```bash
git clone remote-repo-url
```

**origin/master** : origin is remote folder while master is the default branch
