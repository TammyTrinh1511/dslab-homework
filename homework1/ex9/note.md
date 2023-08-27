- Exercie 1: 
```
$> git grep -e "Python"
python_code.py:# This is a Python file
python_code.py:    print("Welcome to Python!")
$>  git grep --line-number -e "Python"
python_code.py:1:# This is a Python file
python_code.py:4:    print("Welcome to Python!")
$>  git grep --line-number --cached 
 -e "Python"
python_code.py:1:# This is a Python file
python_code.py:4:    print("Welcome to Python!")
echo "More Python code" >> python_code.py
$>  git grep --line-number -e "Python"
python_code.py:1:# This is a Python file
python_code.py:4:    print("Welcome to Python!")
python_code.py:5:More Python code
$>  git grep --line-number --cached  -e "Python"
python_code.py:1:# This is a Python file
python_code.py:4:    print("Welcome to Python!")
$>  git add python_code.py 
$>  git grep --line-number --cached 
-e "Python"
python_code.py:1:# This is a Python file
python_code.py:4:    print("Welcome to Python!")
python_code.py:5:More Python code

$> git checkout python_code.py
Updated 0 paths from the index
$>  git log --oneline
88f6e28 (HEAD -> exercise9, upstream/exercise9) Adding bash, python, and java code examples
43388fe (upstream/master, upstream/exercise7, upstream/exercise4, upstream/exercise2, upstream/HEAD, origin/master, exercise2) Initial commit
$>  git log exercise3 --oneline
e348ebc (tag: my-exercise3-tag, tag: exercise3-annotated-tag, upstream/exercise3, exercise3) Testing the emergency git-casting system
43388fe (upstream/master, upstream/exercise7, upstream/exercise4, upstream/exercise2, upstream/HEAD, origin/master, exercise2) Initial commit

#commit your changes or stash them to proceed

$> git stash
Saved working directory and index state WIP on exercise9: 88f6e28 Adding bash, python, and java code examples
$>  git cherry-pick e348ebc 
[exercise9 3a0c8c8] Testing the emergency git-casting system
 Author: Nina Zakharenko <nina@nnja.io>
 Date: Wed Oct 4 19:01:12 2017 -0700
 1 file changed, 1 insertion(+)

$> git log --oneline
3a0c8c8 (HEAD -> exercise9) Testing the emergency git-casting system
88f6e28 (upstream/exercise9) Adding bash, python, and java code examples
43388fe (upstream/master, upstream/exercise7, upstream/exercise4, upstream/exercise2, upstream/HEAD, origin/master, exercise2) Initial commit
```
- Exercise 3: 
```
$> git blame hello.txt
^43388fe (Nina Zakharenko 2017-10-04 18:51:49 -0700 1) Hello World!
3a0c8c80 (Nina Zakharenko 2017-10-04 19:01:12 -0700 2) This is a test of the emergency git-casting system.
$>  git rm java_code.java 
rm 'java_code.java'
$>  git commit -m "Who uses Java Anyway?"
[exercise9 898c44a] Who uses Java Anyway?
 1 file changed, 7 deletions(-)
 delete mode 100644 java_code.java

$> git log --diff-filter=D -- java_
code.java 
commit 898c44a7166db555f5c0049799167f92cfd95f25 (HEAD -> exercise9)
Author: tammytrinh <trinhthiminhtamvq@gmail.com>
Date:   Sat Aug 26 21:02:51 2023 +0700

    Who uses Java Anyway?

git blame  898c44a7166db555f5c0049799167f92cfd95f25^ -- java_code.java
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 1) // This is a Java file
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 2) 
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 3) public class HelloWorld {
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 4)    public static void main(String[] args) {
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 5)       System.out.println("Привет от Java!");
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 6)    }
88f6e286 (Nina Zakharenko 2017-10-05 11:31:34 -0700 7) }

$> git log --oneline
898c44a (HEAD -> exercise9) Who uses Java Anyway?
3a0c8c8 Testing the emergency git-casting system
88f6e28 (upstream/exercise9) Adding bash, python, and java code examples
43388fe (upstream/master, upstream/exercise7, upstream/exercise4, upstream/exercise2, upstream/HEAD, origin/master, exercise2) Initial commit
$>  git bisect start 898c44a 43388fe
Bisecting: 0 revisions left to test after this (roughly 1 step)
[3a0c8c80e539bef446b0757b732618c957b9ad44] Testing the emergency git-casting system
```
- Exercise 4: git bisect start <good_commit> <bad_commit>: it will show the middle commit 
```
$> git log --oneline
898c44a (HEAD -> exercise9) Who uses Java Anyway?
3a0c8c8 Testing the emergency git-casting system
88f6e28 (upstream/exercise9) Adding bash, python, and java code examples
43388fe (upstream/master, upstream/exercise7, upstream/exercise4, upstream/exercise2, upstream/HEAD, origin/master, exercise2) Initial commit
$>  git bisect start 898c44a 43388fe
Bisecting: 0 revisions left to test after this (roughly 1 step)
[3a0c8c80e539bef446b0757b732618c957b9ad44] Testing the emergency git-casting system
$>  cat hello.txt
Hello World!
This is a test of the emergency git-casting system.
$>  git bisect bad
Bisecting: 0 revisions left to test after this (roughly 0 steps)
[88f6e2864bd0829c71654f1d19096f436a66ce07] Adding bash, python, and java code examples
$>  cat hello.txt
Hello World!
$>  git bisect good
3a0c8c80e539bef446b0757b732618c957b9ad44 is the first bad commit
commit 3a0c8c80e539bef446b0757b732618c957b9ad44
Author: Nina Zakharenko <nina@nnja.io>
Date:   Wed Oct 4 19:01:12 2017 -0700

    Testing the emergency git-casting system

 hello.txt | 1 +
 1 file changed, 1 insertion(+)
```