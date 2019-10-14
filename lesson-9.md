# Rebase and Reflog

HEAD will always represent the last commit on current branch

```bash
git reset HEAD^1 # i.e. last commit-1

git reset HEAD^

git log # will show history
git reflog # will show log of all activities
```

## Moving to specific commit

```bash
# 1st way:
git reset commitID

git reset HEAD@{2}
# will reset HEAD^^ i.e. HEAD-2
```

## Types of reset

1. Mixed: will reset staging, moves HEAD to specific id

2. Hard: will reset local, working directory and staging area, moves HEAD to specific id

3. Soft: will move HEAD to specific id

## Cherry-pick

It help to merge a specific tag to any branch

```bash
git cherry-pick commitID
```
