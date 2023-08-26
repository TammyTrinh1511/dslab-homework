- Exercise 1
```
git checkout exercise4
Branch 'exercise4' set up to track remote branch 'exercise4' from 'origin'.
Switched to a new branch 'exercise4'
$>  git merge exercise3
Updating 43388fe..e348ebc
Fast-forward
 hello.txt | 1 +
 1 file changed, 1 insertion(+)
$>  git log --oneline
e348ebc (HEAD -> exercise4, tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master, exercise2) Initial commit
```
- Exercise 2
```
$> git reset --hard HEAD^
HEAD is now at 43388fe Initial commit
$>  git merge --no-ff exercise3
Merge made by the 'ort' strategy.
 hello.txt | 1 +
 1 file changed, 1 insertion(+)
$> git log --graph
*   commit 249a5b517d9caac196afd11009be695d3b7a1417 (HEAD -> exercise4)
|\  Merge: 43388fe e348ebc
| | Author: tammytrinh <trinhthiminhtamvq@gmail.com>
| | Date:   Thu Aug 24 09:14:05 2023 +0700
| | 
| |     Merge branch 'exercise3' into exercise4
| | 
| * commit e348ebc1187cb3b4066b1e9432a614b464bf9d07 (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3)
|/  Author: Nina Zakharenko <nina@nnja.io>
|   Date:   Wed Oct 4 19:01:12 2017 -0700
|   
|       Testing the emergency git-casting system
| 
* commit 43388fee19744e8893467331d7853a6475a227b8 (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master, exercise2)
  Author: Nina Zakharenko <nina@nnja.io>
  Date:   Wed Oct 4 18:51:49 2017 -0700
  
      Initial commit
```
- Exercise 3
```
$> git branch
  exercise2
  exercise3
* exercise4
  for-q6-ex3
  master

$> git checkout -b mundo
Switched to a new branch 'mundo'

$> git branch
  exercise2
  exercise3
  exercise4
  master
  for-q6-ex3
* mundo
echo 'Hello Mundo' >hello.txt
$>  git status
On branch mundo
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   hello.txt

no changes added to commit (use "git add" and/or "git commit -a")
git add hello.txt 
$>  git commit -m "Change World to Mundo"
[mundo e988ff0] Change World to Mundo
 1 file changed, 1 insertion(+), 2 deletions(-)
$>  git checkout exercise4
Switched to branch 'exercise4'
Your branch is ahead of 'origin/exercise4' by 2 commits.
  (use "git push" to publish your local commits)
$>  echo 'Hola World' > hello.txt
$>  git add hello.txt 
$>  git commit -m "Change Hello to Hola"
[exercise4 10d86e9] Change Hello to Hola
 1 file changed, 1 insertion(+), 2 deletions(-)
```
- Exercise 4
```
$>  git config rerere.enabled true
$>  git merge mundo
Auto-merging hello.txt
CONFLICT (content): Merge conflict in hello.txt
Recorded preimage for 'hello.txt'
Automatic merge failed; fix conflicts and then commit the result.
git rerere diff
--- a/hello.txt
+++ b/hello.txt
@@ -1,5 +1,5 @@
-<<<<<<<
-Hello Mundo
-=======
+<<<<<<< HEAD
 Hola World
->>>>>>>
+=======
+Hello Mundo
+>>>>>>> mundo
$> echo 'Hola Mundo!' > hello.txt 
$>  git rerere diff
--- a/hello.txt
+++ b/hello.txt
@@ -1,5 +1 @@
-<<<<<<<
-Hello Mundo
-=======
-Hola World
->>>>>>>
+Hola Mundo!
$>  git add hello.txt 
$>  git commit -m 'Merging in mundo branch'
Recorded resolution for 'hello.txt'.
[exercise4 bf2ae55] Merging in mundo branch
```
- Exercise 5
```
$> git reset --hard HEAD^
HEAD is now at 10d86e9 Change Hello to Hola
$>  git merge mundo
Auto-merging hello.txt
CONFLICT (content): Merge conflict in hello.txt
Resolved 'hello.txt' using previous resolution.
Automatic merge failed; fix conflicts and then commit the result.
$>  cat hello.txt 
Hola Mundo!

$> git add hello.txt
$> git commit -m 'Back up and merge again'
[exercise4 d893b4c] Back up and merge again
```