*fancy log* `git reflog`

*view particular log* `git log HEAD@{5}`

*reset to certain point base on above info* `git reset --hard HEAD@{15}`

*When doing sth dangerous like --hard reset above, first do...* `git tag BACKUP`

*You can return back to it when things go owry with...* `git reset --hard BACKUP`

*like reflog with details* `git log -g`

*to give summary of commit* `git show abc1234 --stat`

*Lists all the config details in that clone* `git config --list`

*Squash commits long after they have been pushed. First * `git rebase -i issue-25-sth-sth~3` tilde 3 means the number of commits target from top. Then `git push origin +master`

*Detailed branch details and parent branches* `git branch -avv`

### Branch merging process
```
git checkout master
git pull               #to update the state to the latest remote master state
git merge develop      #to bring chnages to local master from your develop branch
git push origin master #push current HEAD to remote master branch
```
### Deleting a branch
Locally `git branch -D my_merged_branch`

Remote `git push --delete origin my_merged_branch`


***Sources***

http://stackoverflow.com/questions/134882/undoing-a-git-rebase

http://stackoverflow.com/questions/5667884/how-to-squash-commits-in-git-after-they-have-been-pushed

http://stackoverflow.com/questions/5189560/squash-my-last-x-commits-together-using-git/5201642#5201642
