This is a repository to practice git concepts

## Important concepts


**The different environments**

staging area/working directory/repository -> edit/stage/commit. Read about it [here](https://www.atlassian.com/git/tutorials/saving-changes).

![image git local remote](https://greenido.files.wordpress.com/2013/07/git-local-remote.png)

---

**Deal with merge conflicts** (learn together)

[Article to read about it](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts).

---
**Merge vs rebase**

When working on a branch, you'll need to regularly merge master in your branch to keep it up to date. There are two approaches to this: merging will create a new commit that merges the two branches together, while rebase will add all commits from master to your branch before the branch commits. Rebase creates a clean, linear history.

[Article about this](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)

---
**How to collaborate in a team** (learn together)


 - [Gitflow workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) - develop features in branch and merge to main branch using a PR. Typical for internal projects at companies.

 - [Forking workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow) - fork a repo, develop feature in your own copy of the repo, open PR and merge to the initial repo. Typical for public open source projects because the maintainer can accept commits without giving the developer access to the official codebase.

---
 **Stashing**

 Sometimes you work on something and you need to change branch to check something else, but you're not ready to commit your changes. Stashing comes in handy here. Reading about [stashing here](https://www.atlassian.com/git/tutorials/saving-changes/git-stash).

 ---

## Cool resources

 http://git-school.github.io/visualizing-git/
 https://learngitbranching.js.org/