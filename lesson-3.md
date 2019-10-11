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
