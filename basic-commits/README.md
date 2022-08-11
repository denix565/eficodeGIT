# Git Kata: Basic Commits
This kata will introduce you to the `git add` and `git commit` commands.

This is a very introductory kata. if you have used `git status`, `git log --oneline --graph`, `git add` and `git commit` extensively you should probably skip it.

You can look at the bottom of this file, if you have not yet done basic git configuration.

## Setup:

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

1. Use `git status` to see which branch you are on.

"On branch master

No commits yet
"
2. What does `git log` look like?

"fatal: your current branch 'master' does not have any commits yet"

3. Create a file
4. What does the output from `git status` look like now?
"On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test.txt

nothing added to commit but untracked files present (use "git add" to track)"

5. `add` the file to the staging area

git add text.txt

"On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   test.txt
"

6. How does `git status` look now?

"On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   test.txt
"

7. `commit` the file to the repository

"ubuntu@inst13:~/git-katas/basic-commits/exercise$ git commit
[master (root-commit) 8848dcc] adding my first file called test.txt
 1 file changed, 1 insertion(+)
 create mode 100644 test.txt
ubuntu@inst13:~/git-katas/basic-commits/exercise$ "

8. How does `git status` look now?
ubuntu@inst13:~/git-katas/basic-commits/exercise$ git status
On branch master
nothing to commit, working tree clean
ubuntu@inst13:~/git-katas/basic-commits/exercise$ 

9. Change the content of the file you created earlier
10. What does `git status` look like now?
ubuntu@inst13:~/git-katas/basic-commits/exercise$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test.txt

no changes added to commit (use "git add" and/or "git commit -a")


11. `add` the file change
git add .

12. What does `git status` look like now?
ubuntu@inst13:~/git-katas/basic-commits/exercise$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   test.txt



13. Change the file again

ubuntu@inst13:~/git-katas/basic-commits/exercise$ mv test.txt newName.txt
ubuntu@inst13:~/git-katas/basic-commits/exercise$ ls
newName.txt

14. Make a `commit`
ubuntu@inst13:~/git-katas/basic-commits/exercise$ git commit
[master 0532576] renamed the file from test.txt to newName.txt
 1 file changed, 4 insertions(+)

15. What does the `status` look like now? The `log`?
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    test.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        newName.txt

no changes added to commit (use "git add" and/or "git commit -a")

16. Add and commit the newest change

## Useful commands
- `git add`
- `git commit`
- `git commit -m "My commit message"`
- `git log`
- `git log -n 5`
- `git log --oneline`
- `git log --oneline --graph`
- `touch filename` to create a file (or `sc filename ''` in PowerShell)
- `echo content > file` to overwrite file with content (or `sc filename 'content'` in PowerShell)
- `echo content >> file` to append file with content (or `ac filename 'content'` in PowerShell)


## Git Initial Configuration
1. `git config --global user.name "John Doe"`
1. `git config --global user.email "johndoe@example.com`

For the vim scared:
- `git config --global core.editor nano`

For the windows peeps:
- `git config --global core.editor notepad`

Other editor options:
- `git config --global core.editor "atom --wait"`
- `git config --global core.editor "code --wait"`
- `git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst"`
