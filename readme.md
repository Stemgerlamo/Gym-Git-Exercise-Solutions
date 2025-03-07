# Git Exercises

## Bundle 1

### Exercise1


``` bash 
PS C:\Users\acer\git-Exercise> git checkout -B dev
M       readme.md
Switched to a new branch 'dev'
PS C:\Users\acer\git-Exercise> git checkout -B test
M       readme.md
Switched to a new branch 'test'
PS C:\Users\acer\git-Exercise> git status
On branch test
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   readme.md

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\acer\git-Exercise> git add .    
PS C:\Users\acer\git-Exercise> git commit -m 'adding dev test branch'
[test 15ee685] adding dev test branch
 1 file changed, 46 insertions(+)
 PS C:\Users\acer\git-Exercise> git push -u origin dev 
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'dev' on GitHub by visiting:
remote:      https://github.com/Stemgerlamo/Gym-Git-Exercise-Solutions/pull/new/dev
remote:
To https://github.com/Stemgerlamo/Gym-Git-Exercise-Solutions.git
 * [new branch]      dev -> dev
branch 'dev' set up to track 'origin/dev'.
PS C:\Users\acer\git-Exercise> git push -u origin test
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 855 bytes | 285.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'test' on GitHub by visiting:
remote:      https://github.com/Stemgerlamo/Gym-Git-Exercise-Solutions/pull/new/test
remote:
To https://github.com/Stemgerlamo/Gym-Git-Exercise-Solutions.git
 * [new branch]      test -> test
branch 'test' set up to track 'origin/test'.
PS C:\Users\acer\git-Exercise> git branch -D test
error: cannot delete branch 'test' used by worktree at 'C:/Users/acer/Git-Exercise'
PS C:\Users\acer\git-Exercise> git branch 
  dev
  main
* test
PS C:\Users\acer\git-Exercise> git checkout dev
error: Your local changes to the following files would be overwritten by checkout:
        readme.md
Please commit your changes or stash them before you switch branches.
Aborting
PS C:\Users\acer\git-Exercise> git add readme.md
PS C:\Users\acer\git-Exercise> git commi -m 'adding codes'
git: 'commi' is not a git command. See 'git --help'.

The most similar commands are
        commit
        column
        config
PS C:\Users\acer\git-Exercise> git commit -m 'adding codes'
[test 0560fbf] adding codes
 1 file changed, 40 insertions(+)
PS C:\Users\acer\git-Exercise> git push origin main
Everything up-to-date
PS C:\Users\acer\git-Exercise> git checkout dev
Switched to branch 'dev'
Your branch is up to date with 'origin/dev'.
PS C:\Users\acer\git-Exercise> git branch -D test
Deleted branch test (was 0560fbf).
PS C:\Users\acer\git-Exercise> git add .
PS C:\Users\acer\git-Exercise> git commit -m 'delete branch test'
On branch dev
Your branch is up to date with 'origin/dev'.

nothing to commit, working tree clean
PS C:\Users\acer\git-Exercise> git push origin --delete test
To https://github.com/Stemgerlamo/Gym-Git-Exercise-Solutions.git
 - [deleted]         test
```
### Exercise2
```bash
 # CHALENGE:Create a new home.html file, add some HTML changes, save them, and stash the changes. Repeat this process for about.html and team.html, stashing each change separately. Use git stash pop to restore the changes for about.html, then use stash pop with an index to bring back home.html. Commit and push the current changes. Restore team.html using stash pop with an index, then reset the current changes using git reset to revert to the state without team.html.

 #SOLUTION
 acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git add home.html

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git stash save 'modifying home.html'
Saved working directory and index state On main: modifying home.html

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ touch about.html 

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ echo "<h1>about Page</h1> "> about.html

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git add about.html
warning: in the working copy of 'about.html', LF will be replaced by CRLF the next time Git touches it

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git stash save "adding about.html"
Saved working directory and index state On main: adding about.html

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ touch team.html
echo "<h1>Team Page</h1>" > team.html
git add team.html
git stash save "Added team.html"
warning: in the working copy of 'team.html', LF will be replaced by CRLF the next time Git touches it
Saved working directory and index state On main: Added team.html

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git stash list
stash@{0}: On main: Added team.html
stash@{1}: On main: adding about.html
stash@{2}: On main: modifying home.html

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git stash pop stash@{1}
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Dropped stash@{1} (3c8924f94f2b49777ee840a24a6d34b395643abb)

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git stash list
stash@{0}: On main: Added team.html
stash@{1}: On main: modifying home.html

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git stash pop stash@{1}
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   home.html

Dropped stash@{1} (fa6e218b20805353b71bebd0af232f5f2a1a909d)

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git add . 

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git commit -m 'Restored home.html and about.html'
[main fa2a2dc] Restored home.html and about.html
 2 files changed, 13 insertions(+)
 create mode 100644 about.html

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git push 
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (7/7), 862 bytes | 172.00 KiB/s, done.
Total 7 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), done.
To https://github.com/Stemgerlamo/Gym-Git-Exercise-Solutions.git
   3118d89..fa2a2dc  main -> main

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git stash pop stash@{0}
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html

Dropped stash@{0} (2691f00885a4edb5d521ba29bace32834627e283)

acer@NBI MINGW64 ~/Desktop/Gym-Git-Exercise-Solutions (main)
$ git reset --hard HEAD
HEAD is now at fa2a2dc Restored home.html and about.html

```

### EXERCISE3
```bash

```