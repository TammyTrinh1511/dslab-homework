- Exercise 1
```
$> echo "Bad data" > hello.template
$>  cat hello.template
Bad data
$>  git checkout -- hello.template
$>  cat hello.template 
[greeting] [noun]!
This is a test of the emergency git-casting system.
$>  git lo
g --name-status --follow --oneline hello.template
4b2b90e (HEAD -> exercise6, origin/exercise6) Replacing greeting with tokens for i18n
R073    hello.txt       hello.template
fec9e7b Changing Hello to Hola
M       hello.txt
afa34a6 Changing World to Mundo
M       hello.txt
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
M       hello.txt
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master, exercise2) Initial commit
A       hello.txt

$> git log --name-status --follow --oneline hello.template
4b2b90e (HEAD -> exercise6, origin/exercise6) Replacing greeting with tokens for i18n
R073    hello.txt       hello.template
fec9e7b Changing Hello to Hola
M       hello.txt
afa34a6 Changing World to Mundo
M       hello.txt
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
M       hello.txt
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master, exercise2) Initial commit
A       hello.txt
$>  git checkout fec9e7b -- hello.txt
cat hello.txt
Hola World!
This is a test of the emergency git-casting system.
git reset HEAD hello.txt
$>  git rm hello.template 
rm 'hello.template'
$>  git status
On branch exercise6
Your branch is up to date with 'origin/exercise6'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    hello.template

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        hello.txt

$>  git commit -m "Deleting hello.template"
[exercise6 17a35b3] Deleting hello.template
 1 file changed, 2 deletions(-)
 delete mode 100644 hello.template
$>  git log --diff-filter=D --oneline -- hello.template
17a35b3 (HEAD -> exercise6) Deleting hello.template
$>  git checkout 17a35b3^ -- hello.template
$>  git status
On branch exercise6
Your branch is ahead of 'origin/exercise6' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   hello.template

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        hello.txt

$>  cat hello.template
[greeting] [noun]!
This is a test of the emergency git-casting system.
```
- Exercise 2
```
$> git clean --dry-run
Would remove hello.txt
$>  git clean -f
Removing hello.txt
```
- Exercise 3
```
$> git status
On branch exercise6
Your branch is ahead of 'origin/exercise6' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   hello.template

$>  git reset -- hello.template
$>  git status
On branch exercise6
Your branch is ahead of 'origin/exercise6' by 1 commit.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        hello.template

nothing added to commit but untracked files present (use "git add" to track)
$> git log --oneline
17a35b3 (HEAD -> exercise6) Deleting hello.template
4b2b90e (origin/exercise6) Replacing greeting with tokens for i18n
ff91b70 (origin/exercise5) Merging in mundo branch
fec9e7b Changing Hello to Hola
4582f72 Merge branch 'exercise3' into exercise4
afa34a6 Changing World to Mundo
7ea8b01 Merge branch 'exercise3' into exercise4
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, origin/exercise3, exercise3) Testing the emergency git-casting system
43388fe (origin/master, origin/exercise7, origin/exercise4, origin/exercise2, origin/HEAD, master, exercise2) Initial commit
$>  rm hello.template 
$>  cat hello.template
cat: hello.template: No such file or directory
$>  git reset 4b2b90e -- hello.template 
Unstaged changes after reset:
D       hello.template
$>  git status
On branch exercise6
Your branch is ahead of 'origin/exercise6' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   hello.template

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    hello.template

$>  cat hello.template
cat: hello.template: No such file or directory

$> git log -2 --oneline
17a35b3 (HEAD -> exercise6) Deleting hello.template
4b2b90e (origin/exercise6) Replacing greeting with tokens for i18n
$>  git reset 4b2b90e
Unstaged changes after reset:
D       hello.template
$>  git log -1 4b2b90e
commit 4b2b90ec4f526139ca9c81e22174ebf5b9c56b52 (HEAD -> exercise6, origin/exercise6)
Author: Nina Zakharenko <nina@nnja.io>
Date:   Wed Oct 4 20:46:45 2017 -0700

    Replacing greeting with tokens for i18n
    
    Currently, hello.txt contains both Spanish and English.
    Let's replace Hola with a [greeting] token, and Mundo
    with a [noun] token. That way, we can localize hello.txt for
    any language!
$>  git reset ORIG_HEAD
$>  git log -1 --oneline
17a35b3 (HEAD -> exercise6) Deleting hello.template
```
- Exercise 4 
```
$> git log -1 --oneline
17a35b3 (HEAD -> exercise6) Deleting hello.template
$>  git revert 17a35b3
[exercise6 9cdc8c9] Revert "Deleting hello.template"
 1 file changed, 2 insertions(+)
 create mode 100644 hello.template
```
