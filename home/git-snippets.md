---
title: Git Snippets
description: Git snippets for frequent git-related issues
published: true
date: 2022-12-22T09:23:37.803Z
tags: 
editor: markdown
dateCreated: 2021-10-04T10:32:51.318Z
---

# Nomenclature

- `fork`: When forking, this is the resulting fork repository
- `upstream`: When forking, this is the original repository that was forked from
- `remote`: When you clone a repository, the repository you cloned from is called a `remote`. It's usually the `remote` called `origin`.

# Setup

Code in here will be git commands. If you don't have [git for windows](https://gitforwindows.org/) installed, you should do so.

To open a git terminal in a folder, you should be able to right-click and open a git bash. A terminal (black window) should open.

You should also have a merge tool installed, such as `kdiff3` or similar. It needs to support 3-way merges. To set a tool as mergetool, run 
```sh
git config --global merge.tool <tool>
```
For example, for kdiff3:
```sh
git config --global merge.tool kdiff3
```

# Common Issues

## Reset a fork to the state of upstream

Problem: You made a fork but it's not up-to-date with the upstream, and it has changes that you'd like to **get rid of**. Basically, you want to **reset** your fork's status to the one of the upstream repository.

Assuming
- `https://github.com/example/example` is the upstream repo
- `https://github.com/me/example` is your fork
- `<branch>` is the branch you want to reset

We're also assuming that your fork's repo is already set up as `origin` (this is usually the case).

1. Add the upstream repository:
```sh
git remote add upstream https://github.com/example/example
```

2. Pull from upstream and reset:
```sh
git pull -f upstream <branch>
git reset --hard upstream/<branch>
```
**This will NUKE your local changes on that branch.**

3. Push to origin:
```sh
git push --force-with-lease origin <branch>
```

## Push: Not possible to fast-forward

Problem: You made a change to `a.txt` on `main`, but the remote also changed `a.txt` on `master`, and you can't push your commit because it fails with `fatal: Not possible to fast-forward, aborting.`.

In our example, we add `cruel` but origin adds `beautiful` to our `a.txt`.

To fix:

1.  `git rebase origin main` - Replace `main` with the branch you're working on. This will set our "base" (the starting point for our work) to the latest version of origin's main branch. That way our change to `a.txt` will appear to be *after* the change to `a.txt` from origin's main branch. 
2. You will likely see something like this: 
```sh
Auto-merging a.txt
CONFLICT (content): Merge conflict in a.txt
error: could not apply 751b0ad... Added "cruel" to a.txt
Resolve all conflicts manually, mark them as resolved with
"git add/rm <conflicted_files>", then run "git rebase --continue".
You can instead skip this commit: run "git rebase --skip".
To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply 751b0ad... Added "cruel" to a.txt
```
3. As it says `Resolve all conflicts manually`, we need to resolve them by running `git mergetool`. This should open the merge tool of your choice. How to use your merge tool will not be expanded on here. Resolve all conflicts now. In our example we make it so that the file has both `cruel` and `beautiful`. Once all conflicts are resolved, close your merge tool.
4. `git rebase --continue` - If your editor opens after this, just save and close it. If you get the error from 2., go to step 3. and repeat. Do this until you don't get it anymore. This will go through all commits and rebase them onto the newer branch, one-by-one.
5. Eventually you should see `Successfully rebased and updated refs/heads/main`.
6. You can now push your changes - but it won't let you `push` just like that (thanks, git). Instead, you want to **make sure you have successfully rebased and your history is "ahead" of the remote**. Then `git push --force-with-lease origin main`. **Never force-push to an official branch** (like BeamMP's `development` or BeamMP-Server's `master`), **ever**. Always use a feature-branch and PR it into the branch you want.
