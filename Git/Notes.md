GIT Lab

 
 
 
 

 

Public IP address for Connecting : 3.108.221.108

login as: ec2-user
[ec2-user@ip-172-31-42-58 ~]$ sudo su
[root@ip-172-31-42-58 ec2-user]# yum update -y
[root@ip-172-31-42-58 ec2-user]# yum install git -y
[root@ip-172-31-42-58 ec2-user]# which git
[root@ip-172-31-42-58 ec2-user]# git --version
[root@ip-172-31-42-58 ec2-user]# git config --global user.name "Employee1"
[root@ip-172-31-42-58 ec2-user]# git config --global user.email "Employee1@company.com"
[root@ip-172-31-42-58 ec2-user]# git config –list








Creating Virginia Instances
 
 
 
 
[ec2-user@ip-172-31-81-102 ~]$ sudo su
[root@ip-172-31-81-102 ec2-user]# yum update -y
[root@ip-172-31-81-102 ec2-user]# yum install git -y
[root@ip-172-31-81-102 ec2-user]# git --version
[root@ip-172-31-81-102 ec2-user]# git config --global user.name "Employee2"
[root@ip-172-31-81-102 ec2-user]# git config --global user.email "Employee2@company.com"
[root@ip-172-31-81-102 ec2-user]# git config –list







Connect to the Mumbai Instance and run below commands;
Initially I missed running sudo su
[ec2-user@ip-172-31-42-58 ~]$ mkdir mumbaigit
[ec2-user@ip-172-31-42-58 ~]$ ls
[ec2-user@ip-172-31-42-58 ~]$ cd mumbaigit
[ec2-user@ip-172-31-42-58 mumbaigit]$ git init
[ec2-user@ip-172-31-42-58 mumbaigit]$ cat >mumbai1
printf("Hello Mumbai")
[ec2-user@ip-172-31-42-58 mumbaigit]$ cat mumbai1
[ec2-user@ip-172-31-42-58 mumbaigit]$ git status
[ec2-user@ip-172-31-42-58 mumbaigit]$ git add .
[ec2-user@ip-172-31-42-58 mumbaigit]$ git status
[ec2-user@ip-172-31-42-58 mumbaigit]$ git status
[ec2-user@ip-172-31-42-58 mumbaigit]$ git log
[root@ip-172-31-42-58 mumbaigit]# git  show 498964ecac01375d6f33df0b49f7f7478afcb537
[root@ip-172-31-42-58 mumbaigit]# git remote add origin https://github.com/nayak22/Devops.git
[root@ip-172-31-42-58 mumbaigit]# git push -u origin master
[root@ip-172-31-42-58 mumbaigit]# cat >>mumbai1
#adding additional lines to the file
print("Added new Line");
[root@ip-172-31-42-58 mumbaigit]# git status
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git commit -m "Second Commit from Mumbai Region"
[root@ip-172-31-42-58 mumbaigit]# git status
[root@ip-172-31-42-58 mumbaigit]# git log
[root@ip-172-31-42-58 mumbaigit]# git show 462e4392ee121854d5542029fb7389943aec1fce
[root@ip-172-31-42-58 mumbaigit]# git push -u origin master




Connect to Virginia Instance
[ec2-user@ip-172-31-81-102 ~]$ sudo su
[root@ip-172-31-81-102 ec2-user]# ls
[root@ip-172-31-81-102 ec2-user]# which git
[root@ip-172-31-81-102 ec2-user]# mkdir virginiagit
[root@ip-172-31-81-102 ec2-user]# ls
[root@ip-172-31-81-102 ec2-user]# cd virginiagit
[root@ip-172-31-81-102 virginiagit]# git init
[root@ip-172-31-81-102 virginiagit]# git remote add origin https://github.com/nayak22/Devops.git
[root@ip-172-31-81-102 virginiagit]# git pull origin master
[root@ip-172-31-81-102 virginiagit]# git log
[root@ip-172-31-81-102 virginiagit]# git show 462e4392ee121854d5542029fb7389943aec1fce
[root@ip-172-31-81-102 virginiagit]# cat >>mumbai1
#Adding the lines of code
print("Hello from Virginia Location")
[root@ip-172-31-81-102 virginiagit]# git status
[root@ip-172-31-81-102 virginiagit]# git add .
[root@ip-172-31-81-102 virginiagit]# git status
[root@ip-172-31-81-102 virginiagit]# git commit -m "First Commit from Virginia Region"
[root@ip-172-31-81-102 virginiagit]# git log
[root@ip-172-31-81-102 virginiagit]# git show 730c484409d339cefcf6c116f8d5bb783859eaaf
[root@ip-172-31-81-102 virginiagit]# git push origin master









