- Excercise 1 
```
$>git ls-files -s
100644 980a0d5f19a64b4b30a87d4206aade58726b60e3 0       hello.txt
```
- Excercise 2 
```
$> echo "Hehe xin chao co ai khong" >hello.txt
$> git add -p
diff --git a/hello.txt b/hello.txt
index 980a0d5..b64db91 100644
--- a/hello.txt
+++ b/hello.txt
@@ -1 +1 @@
-Hello World!
+Hehe xin chao co ai khong
(1/1) Stage this hunk [y,n,q,a,d,e,?]? 
y - stage this hunk
n - do not stage this hunk
q - quit; do not stage this hunk or any of the remaining ones
a - stage this hunk and all later hunks in the file
d - do not stage this hunk or any of the later hunks in the file
e - manually edit the current hunk
? - print help
@@ -1 +1 @@
-Hello World!
+Hehe xin chao co ai khong
(1/1) Stage this hunk [y,n,q,a,d,e,?]? y
$> git status
On branch exercise2
Your branch is up to date with 'origin/exercise2'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   hello.txt

```
- Exercise 3
```
$> git reset hello.txt
Unstaged changes after reset:
M       hello.txt
$> git status
On branch exercise2
Your branch is up to date with 'origin/exercise2'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   hello.txt
```
- Exercise 4
```
$> git stash save "hello tieng viet"
Saved working directory and index state On exercise2: hello tieng viet
$> git status
On branch exercise2
Your branch is up to date with 'origin/exercise2'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        note.md

nothing added to commit but untracked files present (use "git add" to track)
$> git stash list
stash@{0}: On exercise2: hello tieng viet
$>  git stash apply stash@{0}
On branch exercise2
Your branch is up to date with 'origin/exercise2'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   hello.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        note.md

no changes added to commit (use "git add" and/or "git commit -a")
$>  git diff hello.txt
diff --git a/hello.txt b/hello.txt
index 980a0d5..b64db91 100644
--- a/hello.txt
+++ b/hello.txt
@@ -1 +1 @@
-Hello World!
+Hehe xin chao co ai khong
```