# Debugging Commits
Big merge commits can be hard to debug, especially if they contain many changes.
This guide provides strategies to debugging when there are a lot of changes in a branch or merge commit.

## Strategy: Separate branch, shelve/unshelve similar to binary tree
Create a new branch from origin/main and have all the changes from the problem branch, uncommitted/unstaged.
```bash
git checkout origin/main -b ${debug_branch_name}                        # Create the debug branch
git merge --squash ${error_branch_name}           # Get all the changes from the error branch, stage but do not commit
# alternatively, specify a commit hash, it will get all the changes between the common ancestor and the commit
# git merge --squash <commit_hash>
```
Now you can use `git status` to see which files have changes.
Use the shelve/unshelve commands to test the changes in a binary tree-like fashion.
Example:
```bash
Problem: existing tests fail
Git status: 4 interfaces added, 10 new tests defined, 12 implementation classes changed.

Shelve all, unshelve the interfaces and new tests.
- Run the tests, no problems -> commit.

Unshelve the least dependent implementation classes (dao/repository/record).
- Run the tests, no problems -> ammend commit.

Keep unshelving until you detect a problem, then unshelve less and less until you detect your problem.
```
