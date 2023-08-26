- Exercise 1
```
$> cat hello.txt 
Hola Mundo!
This is a test of the emergency git-casting system.
$>  git mv
hello.txt hello.template
git: 'mvhello.txt' is not a git command. See 'git --help'.
$>  git mv
 hello.txt hello.template
$> git add hello.template 
$> git commit
[exercise5 9170afc] Change file name
 1 file changed, 1 insertion(+), 1 deletion(-)
 rename hello.txt => hello.template (81%)
```
- Exercise 2
```
$> git log --since="yesterday"
commit 9170afcdafb55fc2ad23325890739a91c11a73ff (HEAD -> exercise5)
Author: tammytrinh <trinhthiminhtamvq@gmail.com>
Date:   Thu Aug 24 23:44:51 2023 +0700

    Change file name
$> git log --name-status --follow --oneline hello.template
9170afc (HEAD -> exercise5) Change file name
R081    hello.txt       hello.template
fec9e7b Changing Hello to Hola
M       hello.txt
afa34a6 Changing World to Mundo
M       hello.txt
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
M       hello.txt
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master, exercise2) Initial commit
A       hello.txt
### The answer in github is git log --grep=i18n --author=nina --since=2.weeks, 'grep' keyword tell that git log command to search fot the string i18n in the log files, and since my terminal didn't appear anything and the last time commit if 6 years ago, I change --since in the cmd line
$> git log  --author=nina --since=7.years
commit ff91b70c7f23de6b168dc60478f270e8e3f992a8 (origin/exercise5)
Merge: fec9e7b afa34a6
Author: Nina Zakharenko <nina@nnja.io>
Date:   Wed Oct 4 19:51:40 2017 -0700

    Merging in mundo branch

commit fec9e7b9f23a77bbc8e15603de0d7ea9152c7222
Author: Nina Zakharenko <nina@nnja.io>
Date:   Wed Oct 4 19:50:45 2017 -0700

    Changing Hello to Hola

commit 4582f72b8839b832aec19015bd0447ceac044899
Merge: 43388fe e348ebc
Author: Nina Zakharenko <nina@nnja.io>
Date:   Wed Oct 4 19:49:49 2017 -0700

    Merge branch 'exercise3' into exercise4

commit afa34a64f5711c79486465d6fa1c77a9a6109d84
Author: Nina Zakharenko <nina@nnja.io>
Date:   Wed Oct 4 19:23:18 2017 -0700

git log --diff-filter=R --find-renames
commit 9170afcdafb55fc2ad23325890739a91c11a73ff (HEAD -> exercise5)
Author: tammytrinh <trinhthiminhtamvq@gmail.com>
Date:   Thu Aug 24 23:44:51 2023 +0700

    Change file name
$>  git log --diff-filter=M --oneline
fec9e7b Changing Hello to Hola
afa34a6 Changing World to Mundo
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
```
- Exercise 3
```
$> git log --oneline
9170afc (HEAD -> exercise5) Change file name
ff91b70 (origin/exercise5) Merging in mundo branch
fec9e7b Changing Hello to Hola
4582f72 Merge branch 'exercise3' into exercise4
afa34a6 Changing World to Mundo
7ea8b01 Merge branch 'exercise3' into exercise4
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master, exercise2) Initial commit
$>  git show 9170afc
commit 9170afcdafb55fc2ad23325890739a91c11a73ff (HEAD -> exercise5)
Author: tammytrinh <trinhthiminhtamvq@gmail.com>
Date:   Thu Aug 24 23:44:51 2023 +0700

    Change file name

diff --git a/hello.txt b/hello.template
similarity index 81%
rename from hello.txt
rename to hello.template
index 7018e35..bddb90d 100644
--- a/hello.txt
+++ b/hello.template
@@ -1,2 +1,2 @@
-Hola Mundo!
+Hola Mita!
 This is a test of the emergency git-casting system.
$>  git show 9170af --stat --oneline
9170afc (HEAD -> exercise5) Change file name
 hello.txt => hello.template | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```
- Exercise 4
```
git branch --merged master
  exercise2
  master
$>  git branch --no-merged master
  exercise3
  exercise4
* exercise5
  exercise6
  for-q6-ex3
  mundo
```
