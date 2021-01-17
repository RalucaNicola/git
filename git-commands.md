Commands I use on a daily basis:

## Basics

### Creation
- `git init` - initiate a repository
- `git clone <repo>` - clone a repository on your local machine

### Get info

- `git status` - list which files are staged, unstaged and untracked
- `git log` - shows the whole list of commits made
- `git log --graph --oneline --all --decorate` - shows a nice graph of the commits
- `git log -- <file>` - only show commits that have the specified file
- `git diff --cached` - shows difference between staging area and last commit
- `git diff` - shows difference between working directory and staging area
- `git diff HEAD` - show difference between working directory and last commit
- `git remote -v` - list all the remote repositories
- `git branch` - list all the branches on the local repository.
- `git branch -r` - list all the branches on the remote repository.
- `git branch --list 'hello*'` - list all the branches that start with hello

### Make changes to staging area/repository
- `git add <directory/file>` - stage all changes in \<directory/file> for the next commit
- `git rm <file>` - removes a file from the repository and the working directory
- `git rm --cached <file>` - removes a file from the repository, but it keeps it in the working directory
- `git commit -m "commit message"` - commit the staged snapshot with the set commit message

### Sync with the main repository
- `git fetch <remote> <branch>` - fetches a specific branch from the repo. I usually run `git fetch --all` to fetch all the branches on the `origin` remote.

- `git pull <remote>` - fetch the current branch of the remote and immediately merge it into the local copy.

- `git pull --rebase <remote>` - fetches the remote's copy of the current branch and rebases it into the local copy. Uses git rebase instead of merge to integrate the branches. When I need to work on master I usually run `git pull --rebase` to put all the changes that happened in the meantime before my changes.

- `git push <remote> <branch>` - push a local branch to the remote repository. For example: `git push origin master` to push your commits to the master branch. If the branch doesn't exist on the remote, it will create one.

- `git submodule update --init --recursive` - update the submodules

## Undoing changes and rewriting history

The only safe way to revert a commit that was already pushed to the main repo:
- `git revert <commit>` - create a new commit that undoes all of the changes made in <commit>, then applies it to the current branch

### Reset changes
- `git reset <file>` - unstages a file without overwriting any changes. It removes the file from the staging area, but keeps it in the working directory unchanged.

- `git reset` - reset staging area to match most recent commit, but leave the working directory unchanged

- `git reset --hard` - reset staging area and working directory to match last commit. This will **overwrite** all the changes in the working directory.

- `git checkout -- <file>` - undo changes you made to this file in the working directory. This brings back the file from the last commit. All the changes in the working repository are lost.

### Amending the last commit

(Only do this if you didn't push the commit to master)
- `git commit --amend` - replace the last commit  with the staged changes and last commit combined.
- `git commend --amend -m "new message"` - change the message of your last commit. Do this only when you haven't pushed the commit to the remote repository.

### Going back in history

You might want to do this to test which commit introduced a certain bug.

- `git checkout <commit>` - move the current branch tip to the commit given in the command. To get out of the detached HEAD state use `git checkout <branch>` if you know the branch you were on. Otherwise use `git checkout -`

### Cleaning up

- `git clean -n` - shows which files would be deleted
- `git clean -fd` - removed untracked files and directories (files that are not in the staging area, nor in the repo)

## Branches

### List branches

- `git branch` - list all the branches on the local repository.
- `git branch -r` - list all the branches on the remote repository.
- `git branch --list 'hello*'` - list all the branches that start with hello

### Create branches

- `git checkout -b <branch>` - create and checkout a local branch
- `git fetch` -> `git checkout <branch-name>` - create a local branch and set it to track a remote branch. If the remote isn't the origin: `git fetch <remote> <branch>` -> `git checkout -b <branch>`
- `git checkout <branch>` - checkout a branch

### Delete branches

- `git branch -d <branch>` - deletes a branch that has been already merged into master. To delete a branch that contains changes that haven't been merged use `git branch -D <branch>`

- `git branch -d $(git branch | grep 'hello*')` - delete all the branches that start with hello

### Merge branches

- `git checkout <branch1>` -> `git merge <branch2>`. This merges branch2 into branch1. In case you run into conflicts that you don't know how to resolve you can always escape it with `git merge --abort`.

- `git diff <branch1>..<branch2>` - get the differences between the two branches

- `git rebase master` - when working on a feature branch and you need to keep it up to date with the master branch, the best thing is to rebase. This will add all commits from master to your branch, before the branch commits.

- `git pull --rebase` - when multiple people work on a branch and you want to update it with the latest changes on the branch. This will pull the changes using the rebase strategy: all commits will go before your commits.

## Remotes

A repository can have multiple remotes.

- `git remote -v` - list all the remotes
- `git remote add <remote> <repository_url>` - add a remote to your local repository. For example: `git remote add origin2 https://github.com/etc`
- `git remote rm <remote>` - removes the remote repository. For example: `git remote rm origin2`
- `git remote set-url <repository_url>` - change the remote's url
- `git push <remote> <branch>` - push changes on the remote branch. For example: `git push origin master` -push the changes in the master branch up to the origin remote repository
