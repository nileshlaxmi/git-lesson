# CheatSheet

```bash
# Cloning:
git clone repo-url

# Adding and commit a file
git add fileName
git commit -m "Adding file"
git pull origin master # in case your origin is already set up
git remote add origin git@github.com:nilesh/<reponame>.git # in case your origin is not set up
git push origin master
```

## Branching

```bash
# Listing branches:
git branch # listing local branch
git branch -a # listing local + remote branch
git branch -r # listing remote branch

# Creating new branch
git branch newBranchName # it will create local branch but it will not be check out
git checkout -b "newBranch" # it will create and check out to your new branch

# Deleting branches:
# Local
git branch -d branchName # -d flag is for delete
git branch -D branchName # -D flag is for delete forcefully
# Remote
git push origin --delete branchName

# Renaming branch
# Local branch when you are on same branch
git branch -m "new/BranchName"

# Rename the local branch to the new name when you are different branch
git branch -m <old_name> <new_name>

# -m : move

# Remote : You can't directly rename a remote branch. You have to delete it and then re-push it.
```

### Renaming a remote branch

***You can't directly rename a remote branch.*** You have to delete it and then re-push it.

#### Solution

```bash
# Rename the local branch to the new name
git branch -m <old_name> <new_name>

# Delete the old branch on remote - where <remote> is, for example, origin
git push <remote> --delete old_name

# Push the new branch to remote
git push <remote> new_name

# Reset the upstream branch for the new_name local branch
git push <remote> -u new-name # -u flag will create the upstream link

# Fetching from branch
git fetch origin branchName

# Pulling from branch
git pull origin branchName
```

**Difference between fetch and pull:**

Fetch will fetch the data from remote directory or branch while
Pull will fetch as well as merge the data with local data.

## Tagging

```bash
git tag -a 'Demo_1_0' -m 'Tagged Demo version' HEAD
git push origin tag Demo_1_0
git tag -l # view tags
git tag -a v1.2 9fceb02(specific commit) -m "Message here"
git tag v1.0 name_of_other_branch
git tag v1.0 <sha1> - Hash code of specific commit

# If you create a tag by e.g.
git tag v1.0
# the tag will refer to the most recent commit of the branch you are currently on. You can change branch and create a tag there.

# You can also just refer to the other branch while tagging,
git tag v1.0 name_of_other_branch
# which will create the tag to the most recent commit of the other branch.

# Or you can just put the tag anywhere, no matter which branch, by directly referencing to the SHA1 of some commit
git tag v1.0 <sha1>
```

## Rebase and Reflog

```bash
# Moving to specific commit
# 1st way:
git reset commitID

git reset HEAD@{2}
# will reset HEAD^^ i.e. HEAD-2

git log # will show history
git reflog # will show log of all activities
```

### **HEAD** will always represent the last commit on current branch

### Types of reset

1. Mixed: will reset staging, moves HEAD to specific id.

2. Hard: will reset local, working directory and staging area, moves HEAD to specific id.

3. Soft: will move HEAD to specific id.
