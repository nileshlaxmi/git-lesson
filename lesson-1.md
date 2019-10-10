# GIT Lesson

```Bash:  
Commands
git --version
git version
```

Git will require two things to start:

1. username
2. email

```Bash:  
Commands
git config --global.user "nileshlaxmi"
git config --global.email "nileshlaxmi4@gmail.com"

git config --global --list # It will list user and email

git clone "repo clone url" # It will clone the remote repo

ls # list all repo inside a folder

cd clone_repo # will go inside cloned-repo

git status # will tell on which branch you are and if there is anything to commit or not

touch filename # will create a file

echo "hello world" >> filename 
# hello world will be printed inside a new file if that file is not present.

cat filename # will display file content

git add . # will add all file

git add filename # will add single file of its name provided

git commit -m "commit message" # will commit with a message

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