Now connect back to Mumbai instance to validate if these changes are reflecting or not.
[ec2-user@ip-172-31-42-58 ~]$ sudo su
[root@ip-172-31-42-58 ec2-user]# cd mumbaigit
[root@ip-172-31-42-58 mumbaigit]# ls
[root@ip-172-31-42-58 mumbaigit]# git log
[root@ip-172-31-42-58 mumbaigit]# git show 730c484409d339cefcf6c116f8d5bb783859eaaf

Git Ignore demo
[root@ip-172-31-42-58 mumbaigit]# vi .gitignore
Press “I”
Type below:
*.java
*.css
Press “esc” key and type “:wq”
[root@ip-172-31-42-58 mumbaigit]# git status
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git status
[root@ip-172-31-42-58 mumbaigit]# git commit -m "adding the git ignore file"
[root@ip-172-31-42-58 mumbaigit]# touch file1.txt file2.txt file3.java file4.css file5.java
[root@ip-172-31-42-58 mumbaigit]# ls
[root@ip-172-31-42-58 mumbaigit]# git status
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git status
[root@ip-172-31-42-58 mumbaigit]# git commit -m "added some files and ignoring some"
[root@ip-172-31-42-58 mumbaigit]# git push origin master






Branching, merging, conflict demo
[root@ip-172-31-42-58 mumbaigit]# cat >CoflictDemoFile
This is line1 master branch
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git commit -m "conflict demo file from master"
[root@ip-172-31-42-58 mumbaigit]# git checkout branch1
[root@ip-172-31-42-58 mumbaigit]# cat >CoflictDemoFile
This is line1 from branch1 branch
[root@ip-172-31-42-58 mumbaigit]#
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git commit -m "conflict demo file from branch1"
[root@ip-172-31-42-58 mumbaigit]# git checkout master
[root@ip-172-31-42-58 mumbaigit]# git merge branch1
[root@ip-172-31-42-58 mumbaigit]# vi CoflictDemoFile
[root@ip-172-31-42-58 mumbaigit]# git status
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git commit -m "Resolving the conflict"
[root@ip-172-31-42-58 mumbaigit]# touch stashDemoFile
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git commit -m "stashDemoFile commit"
[root@ip-172-31-42-58 mumbaigit]# vi stashDemoFile
Write: First Enhancement 
Click “esc”
:wq
[root@ip-172-31-42-58 mumbaigit]# git stash
[root@ip-172-31-42-58 mumbaigit]# vi stashDemoFile
Write: Second Enhancement 
Click “esc”
:wq

[root@ip-172-31-42-58 mumbaigit]# git stash
[root@ip-172-31-42-58 mumbaigit]# git stash list
[root@ip-172-31-42-58 mumbaigit]# git stash apply stash@{1}
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git commit -m "first Enhancement to be pushed "
[root@ip-172-31-42-58 mumbaigit]# git stash apply stash@{0}
[root@ip-172-31-42-58 mumbaigit]# vi stashDemoFile
Resolved the Stash Conflict
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git commit -m "second enhancement "
[root@ip-172-31-42-58 mumbaigit]# git push origin master
[root@ip-172-31-42-58 mumbaigit]# git log –oneline

[root@ip-172-31-42-58 mumbaigit]# git stash clear
[root@ip-172-31-42-58 mumbaigit]# git stash  list
[root@ip-172-31-42-58 mumbaigit]# cat >ResetDemoFile
Will reverse the staging
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git status
[root@ip-172-31-42-58 mumbaigit]# git reset
[root@ip-172-31-42-58 mumbaigit]# git status











Git revert and tag
[root@ip-172-31-42-58 mumbaigit]# cat >>ReverstDemo
Reverstdemo file for demoing Revert in Git
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git commit -m "Commiting the to be reverted changes"
[root@ip-172-31-42-58 mumbaigit]# cat >>ReverstDemo
Adding more lines
[root@ip-172-31-42-58 mumbaigit]# git add .
[root@ip-172-31-42-58 mumbaigit]# git commit -m "Commiting the to be reverted change2"
[root@ip-172-31-42-58 mumbaigit]# git log –oneline
[root@ip-172-31-42-58 mumbaigit]# git revert 23e8937
Opens VI to edit message
[root@ip-172-31-42-58 mumbaigit]# git log –oneline

[root@ip-172-31-42-58 mumbaigit]# touch filex filey filez
[root@ip-172-31-42-58 mumbaigit]# git status
[root@ip-172-31-42-58 mumbaigit]# git clean  -n
Would remove filex
Would remove filey
Would remove filez
[root@ip-172-31-42-58 mumbaigit]# git clean  -f
Removing filex
Removing filey
Removing filez

[root@ip-172-31-42-58 mumbaigit]# git tag -a important -m "this is reverted version for dev pupose - cleanup " 7583af4
[root@ip-172-31-42-58 mumbaigit]# git tag
important
[root@ip-172-31-42-58 mumbaigit]# git show important
[root@ip-172-31-42-58 mumbaigit]# git tag -d important




