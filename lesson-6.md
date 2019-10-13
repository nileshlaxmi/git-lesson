# Rebasing

Rebase is done when we want to add updated commits from master to our feature branch

```bash
git rebase master
# we are on our feature branch
# it will help us in fast forwarding merge and there will be no conflicts

git rebase abort
# aborting a rebase

git rebase master
# O/P: (feature|Rebase 1/1): if there is conflict then we resolve it manually
# After resolving conflicts
git rebase --continue

git fetch origin master
# fetch: it will simply update the local and remote reference.

git pull --rebase origin master
# it will bring the changes done on remote master to your branch
```
