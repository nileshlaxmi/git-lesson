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
