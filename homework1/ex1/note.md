- Exercise 1: 
```
$> mkdir -p ~/DSLab/homework/homework1/ex1

$> cd DSLab/homework/homework1/ex1

$> git status
fatal: Not a git repository (or any of the parent directories): .git

$> git init
Initialized empty Git repository in /Users/nnja/projects/sample/.git/
```
- Exercise 2 
```
$> echo 'Hello World!' > hello.txt

$> git add hello.txt

$> git commit -m "Initial commit"
```
- Exercise 3 
```
$> tree .git/objects
.git
├── branches
├── COMMIT_EDITMSG
├── config
├── description
├── HEAD
├── hooks
│   ├── applypatch-msg.sample
│   ├── commit-msg.sample
│   ├── fsmonitor-watchman.sample
│   ├── post-update.sample
│   ├── pre-applypatch.sample
│   ├── pre-commit.sample
│   ├── pre-merge-commit.sample
│   ├── prepare-commit-msg.sample
│   ├── pre-push.sample
│   ├── pre-rebase.sample
│   ├── pre-receive.sample
│   ├── push-to-checkout.sample
│   └── update.sample
├── index
├── info
│   └── exclude
├── logs
│   ├── HEAD
│   └── refs
│       └── heads
│           └── master
├── objects
│   ├── 58
│   │   └── 1caa0fe56cf01dc028cc0b089d364993e046b6
│   ├── 98
│   │   └── 0a0d5f19a64b4b30a87d4206aade58726b60e3
│   ├── ff
│   │   └── 767227596240d6f6e095ca9558d7dabda0eccd
│   ├── info
│   └── pack
└── refs
    ├── heads
    │   └── master
    └── tags
```
- Exercise 4: 
```
$> git cat-file -t 581caa0
tree
$> git cat-file -p 581caa0
100644 blob 980a0d5f19a64b4b30a87d4206aade58726b60e3    hello.txt
$> git cat-file -t 980a0d
blob
$> git cat-file -p 980a0d
Hello World!
$> git cat-file -t ff767227
commit
$> git cat-file -p ff767227
tree 581caa0fe56cf01dc028cc0b089d364993e046b6
author tammytrinh <trinhthiminhtamvq@gmail.com> 1692763148 +0700
committer tammytrinh <trinhthiminhtamvq@gmail.com> 1692763148 +0700

Initial commit
```
- Exercise 5
```
$> cat .git/HEAD
ref: refs/heads/master
$> cat .git/refs/heads/master
ff767227596240d6f6e095ca9558d7dabda0eccd
```
