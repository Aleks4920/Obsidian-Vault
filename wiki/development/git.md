---
tags: [development, git, version-control]
notion_source: "https://www.notion.so/2acfe6aa14b9806db9a4cae2e9647b9d"
last_synced: "2026-04-12"
---

# Git

Distributed Code Version Control System. See also [[devsecops]] and [[orbital-hardware-request-form]].

## Configuration

```bash
# set config personal identifiers
git config --global user.email "bob@example.com"
git config --global user.name "Bob Dylan"
# remove --global to use locally (e.g. for work)

# view set identifiers
git config --global --get user.email
```

## Git History

```bash
git log

# revert to previous commit
git checkout <commit hash>
# commit hash seen in git log

# return to latest
git checkout main
# if you made changes but want to forget them:
git checkout -f main

# rename master branch to main
git branch -M main
```

## Branches

```bash
# create new branch
git branch <branch name>

# pick source to start from
git branch <branch name> <source branch>

# switch to branch
git checkout <branch name>

# create and move to branch in one go
git checkout -b <branch name>

# publish local branch
git push --set-upstream origin <branch name>
# or
git push -u origin <branch name>
```

## GitHub

A cloud platform to store Git repos and collaborate.

**Origin** = Alias for remote repo URL (e.g. `https://github.com/Aleks4920/DevOps-Zero-to-Hero.git`)

```bash
# link repo to Github
git remote add origin https://github.com/Aleks4920/DevOps-Zero-to-Hero.git
# can have multiple remotes with different names

# push to github
git push -u origin main
```
