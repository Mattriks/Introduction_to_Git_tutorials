# Introduction_to_Git_tutorials

## Clone (to get a local copy)
- `git clone https://github.com/Mattriks/reponame`  
- `git remote -v`
- `git remote add upstream https://gihub.com/upstreamdir/upstreamreponame` 

## Backup a branch
- `git checkout branchname`
- `git checkout -b branch_bk`
- `git checkout branchname`

## Commit list
- `git cherry -v master` # lists all commits cf master

## Stashing (keep edits without committing)
- `git stash list`
- `git stash` # works for current branch
- `git stash pop` # applies stash@{0} and removes from stash list
- `git stash drop stash@{1}`

## Rebasing ...
### To squash commits only
- `git checkout branchname`
- `git rebase -i HEAD~n` # n is the number of commits to squash
- `git push -f` # if there's nothing else to do

### Rebase a branch (with upstream/master, also works for branch master of a forked repo)


- `git checkout branchname` 
- `git fetch upstream`
- `git rebase upstream/master`

 fix any merge conflicts, then  
- `git add .`    and   `git rebase --continue` 
- `git push -f`

 
## Pull Requests:
Commit changes! \
In vscode use publish (to publish the branch to your forked repo) \
Go to your forked repo (in GitHub) and "Create pull request"

## Tags
- `git log --tags --simplify-by-decoration --pretty="format:%ai %d" | sort`

## If something goes badly:
- `git reset --hard branch_bk`

## Miscellaneous:
- `git branch` # branch list
- `git branch -D branch_bk` # delete branch
- `git clone https://github.com/upstreamdir/upstreamreponame -b PRbranchname` # clone a PR branch
- `git status`, `git pull` # e.g. update a cloned PR branch

### Rebase a stash (not convinced this is useful):
- `git stash pop stash@{#}`
- commit all changes
- `git fetch upstream`
- `git rebase upstream/master`  	# fix conflicts if needed 
- `git reset HEAD~1` 			# reverts to uncommitted edits

