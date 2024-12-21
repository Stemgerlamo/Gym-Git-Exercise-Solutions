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

```