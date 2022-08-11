# Git Kata: 3-Way Merge

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

You again live in your own branch, this time we will be doing a bit of juggling with branches, to show how lightweight branches are in git.

1. Create a branch called greeting and check it out
2. Edit the greeting.txt to contain your favorite greeting
3. Add greeting.txt files to the staging area
4. Commit
5. Switch back to the master branch
6. Create a file README.md with information about this repository
7. Add the README.md file to staging area and make the commit
8. What is the output of `git log --oneline --graph --all`?
9. Diff the branches
10. Merge the greeting branch into master
11. What is the output of `git log --oneline --graph --all` now? Observe the extra merge commit created with the message "Merge branch 'greeting'".

greeting.txt
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ echo HELLOOOOOO > greeting.txt 
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ cat greeting.txt 
HELLOOOOOO
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git add .
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ ls
greeting.txt
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git commit
[greeting 45aea2c] added my favorite greeting :D
 1 file changed, 1 insertion(+), 1 deletion(-)
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git switch master
Switched to branch 'master'
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git branch
  greeting
* master
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ ls
greeting.txt
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git remote show origin
fatal: 'origin' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git remote -v
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git remote
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git info
git: 'info' is not a git command. See 'git --help'.

The most similar commands are
        init
        mailinfo
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ ls
greeting.txt
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ echo This project is about training > README.md
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ cat README.md 
This project is about training
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git add .
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git commit
[master 9e78570] added a description of Readme
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git log --online --graph --all
fatal: unrecognized argument: --online
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ git log --oneline --graph --all
* 9e78570 (HEAD -> master) added a description of Readme
| * 45aea2c (greeting) added my favorite greeting :D
|/  
* fe8e78a Add content to greeting.txt
* b747bdb Add file greeting.txt
ubuntu@inst13:~/git-katas/3-way-merge/exercise$ 
## Useful commands

- `git branch`
- `git branch <branch-name>`
- `git branch -d <branch-name>`
- `git switch <branch-name>`
- `git switch -c <branch-name>`
- `git branch -v`
- `git add`
- `git commit`
- `git commit -m`
- `git merge <branchA> <branchB>`
- `git diff <branchA> <branchB>`
- `git log --oneline --graph --all`
