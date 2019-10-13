# Stashing

It helps us to save the changes and after that we can work on new features.

By default, git stash save changes of tracked files only.

```bash
git stash

git stash apply # it will bring the saved changes
git stash drop # it will drop the stash

git stash list # will list all stash
# O/P: stash@{0}: WIP on master: saved changes

git stash -u
# will stash un tracked files also

git stash pop # alternative of stash apply and drop
```

## Managing multiple stash

```bash
git stash save "changes 1.0"
git stash save "changes 1.1"
git stash save "changes 1.2"
# it will help us in differentiating b/w multiple stashes with the help of messages

git stash list
# O/P: Latest commit on top
# stash@{0}: changes 1.2
# stash@{1}: changes 1.1
# stash@{2}: changes 1.0

git stash show stash@{1}
# it will show the middle stash

git stash apply stash@{1}
git stash drop stash@{1}
# stash@{1} will be applied and drop, now again listing stash middle one is dropped

git stash list
# stash@{0}: changes 1.2
# stash@{1}: changes 1.0

# Here pop will not work as pop will apply the last one not the middle one

git stash clear # will cleared all stash
```

## Stashing into a Branch

```bash
git stash branch stashBranchName
# a new branch will be created, all the stash will be applied and the stash will be dropped.
```
