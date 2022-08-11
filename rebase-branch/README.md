# Git Kata: rebase branch

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

You again live in your own branch, this time we will be doing a bit of juggling with branches, to show how lightweight branches are in git.

1. Which branches exist?
git branch 
* master
  uppercase
2. Look at the log for the master branch
commit 30503f9647ece4e2b256b4227b822ebc8e9ec8e2 (HEAD -> master)
Author: Ubuntu <denix565@gmail.com>
Date:   Tue Aug 9 07:22:11 2022 +0000

    Add readme

commit c2d5a914f4a41d222c66a40db38606b778388bf5
Author: Ubuntu <denix565@gmail.com>
Date:   Tue Aug 9 07:22:11 2022 +0000

    Add content to greeting.txt

commit 9e861071a9b2ca2e60ad34601c746718687c41f9
:
3. Check out the uppercase branch
4. How does the log compare to the log on the master branch?
commit 86659a31271e492d84a29d08ad449a165629a55c (HEAD -> uppercase)
Author: Ubuntu <denix565@gmail.com>
Date:   Tue Aug 9 07:22:11 2022 +0000

    Change greeting to uppercase

commit c2d5a914f4a41d222c66a40db38606b778388bf5
Author: Ubuntu <denix565@gmail.com>
Date:   Tue Aug 9 07:22:11 2022 +0000

    Add content to greeting.txt

commit 9e861071a9b2ca2e60ad34601c746718687c41f9
:
The head topint to uppercase instead of to Master 

5. Rebase your uppercase branch with the master (`git rebase master`)
6. What did just happen? Draw it!
7. Now switch to the master branch
8. Merge uppercase into master
9. What does the log look like now?
commit 061f6d2fae034a361f96337ba8af51fc8f8c582b (HEAD -> master, uppercase)
Author: Ubuntu <denix565@gmail.com>
Date:   Tue Aug 9 07:22:11 2022 +0000

    Change greeting to uppercase

commit 30503f9647ece4e2b256b4227b822ebc8e9ec8e2
Author: Ubuntu <denix565@gmail.com>
Date:   Tue Aug 9 07:22:11 2022 +0000

    Add readme

commit c2d5a914f4a41d222c66a40db38606b778388bf5
:


## Useful commandsg

- `git checkout <branch-name>`
- `git rebase <branch-name>`
- `git log --oneline --graph --all`
- `git merge <branch-name>`
