All the command lines are noted in the note.md file of each folder. 
This is the summary of every git command line in each exercise

- Exercise 1:
`tree .git`
`git cat-file -t <hash>` : type (tree or blob)
`git cat-file -p <hash>` : print (name file, hash file)
`cat file`: show file

 - Exercise 2:
`git ls-files -s`: list files, show SHA1 hash
`git add -p`: stage changes interactively, 
`git reset file`: unstaged changes
`git stash save`: stash your uncommitted changes and save with message
`git stash list`: show list of stash
`git stash show stash@{0)`
`git stash apply stash@{0}`
`git diff file`

- Exercise 3:
`git tag name-tag`: simply named pointers to a commit (lightweight tag)
`git show-ref --heads`: see which commits your HEADs are pointing at
`git tag -a '' -m ''`: annotated tags, the same as regular tags but store additional metadata
`git show annotated-data`
`git checkout e348ebc`: detached HEAD, use `cat .git/HEAD` to see what HEAD points to

- Exercise 4:
`git merge branch`: fast-forward merge
`git reset --hard HEAD^`: back things up to the last commit.
`git merge --no-ff exercise3`: non-fast-forward merge (the feature branch still exist)
`git config rerere.enabled true`: allows Git to remember how you resolved a conflict in a file so that the next time it encounters the same conflict, it can automatically resolve it for you
` git rerere diff`

- Exercise 5:
`git mv hello.txt hello.template`: rename
`git log --since="yesterday"`
`git log --name-status --follow --oneline hello.template`
`git log --grep=i18n --author=nina --since=2.weeks`:  filter the results to only show commits that contain the string i18n.
`git log --diff-filter=R --find-renames`: find commits where files have been renamed
`git log --diff-filter=M --oneline`: find commits where files have been modified
`git branch --merged master` : show branch has merged to master
`git branch --no-merged master`:  show branch has not merged to master

- Exercise 6:
`git checkout hash -- file`: checkout to hash commit
`git reset HEAD hello.txt`: reset it to unstage it and clear the staging area
`git rm file`: remove file
`git log --diff-filter=D --oneline -- hello.template`: track down file we deleted
`git clean --dry-run`: clean all file deleted
`git clean -f`
`git revert hash`: undo deleting

- Exercise 7:
`git commit --amend`: add and commit but havent push, gop 2 cai lai 
`git rebase`

- Exercise 8: set up our local repository so that your fork is the origin
` git remote -v`
`git remote rename origin upstream`
`git remote add origin git@github.com:mhenstell/advanced-git-exercises.git`
`git branch --set-upstream-to origin/master`

- Exercise 9:
` `
