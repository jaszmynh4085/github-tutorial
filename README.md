# GitHub Tutorial

_by Jaszmyn Hernandez_

---
## Git vs. GitHub

**git** is your workspace.

**github** is where your work will be stored.

the difference between the two is that most of the work will be done with git and its commands while github just holds the work that you have made. git can be used alone while github requires git.


---
## Initial Setup



---
## Repository Setup

**git init:**  
Initializes your repository so that you can use git commands.



---
## Workflow & Commands

**git status:**  
A way to check up on the status of your work.  
(use often as it can tell you if you added or committed your work along with some helpful hints.)

if a file has been modified but not added to the staging area it will apear red and above it would tell you how to add the file or remove the changes you have made

Example:
```bash
jaszmynh4085:~/workspace/github-tutorial (master) $ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

if a file has been added but not commited it will show up in green and tell you how to unsatge if you had made a mistake. 

Example:
```bash
jaszmynh4085:~/workspace/github-tutorial (master) $ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   README.md
```

**git add:**  
`git add <filename>`  
Adds your edits to the staging area.  
(think of bringing people in the frame for a picture)


**git commit:**  
`git commit -m "<message>"`  
Commits whats on the staging area. _Sorta like finalizing it_  
(think of taking a picture of the people you had just added into frame)

The `-m ""` after `git commit` is for you to write a little note for yourself _and others_ on what you have done in that commit. It is best to keep it sort and make sure that you do not use past tense such as "changed" in your notes.


**git push:**  
`git push -u origin master`  
Pushes your commits to your remote repository and it tells the computer to remember where to push the commits (which is the master branch of your repository that had been nicked named "origin")  
_(this should be used once at the beginning)_

`git push`  
Also pushes your commits to your remote repository but does not tell it where to push the commits to.  
_(use this for other commits you have made after pushing your first commit with `git push -u origin master`)_

How it should look if done correctly:
```bash
jaszmynh4085:~/workspace/github-tutorial (master) $ git push
Warning: Permanently added 'github.com,192.30.253.112' (RSA) to the list of known hosts.
Counting objects: 3, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 640 bytes | 640.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:jaszmynh4085/github-tutorial.git
   3112af2..853bb2a  master -> master
```

---
## Rolling Back Changes