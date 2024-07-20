* Git needs to know who is making the changes

  `  git config --global user.name saeed-sufi`<br>
  `  git config --global user.email saeed.sufi@hotmail.com`

* Git command who am I
`  git config --list
* prints commits: `git log --oneline
`
* to go back a specific commit:
  `git checkout 900cfcf index.html`
* In order to get back to the last commit
  `git checkout -- .`
* remove staged file and from cache and move it back to untracked files.
  `git rm --cached index.html`
* In order to delete .git 
  `rm -rf .git`
* `git remote add origin https://github.com/saeed-sufi/travel-agency.git`
* if you want to know where your github repo will be pushed to:
  `git remote -v`

* `git remote set-url origin https://github.com/saeed-sufi/travel-agency.git`

* to change branch name from master to main
  `git branch -m master main`
* to only clone one branch use the `--single-branch` option
  `git clone -b <branchname> --single-branch <remote-repo-url>`

* to see the status of local and remote branches:
  `git remote show origin`
* if you don't need to commit changes to a specific file.`git reset app/index.html` 

* to delete a branch
  `git branch -d count-to-fifteen`
* create a new branch and check out to it in one move: 
  `git checkout -b our-features`
* if you want a dedicated commit for the merge so that all the commits could be reviewed in one place and (in case you have lots of commits already), then it's better to merge with disabled fast forward.
  `git merge our-features --no-ff`
  
* This will get all the files at repo ready and available
  `git fetch `
  `git pull origin .gitignore` 
  
* for more extended comment use the following commenting method:
  `git commit -m "Subject" -m "Description..."`
  
* Create a branch on remote repository
  `git push origin <branch-name>`
  
* The following command, makes a branch named 'static' on the remote repo and push commit with d23ea94 hash (newer commits wouldn't be pushed)
  `git push origin d23ea94:refs/heads/static`
  
* Undo the last push from remote repository (make sure no one has made changes to the repository before proceeding)
  `git push -f origin <sha_of_previous_commit>:alpha-0.3.0`
  
* Delete remote branch
  `git push -d origin <branch_name>`
  
* To see what other commits your HEAD (or any other ref) has pointed to in the past
  `git reflog`
  
* A pull is just a fetch followed by a merge which means `git pull origin other-branch` is equivalent to `git fetch origin other-branch && git merge other-branch`.
  
* To delete a commit but keeping changes: (`git reset` without a --hard or --soft moves your HEAD to point to the specified commit, without changing any files.)
  `git reset HEAD^`
  
* To delete some commits and discarding any commits in between as if they were never there:
  `git reset --hard 79aaee0`

* To create a `hist` alias:
  `git config --global alias.hist "log --oneline --graph --decorate --all"`
  
* to check the alias entries and other info.
  `git config --global --list` 

* To store git token `git config credential.helper store` and to clear it `git config --unset credential.helper`

* To stash changes: `git stash` and to see the list of stashes: `git stash list`. To get back to the changes: `git stash pop`.

* To modify a specific commit do the following. Note that this will change the history from that commit forward. Also, you may run into merge conflicts with the new
er commits.
```
git rebase --interactive bbc64cdd~
change `pick` to `edit`
git commit -all --amend --no-edit
git rebase --continue
```
