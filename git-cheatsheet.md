# CheatSheet

## GIT Basics

```bash
git init <directory>
# Create empty Git repo in specified directory. Run with no arguments to initialize the current directory as a git repository.

git clone <repo>
# Clone repo located at <repo> onto local machine. Original repo can be located on the local filesystem or on a remote machine via HTTP or SSH.

git config user.name <name>
# Define author name to be used for all commits in current repo. Devs commonly use --global flag to set config options for current user.

git add <directory>
# Stage all changes in <directory> for the next commit. Replace <directory> with a <file> to change a specific file.

git commit -m "<message>"
# Commit the staged snapshot, but instead of launching a text editor, use <message> as the commit message.

git status
# List which files are staged, unstaged, and untracked.

git log
# Display the entire commit history using the default format. For customization see additional options.

git diff
# Show unstaged changes between your index and working directory.
```

## GIT Config

```bash
git config --global user.name <name>
# Define the author name to be used for all commits by the current user.

git config --global user.email <email>
# Define the author email to be used for all commits by the current user.

git config --global alias. <alias-name> <git-command>
# Create shortcut for a Git command. E.g. alias.glog log --graph --oneline will set git glog equivalent to git log --graph --oneline.

git config --system core.editor <editor>
# Set text editor used by commands for all users on the machine. <editor> arg should be the command that launches the desired editor (e.g., vi).

git config --global --edit
# Open the global configuration file in a text editor for manual editing.
```

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
