- Exercise 1: 
```
$> echo "This is the first file" > first.txt
$> echo "This is the second file" > second.txt
$> git add first.txt
$> git commit -m "Committing two new files"
[exercise7 affee2e] Committing two new files
 1 file changed, 1 insertion(+)
 create mode 100644 first.txt
$> git add second.txt 
$> git commit --amend
[exercise7 0252eac] Committing two new files
 Date: Fri Aug 25 00:55:06 2023 +0700
 2 files changed, 2 insertions(+)
 create mode 100644 first.txt
 create mode 100644 second.txt
```
- Exercise 2: 
```
$> git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
$> git checkout -b exercise7-2
Switched to a new branch 'exercise7-2'
$> git log --oneline
43388fe (HEAD -> exercise7-2, origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master, exercise2) Initial commit
$> echo "New feature" > feature.txt
$> git add feature.txt 
$> git commit -m "Adding a new feature"
[exercise7-2 be317c5] Adding a new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
$> git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
$> echo "Master has continued to change" >> hello.txt
git add hello.txt
$> git commit -m "Master has continued to change"
[master 3dca028] Master has continued to change
 1 file changed, 1 insertion(+)
$> git checkout exercise7-2
Switched to branch 'exercise7-2'
git rebase master
Successfully rebased and updated refs/heads/exercise7-2.
$> git log --oneline
6b12b93 (HEAD -> exercise7-2) Adding a new feature
3dca028 (master) Master has continued to change
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, exercise2) Initial commit
```
- Exercise 3: 
```
$> echo "Another new feature" > another_feature.txt
$> git add another_feature.txt
$> git commit -m "Adding another new feature"
[exercise7-2 b221b15] Adding another new feature
 1 file changed, 1 insertion(+)
 create mode 100644 another_feature.txt
$> git log -n 3 --oneline
b221b15 (HEAD -> exercise7-2) Adding another new feature
6b12b93 Adding a new feature
3dca028 (master) Master has continued to change


$> git rebase -i HEAD~2
[detached HEAD a71b9c3] Adding two new features
 Date: Sat Aug 26 15:33:47 2023 +0700
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
Successfully rebased and updated refs/heads/exercise7-2.
$> git rebase -i HEAD~2
[detached HEAD c7d129a] Adding two new features
 Date: Sat Aug 26 15:33:47 2023 +0700
 2 files changed, 2 insertions(+)
 create mode 100644 another_feature.txt
 create mode 100644 feature.txt
Successfully rebased and updated refs/heads/exercise7-2.

$> git log --oneline
c7d129a (HEAD -> exercise7-2) Adding two new features
3dca028 (master) Master has continued to change
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, exercise2) Initial commit

```