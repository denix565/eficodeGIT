# Git Kata: Basic Branching

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

You again live in your own branch, this time we will be doing a bit of juggling with branches, to show how lightweight branches are in git.
Hint: `git switch` will make you switch from one branch to another.

1. Use `git branch` to see the two branches that are relevant for this exercise
* master
  second-branch
2. What branch are you on?
* master
3. Use `git branch mybranch` to create a new branch called _mybranch_
4. Use `git branch` again to see the new branch created.
* master
  mybranch
  second-branch
5. Use `git switch mybranch` to switch to your new branch.
git switch mybranch
Switched to branch 'mybranch'

6. How does the output from `git status` change when you switch between the _master_ and the new branch that you have created?

ubuntu@inst13:~/git-katas/basic-branching/exercise$ git status
On branch mybranch
nothing to commit, working tree clean

7. How does the workspace change when you change between the two branches?
On branch mybranch
nothing to commit, working tree clean

8. Make sure you are on your _mybranch_ branch before you continue.
9. Create a file called `file1.txt` with your name.
10. `Add` the file and `commit` with this change.
11. Use `git log --oneline --graph` to see your branch pointing to the new commit.
ubuntu@inst13:~/git-katas/basic-branching/exercise$ git log --oneline --graph
* b17a974 (HEAD -> mybranch) changed a files name and made a new one
* 90562a0 (second-branch, master) dummy commit

12. Switch back to the branch called _master_.

git switch master
Switched to branch 'master'

13. Use `git log --oneline --graph` and notice how the commit you made on the _mybranch_ branch is missing on the _master_ branch.
git log --oneline --graph
* 90562a0 (HEAD -> master, second-branch) dummy commit

14. Make a new file called `file2.txt` and commit that file.

15. Use `git log --oneline --graph --all` to see your branch pointing to the new commit, and that the two branches now have different commits on them.
* b17a974 (mybranch) changed a files name and made a new one
* 90562a0 (HEAD -> master, second-branch) dummy commit

16. Switch to your branch _mybranch_.
17. What happened to your working directory? Can you see your `file2.txt`?
yes
but in blue color
18. Use `git diff mybranch master` to see the difference between the two branches.
diff --git a/file1.txt b/file1.txt
deleted file mode 100644
index ea517ab..0000000
--- a/file1.txt
+++ /dev/null
@@ -1 +0,0 @@
-fjf
\ No newline at end of file



## Useful commands

- `git switch`
- `git switch -c`
- `git log --oneline --graph`
- `git branch`
- `git diff`
