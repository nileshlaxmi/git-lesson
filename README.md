# git-lesson

Lessons for becoming expert on Git

## GIT Lesson

```Git:  
Commands
git --version
git version
```

Git will require two things to start:

1. username
2. email

```Git:  
Commands
git config --global.user "nileshlaxmi"
git config --global.email "nileshlaxmi4@gmail.com"

git config --global --list // It will list user and email

git clone "repo clone url" // It will clone the remote repo

ls // list all repo inside a folder

cd clone_repo // will go inside cloned-repo

git status // will tell on which branch you are and if there is anything to commit or not

touch filename // will create a file

echo "hello world" >> filename // hello world will be printed inside a new file if that file is not present.

cat filename // will display file content

git add . // will add all file

git add filename // will add single file of its name provided

git commit -m "commit message" // will commit with a message

git push origin master
or
git push
(in master: upstream link is already created by when we clone the repo.)

```

Git has 2 repos and 4 states:

1. Repos and its state:

    * Local:
        * Working Directory
        * Staging State (by using add we get to staging area)
        * Repository (git folder - by using commit we get to git repo)

    * Remote:
        * Remote State (by using push: we moved to remote repo)

## GIT Basic Overview

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

**root-commit** : It means that this is the first commit
