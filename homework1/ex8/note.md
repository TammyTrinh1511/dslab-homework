- Exercise 1 
- Exercise 2
```
$> git remote -v
origin  https://github.com/nnja/advanced-git-exercises.git (fetch)
origin  https://github.com/nnja/advanced-git-exercises.git (push)
$> git remote rename origin upstream
$> git remote -v
upstream        https://github.com/nnja/advanced-git-exercises.git (fetch)
upstream        https://github.com/nnja/advanced-git-exercises.git (push)
$> git remote add origin git@github.com:TammyTrinh1511/advanced-git-exercises.git
$> git remote -v
origin  git@github.com:TammyTrinh1511/advanced-git-exercises.git (fetch)
origin  git@github.com:TammyTrinh1511/advanced-git-exercises.git (push)
upstream        https://github.com/nnja/advanced-git-exercises.git (fetch)
upstream        https://github.com/nnja/advanced-git-exercises.git (push)
$> git checkout master 
Switched to branch 'master'
Your branch is ahead of 'upstream/master' by 1 commit.
  (use "git push" to publish your local commits)
```
- Exercise 3
```
$> git checkout master 
Switched to branch 'master'
Your branch is ahead of 'upstream/master' by 1 commit.
  (use "git push" to publish your local commits)
$> git fetch origin master
From github.com:TammyTrinh1511/advanced-git-exercises
 * branch            master     -> FETCH_HEAD
 * [new branch]      master     -> origin/master
$> git branch --set-upstream-to origin/master
Branch 'master' set up to track remote branch 'master' from 'origin'.
echo "Change to local repo" > local_change.txt
$> git add local_change.txt
$> git add local_change.txt
$> git pull --rebase upstream master
error: cannot pull with rebase: Your index contains uncommitted changes.
error: please commit or stash them.
$> ls
hello.txt  local_change.txt  upstream_change.txt
$> git commit -m "Change to local repo"
[feature 682d1fc] Change to local repo
 1 file changed, 1 insertion(+)
 create mode 100644 local_change.txt
$> git pull --rebase upstream master
From https://github.com/nnja/advanced-git-exercises
 * branch            master     -> FETCH_HEAD
Current branch feature is up to date.
$> git log --oneline
682d1fc (HEAD -> feature) Change to local repo
2afedc1 (master) Change to the upstream repo
3dca028 Master has continued to change
43388fe (upstream/master, upstream/exercise7, upstream/exercise4, upstream/exercise2, upstream/HEAD, origin/master, exercise2) Initial commit
```
After fixing bugs in ex3, I realize that if you use ```git remote add origin git@github.com:TammyTrinh1511/advanced-git-exercises.git```, 
you have to add SSH keys and ```git fetch origin master``` before changing brach checkout to track our personal copy - ```origin/master```