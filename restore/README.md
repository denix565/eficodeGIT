# Git kata: Restoring files

We all make mistakes. Sometimes we make changes we'd rather not have made, or accidentally stage changes we didn't intend to stage.
This is where `git restore` comes into play.

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

1. Call `git status`\
 What changes were made to this repository?

ubuntu@inst13:~/git-katas/restore/exercise$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   bar.txt

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    foo.txt

2. Restore the `foo.txt` file using `git restore foo.txt`
3. Call `git status` again\
 What happened to `foo.txt`?
 Foo got restored and it displys as a file

4. Unstage the changes to `bar.txt` using `git restore --staged bar.txt`
5. Call `git status` once more\
 What happened to `bar.txt`?
 Now bar.txt appears as not commited on the branch
6. Restore the `bar.txt` file using `git restore bar.txt`
7. Call `git status` once more\
 What happened to `bar.txt`?
8. Call `git log --oneline`\
 Do you spot the tag?
 git restore bar.txt
ubuntu@inst13:~/git-katas/restore/exercise$ git log --oneline
c393672 (HEAD -> master) Update foo.txt
d87db84 Add bar.txt
e0e32ab (tag: v1.0.0) Add foo.txt

9. Restore `foo.txt`'s contents to their previous version using `git restore -s v1.0.0 foo.txt`
10. Call `git status` one last time\
 What happened to `foo.txt`?
 the original message/file content was restored

## Useful commands

- `git status`
- `git log --oneline`
- `git restore`
- `git restore --staged`
