# qSTP Task
A repository to familiarize qstp students with git and github

# Instructions

## Task 1
* Make a fork of this repository
* Clone your fork to your device
* Create a new branch named `task01` (`git checkout -b task01`)
* Create a new file named `yourname.txt` in task01 directory with your name and BITS ID as the content (refer to gauravnarula.txt for an example)
* Commit the changes and push it to your fork `git push origin task01` (read it as push the task01 branch to the remote named origin)
* Browse to your repository on Github and submit a pull request


## Task 2

This task is about syncing your working branch with upstream before pushing the
changes. It might lead to "merge conflicts" at times, which is something which
happens when you and some other contributer make a change on the same line.
Before sending in a PR, it's good to ensure that your work does not introduce
any merge conflicts because the upstream has been updated since then.

We'll try to create a merge conflict scenario. Follow along

* Add a new remote named upstream, which points to my repository if you haven't
  already `git remote add upstream https://github.com/gnarula/qstp_task`
* If as of 29, May 2016, 3:35PM IST you haven't synced your the master branch of your repository with upstream, don't do it until this task is over.
* Checkout to a new branch `git checkout -b task02`
* Create a new folder named task02 and place a file `yourname.txt` in it. The
  name should be the same as the one used in task01
  Contents should be similar to
  ```
FirstName LastName
BITSID
Some text on the third line
  ```
* Add the file and commit the change. Do not push it yet
* Sync with upstream and rebase `git pull --rebase upstream master`
* You should end up with a merge conflict since in upstream, I've already
  written something on the 3rd line. 
  ![conflict](http://i.imgur.com/SlbMTn4.png)
* Let's resolve this by editing `task02/yourname.txt`
  ![resolve](http://i.imgur.com/uwS9CbM.png)

  The `<<<<<` arrows are followed by the hashstring of the commit that creates
  a conflict which happens to be
  [0ef80b1b](https://github.com/gnarula/qstp_task/commit/0ef80b1b) in our case

  To resolve a merge conflict, edit the file to what you'd rather want in that
  place. In our case, we edit the file so that it looks similar to

  ![post_resolve](http://i.imgur.com/TBtQpIE.png)

  Don't forget to save the file
* Add the file to the staging area (`git add task02/yourname.txt`) and continue
  with the rebase `git rebase --continue`
* Push your changes to your fork `git push origin task02` and submit a new PR

