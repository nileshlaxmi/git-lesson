# GIT Comparisons

## Comparing Working Dir & Staging Area

```bash
git diff
```

## Comparing Working Dir & to the last known commit

```bash
git diff HEAD
```

## Comparing b/w Staging Area & last known commit

```bash
git diff --staged HEAD
# staged: staging area
# HEAD: last commit on current branch
```

## Limiting Comparisons to one File (or path)

```bash
git diff
# It will show all the difference of multiple files b/w staged one and working directory

git diff -- README.md
# for specific file
```

## Comparing b/w commits

```bash
git log --oneline # show commit tags and its message

git diff commTag1 commTag2
# alternatively
git diff HEAD HEAD^
# HEAD - last commit
# HEAD^ - last commit-1
```

## Comparing b/w local branches and remote branches

```bash
git diff master origin/master
```
