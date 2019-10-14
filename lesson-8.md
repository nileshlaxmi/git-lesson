# Tagging

When we want to back up a milestone, then we create a tag.

```bash
git tag myTag # to create a new tag

git tag --list # list all tags

git tag --delete myTag # to delete a tag
````

## Annotated tag

Tag with more information i.e. it contain tag message.

```bash
git tag -a v1.0 "version 1.0"

git show v1.0
# it will show commit message, with author and its origin time.
```

## Comparing Tags

```bash
git commit --amend "Amending exiting commit message"

# difference format:
git diff startingRef endingRef
# e.g.:
git diff v1.0 v2.0

# Tagging a specific commit
git tag -a v0.9-beta commitID "beta version" # new commit tag
```

## Updating Tags

1. Delete the existing tag and create a new one.

2. Doing it forcefully

```bash
#2nd way:
git tag -a v0.9-beta -f commitID "beta version"
```

## Pushing tag

```bash
git push origin myTag # specific tag

git push origin master --tags # all tags

# Don't want to publicize a specific tag
git push origin :v1.2
# v1.2 will be deleted from remote repo but will be presented on local repo
```
