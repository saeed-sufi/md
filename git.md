* Git needs to know who is making the changes

  `  git config --global user.name saeed-sufi`<br>
  `  git config --global user.email saeed.sufi@hotmail.com`

* Git command who am I
`  git config --list
`
`  git add -A
`
`  git commit -m 'testing git'
`
* prints commits: `git log --oneline
`
* to go back a specific commit:
  `git checkout 900cfcf index.html`
* In order to get back to the last commit
  `git checkout -- .`
* remove staged file and from cache and move it back to untracked files.
  `git rm --cached index.html`
* A short report of status
  `git status -s`
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
* once you commit all the changes and the working directory is clean, you can create a new branch:
  `git branch count-to-ten`
  `git checkout count-to-ten `
* once you have finished working on a branch you are ready to merge it to the master branch. First be sure to checkout to master branch and then execute the following:
  `git merge count-to-ten`

  `git push origin count-to-fifteen`
* to delete a branch
  `git branch -d count-to-fifteen`
* create a new branch and check out to it in one move: 
  `git checkout -b our-features`
* if you want a dedicated commit for the merge so that all the commits could be reviewed in one place and (in case you have lots of commits already), then it's better to merge with disabled fast forward.
  `git merge our-features --no-ff`
* show a list of branches:
  `git branch`
  `git show-branch`
  `git branch -a`
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

the bug is now fixed.