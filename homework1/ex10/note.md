I thought the exercise will teach me how to install pre-commit and what to write on .yaml file but the exercise is stupid ;>>
- Exercise 1: 
```
$> cp pre-commit .git/hooks/pre-commit
$>  chmod +x .git/hooks/pre-commit
$>  exho "Bad bash script" > test_script.sh
Command 'exho' not found, did you mean:
  command 'exo' from snap exoscale-cli (v1.22.2)
  command 'echo' from deb coreutils (8.32-4.1ubuntu1)
See 'snap info <snapname>' for additional versions.
$>  echo "Bad bash script" > test_sc
ript.sh
$>  git add test_script.sh 
$>  git commit -m "Adding a new test script"
No shebang found! Not allowed to commit!
echo '#!/bin/bash\n Good bash script' > test_script.sh
$>  git add test_script.sh 
$>  git commit -m "Adding a new test script"
[exercise10 9082e1d] Adding a new test script
 1 file changed, 1 insertion(+)
 create mode 100644 test_script.sh
```