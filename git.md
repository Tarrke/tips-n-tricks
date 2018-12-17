# Git Tricks

## Amend author on multiple commits

Some time I do not configure correctly my user on a git repo localy. Hence some commits are not done with the right author. Here is the trick I use to redo all theses commits in a quite acceptable fast way

1. Change the author localy
  ```bash
  git config user.name Tarrke
  git config user.email tarrke [at] provider
  ```

2. Find the last working commit
  ```bash
  git log
  commit fe7d7451e28737b9aa66b38db2aa0470bb95286f
  Author: Tarrke <tarrke@gmail.com>
  Date:   Fri Sep 7 15:55:22 2018 +0200

      add creating a new react project

  commit 9943e8b9e1cd369d97f99923c64fa52560ea9ee3
  Author: Tarrke <tarrke@gmail.com>
  Date:   Fri Sep 7 15:55:10 2018 +0200

      structure of tips
  ```

3. Rebase the work since then
  ```bash
  git rebase -i COMIT_HASH
  ```
  In the editor that open, chose edit for the commits you want to edit.

4. For each commit to edit
  ```bash
  git commit --amend --reset-author
  git rebase --continue
  ```

5. Do not forget to push your modifications, imposing them
  ```bash
  git push orign +branch
  ```
  
  ## Keep fork repo sync with upstream
  
  ```bash
  git fetch upstream
  git checkout master
  git merge upstream/master
  ```

## Send a non git local directory to a github repository :
```bash
git init
git config user.name = Toto
git config user.email = toto@sky.org 
git add something
git commit -m "Copy local to remote"
git remote add origin https://github.com/Tarrke/test_git.git
git push -u origin master
```
