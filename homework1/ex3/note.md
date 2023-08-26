- Exercise 1
```
$> cat .git/HEAD
ref: refs/heads/exercise3
$>  git branch
  exercise2
* exercise3
  master
```
- Exercise 2
```
$> git show-ref --heads
43388fee19744e8893467331d7853a6475a227b8 refs/heads/exercise2
e348ebc1187cb3b4066b1e9432a614b464bf9d07 refs/heads/exercise3
43388fee19744e8893467331d7853a6475a227b8 refs/heads/master
$> git cat-file -p 43388fee  
tree 581caa0fe56cf01dc028cc0b089d364993e046b6
author Nina Zakharenko <nina@nnja.io> 1507168309 -0700
committer Nina Zakharenko <nina@nnja.io> 1507168309 -0700

Initial commit
$> git cat-file -p e348ebc
tree cbcdf5dda7853d595fe0b1942cb0d1d72eb910f3
parent 43388fee19744e8893467331d7853a6475a227b8
author Nina Zakharenko <nina@nnja.io> 1507168872 -0700
committer Nina Zakharenko <nina@nnja.io> 1507168872 -0700

Testing the emergency git-casting system
```
- Exercise 3
```
$> git tag my-exercise3-tag
$>  git show-ref --tags
e348ebc1187cb3b4066b1e9432a614b464bf9d07 refs/tags/my-exercise3-tag
$> git tag --points-at e348ebc
my-exercise3-tag
```
- Exercise 4
```
$> git tag -a "exercise3-annotated-tag" -m"This is my annotated tag for exercise 3"
$>  git show exercise3-annotated-tag
tag exercise3-annotated-tag
Tagger: tammytrinh <trinhthiminhtamvq@gmail.com>
Date:   Wed Aug 23 23:15:37 2023 +0700

This is my annotated tag for exercise 3

commit e348ebc1187cb3b4066b1e9432a614b464bf9d07 (HEAD -> exercise3, tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3)
Author: Nina Zakharenko <nina@nnja.io>
Date:   Wed Oct 4 19:01:12 2017 -0700

    Testing the emergency git-casting system

diff --git a/hello.txt b/hello.txt
index 980a0d5..b31a35b 100644
--- a/hello.txt
+++ b/hello.txt
@@ -1 +1,2 @@
 Hello World!
+This is a test of the emergency git-casting system.
```
- Exercise 5
```
$> git log --oneline
e348ebc (HEAD -> exercise3, tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3) Testing the emergency git-casting system
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master, exercise2) Initial commit
$> git checkout e348ebc 
Note: switching to 'e348ebc'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at e348ebc Testing the emergency git-casting system
$>  cat .git/HEAD
e348ebc1187cb3b4066b1e9432a614b464bf9d07
```
- Exercise 6
```
 $> echo "This is a test file" > dangle.txt
$>  git add dangle.txt
$> git commit -m "This is dangling commit"
[detached HEAD e5a47ea] This is dangling commit
 1 file changed, 1 insertion(+)
 create mode 100644 dangle.txt
$>  git log --oneline
e5a47ea (HEAD) This is dangling commit
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master, exercise2) Initial commit
$>  cat .git/HEAD
e5a47ea197f0113923bba95547e07a382ab216ec
$>  git checkout exercise3
Warning: you are leaving 1 commit behind, not connected to
any of your branches:

  e5a47ea This is dangling commit

If you want to keep it by creating a new branch, this may be a good time
to do so with:

 git branch <new-branch-name> e5a47ea

Switched to branch 'exercise3'
Your branch is up to date with 'origin/exercise3'.
$>  git branch for-q6-ex3 e5a47ea
```

