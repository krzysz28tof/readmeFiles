# GIT



<!-- Staging -->

## Staging

## Reset
To **redo** all uncommitted changes you did after the last commit:

- git reset HEAD --hard
- git clean -fd 
(delete new files)



<!-- Branching -->

## Branching

<https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging>

HEAD points to the branch your working on

#### create branch
git branch B1

git checkout -b B1 
(create and checkout instantly)


#### visiting branch
git checkout B1


#### reversing changes
just switch to the master branch again

git checkout master


#### updating Master branch
git checkout master

git merge B1  
(merges changes of B1 to master)

if B1 is just some commits ahead of master, 
i.e. master is an ancestor of B1, 
then git just "fast-forwards" to the commit of B1.


#### deleting branch
git branch -d B1


#### merge commit
if you want to update the master, 
but master is not an ancestor of B1, 
i.e. master and B1 differ on some commit,
then we take master's version of that particular commit, 
and append the entirely new commits of B1.

if you've edited the same file in two different ways in the differentiating commit, 
then there will be a **DIFFICULT** merge conflict. 
You'll have to edit the files separately. 
Also the merge commit will not be created, and there will be so called *unmerged* files which you have to edit.

git status (will show you the unmerged files)

**git mergetool** will help you go through the files.
