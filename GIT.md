*fancy log* `git reflog`

*view particular log* `git log HEAD@{5}`

*reset to certain point base on above info* `git reset --hard HEAD@{15}`

*When doing sth dangerous like --hard reset above, first do...* `git tag BACKUP`

*You can return back to it when things go owry with...* `git reset --hard BACKUP`

*like reflog with details* `git log -g`

*to give summary of commit* `git show abc1234 --stat`

*view staged changes* `git diff --cached`

*Lists all the config details in that clone* `git config --list`

*Squash commits long after they have been pushed. First * `git rebase -i issue-25-sth-sth~3` tilde 3 means the number of commits target from top. Then `git push origin +master`

*Detailed branch details and parent branches* `git branch -avv`

*Switch to master branch proper*
```
git fetch --all
git reset --hard origin/master
```

*View the contents of git stash [4]*
```
git stash show -p stash@{0}
```

*Remove last commit both from local and remote [3]*
```
git reset --hard HEAD^ 
git push -f
```

*Rename any other branch while pointing to any othet branch [5]*
```
git branch -m <newname>
```

*Rename the current local branch [5]*
```
git branch -m <oldname> <newname>
```

### Branch merging process
```
git checkout master
git pull               # to update the state to the latest remote master state
git merge develop      # to bring chnages to local master from your develop branch
git merge --squash --no-commit develop # to avoid the default git Merge message
git merge --no-commit --no-ff # merge without fast-forwarding and stop commiting with default merge msg
git push origin master # push current HEAD to remote master branch
```

### Getting the raw file from the repo
Standing on scalable-kenya-counties `git cat-file blob 16bab8a^:counties-global.svg`

### Deleting a branch
Locally `git branch -D my_merged_branch`

Remote `git push --delete origin my_merged_branch`

BEFORE MERGE TO MASTER, SQUASH COMMITS!!!!!!!!! SON

### Git-merge-squash
```
git checkout master
git merge --squash bugfix
git commit
```

### Avoid the default merge message [7]
```
git merge --no-commit issue-#-name-title
git commit -sm 'blah blah...'
```

### To fixup and commit that went without the proper changes. Mind lapse thing
```
git reflog issue-name-of-branch
```
### After finding the hash that you want to fix [8]
```
git commit --fix abcd254
```
### [9] Make submodule checkout master branch or any other branch. Pedding it somehow
```
git config -f .gitmodules submodule.freeboard.branch master
```

### [10] Rebase without repeating history by using --force
```
git rebase -i origin/master
git push -f origin branch-name
```


***Sources***

[0] http://stackoverflow.com/questions/134882/undoing-a-git-rebase  
[1] http://stackoverflow.com/questions/5667884/how-to-squash-commits-in-git-after-they-have-been-pushed  
[2] http://stackoverflow.com/questions/5189560/squash-my-last-x-commits-together-using-git/5201642#5201642  
[3] http://stackoverflow.com/questions/4647301/rolling-back-local-and-remote-git-repository-by-1-commit  
[4] http://stackoverflow.com/questions/10725729/git-see-whats-in-a-stash-without-applying-stash  
[5] http://stackoverflow.com/questions/6591213/how-to-rename-local-branch  
[6] http://stackoverflow.com/questions/5308816/how-to-use-git-merge-squash  
[7] http://stackoverflow.com/questions/3594894/how-to-avoid-merge-branch-name-of-branch-in-commit-messages  
[8] http://fle.github.io/git-tip-keep-your-branch-clean-with-fixup-and-autosquash.html  
[9] https://git-scm.com/book/en/v2/Git-Tools-Submodules
