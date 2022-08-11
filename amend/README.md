# Git kata: Amending commits
When we are working, we make a lot of commits.
Sometimes we just forget something obvious that we want to fix quickly.

`git commit --amend` allows us to do that - tinker with the last commit we made.

You can use `git log -p` or `git show` to inspect the contents of commits and file changes that were added to the commits.

## Setup:

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

1. What does `git status` tell us?
We are on master, bar.txt is not included in the commit.

2. What does `git log -p` tell us?
ubuntu@inst13:~/git-katas/amend/exercise$ git log -p
commit 060abf019b8143eb39c2e40af240643b8fac3fbc (HEAD -> master)
Author: Ubuntu <denix565@gmail.com>
Date:   Tue Aug 9 08:05:13 2022 +0000

    feature 73

diff --git a/foo.txt b/foo.txt
new file mode 100644
index 0000000..257cc56
--- /dev/null
+++ b/foo.txt
@@ -0,0 +1 @@
+foo

the commits done on the files

3. Stage the addition of bar.txt
git add bar.txt
4. Run `git commit --amend`
5. What happened? 
bar.txt was added to the commit
What does `git log -p` tell us?
tells us that bar was added to the commit


diff --git a/bar.txt b/bar.txt
new file mode 100644
index 0000000..5716ca5
--- /dev/null
+++ b/bar.txt
@@ -0,0 +1 @@
+bar
diff --git a/foo.txt b/foo.txt
new file mode 100644

6. What happens if you run `git commit --amend` again?
git commit --amend
[master aa688cb] feature 73
 Date: Tue Aug 9 08:05:13 2022 +0000
 2 files changed, 2 insertions(+)
 create mode 100644 bar.txt
 create mode 100644 foo.txt

 It amends the commit with the same files

## Useful commands

- `git add`
- `git log --oneline --graph`
- `git log -p`
- `git show`
- `git commit --amend`
