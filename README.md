# GitHub Tutorial

_by Jaszmyn Hernandez_

---
## Git vs. GitHub

**Git** is your workspace.

**Github** is where your work will be stored.

The difference between the two is that most of the work will be done with git and its commands while github just holds the work that you have made. Git can be used alone while github requires git.


---
## Initial Setup

Of course, before we start working with git, you should have a github account and making one should be fairly easy.
1. go to github.com
2. put in the information that is required of you (username, email and password)
3. click the green button that says "create your account"
4. choose your plan, in this case the free one
5. click continue 
6. veryify your email and now youre done!

Next we have to get things in order so staying in personal settings go down till you see "SSH and GPG keys". Here you will see that there are no keys for either one so make one for SSH since this is what we will be using along with cloud9.   
After doing that you will be told to give the key as well as a title. Now the title can be anything but i would advise to make it "cloud9" since it will be what we will work with and the key you can also find on cloud9.  
To get the key needed, go to your cloud9 and click on the workspace you will be using. (**DO NOT** click clone or open just click the workspace in general). From there click the gear/settings in the top right corner next to the plus sign. next look to your left and find "SSH keys" and click on it. It will bring you to a place with two very long keys but you will only copy and paste the first one into github before clicking "add SSH key".

And with everything set up we can now continue


---
## Repository Setup

**git init:**  
`git init`
Initializes your repository so that you can use git commands.  
_(use this once at the beginning **inside** the directory you want to make your repository. To get inside use cd "directory name")_

Now that git is initialized you can start working with its commands. what you will mainly be using are `git add` and `git commit` these commands are used to save edits that you have made to your file. (more info on what they do in  Workflow & Commands)

Then if you want to save your work, _just in case cloud9 ever crashes and stops working_, you would want to make a new repo on github. This will be called your remote repository.  
To make a new repository on github look to the top left of the website at the plus sign that is between a bell and your profile image. Click on the plus sign and click "new repository".  
With the new repository made check at the top, _below the words "quick setup"_, and make sure that SSH is selected. This is to make things easier on yourself when you push, (more info on what push is/does in  Workflow & Commands), as your username and password wont have to be put in every time you want to push your new commits into your remote repository.  
Now with SSH chosen go down to "or push an existing repository from the command line" copy and paste the first line into the command line on cloud9 then the second one if you already have a commit ready to be pushed. (more in Workflow & Commands)
It doesnt matter in which order the repositories are made but what you need to make sure is that both repositories, the one from github and the one youve made made in cloud9, have the same name or else it wont work.


---
## Workflow & Commands

**git status:**  
`git status` is a way to check up on the status of your work.  
(use often as it can tell you if you added or committed your work along with some helpful hints.)

If a file (in this case modified:   README.md) has been modified but not added to the staging area it should apear red and above it would tell you how to add the file or remove the changes you have made

Example:
``` 
jaszmynh4085:~/workspace/github-tutorial (master) $ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

If a file (in this case modified:   README.md) has been added but not commited it should show up in green and tell you how to unsatge if you had made a mistake. 

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

The `-m ""` after `git commit` is for you to write a little note for yourself _and others_ on what you have done in that commit. It is best to keep it short and make sure that you do not use past tense such as "changed" in your message.


**git push:**  
`git push -u origin master`  
Pushes your commits to your remote repository and it tells the computer to remember where to push the commits (which is the master branch of your repository that had been nicked named "origin")  
_(this should be used once with your first commit)_

`git push`  
Also pushes your commits to your remote repository but does not tell it where to push the commits to.  
_(use this for other commits you have made after pushing your first commit with `git push -u origin master`)_

How it should look if done correctly:
``` bash
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

Some things were breifly mentioned in Workflow & Commands on how to undo changes but lets go over them again and inclue how to undo a commit/push. 

To undo a regular edit had not been added to the staging area use the command `git status` and above the modified file will be commands that you could use next. One of those commands (`git checkout -- <file>`) is for undoing your edits. all you have to do is add the name of your file in where it says "file".

If you had already added the file to the staging area do not worry. Again just use `git status` and above the modified file it will tell you to use `git reset HEAD <file>` to unstage. 

Now to undo commits is a little harder and `git status` will not be useful at this point. Plus there are multiple way to undo a commiti that can also undo add and edits. 

First lets start with just undoing the commit and to do that we will use the command `git reset --soft HEAD~1`. Using this command doesnt do anything to the changes and does not unstage the file that you've added. If you wanted you could just commit it all over again and nothing different would happen.

Next will be how to undo the commit and add by using the command `git reset HEAD~1`. So by using this the edits are still there but they have not been added to the staging area. (It is best to use this rather than whats coming next since maybe you only needed to add or delete something minor).

Finally to undo it all use the command `git reset --hard HEAD~1` which undoes everything from the commit to the edits you have made. This is very risky to do as somethings you had writen could still be important or used so only use this command when you are truly sure that what you have editied is unneeded. 

Last but not least is removing a push that you have made and its not that dificult as you can just remove the commit you have made in the repositary that you are currently working in then use the command `git push` to reset the remote repository back to that state.