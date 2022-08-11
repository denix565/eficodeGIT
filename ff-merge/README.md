# Git Kata: Fast-forward Merge

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

You again live in your own branch, this time we will be doing a bit of juggling with branches, to show how lightweight branches are in git.

1. Create a (feature)branch called `feature/uppercase` (yes, `feature/uppercase` is a perfectly legal branch name, and a common convention).
2. Switch to this branch
3. What is the output of `git status`?
 git switch feature/uppercase
Switched to branch 'feature/uppercase'
4. Edit the greeting.txt to contain an uppercase greeting
ubuntu@inst13:~/git-katas/ff-merge/exercise$ echo GREETING > greeting.txt 
ubuntu@inst13:~/git-katas/ff-merge/exercise$ cat greeting.txt 
GREETING
5. Add `greeting.txt` files to staging area and commit
6. What is the output of `git branch`?
7. What is the output of `git log --oneline --graph --all`

ubuntu@inst13:~/git-katas/ff-merge/exercise$ git log --oneline --graph --all
* 734727c (HEAD -> feature/uppercase) changed the name to uppercase
* e7f8f90 (switch, master) Add content to greeting.txt
* 16cc0d1 Add file greeting.txt

   *Remember: you want to pull in the commit on the feature branch into master. The command 'git merge [branch name]' takes one branch as argument from which it takes commits. The commits are applied to the branch pointed to by HEAD (currently checked out branch).*

8. Switch to the `master` branch
9. Use `cat` to see the contents of the greetings
10. Diff the branches
 git diff master feature/uppercase
diff --git a/greeting.txt b/greeting.txt
index ce01362..1e4307a 100644
--- a/greeting.txt
+++ b/greeting.txt
@@ -1 +1 @@
-hello
+GREETING
ubuntu@inst13:~/git-k

11. Merge the branches
git merge feature/uppercase master
Updating e7f8f90..734727c
Fast-forward
 greeting.txt | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
12. Use `cat` to see the contents of the greetings
e$ cat greeting.txt 
GREETING
ubuntu@inst13:~/git-katas/ff-merge/exercise$ 

13. Delete the uppercase branch
git branch -d feature/uppercase
Deleted branch feature/uppercase (was 734727c).

## Useful commands

- `git branch`
- `git branch <branch-name>`
- `git branch -d <branch-name>`
- `git switch`
- `git branch -v`
- `git add`
- `git commit`
- `git commit -m`
- `git merge <branch>`
- `git diff <branchA> <branchB>`
- `git log --oneline --graph --all`
