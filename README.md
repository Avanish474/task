# TASK 1

# Task Description

JOB#1
If Developer push to dev branch then Jenkins will fetch from dev and deploy on dev-docker environment.

JOB#2
If Developer push to master branch then Jenkins will fetch from master and deploy on master-docke environment.
both dev-docker and master-docker environment are on different docker containers.

JOB#3
Manually the QA team will check (test) for the website running in dev-docker environment. If it is running fine then Jenkins will merge the dev branch to master branch and trigger #job 2

# Prerequisite

1- LINUX command knowledge


2- Basics of Jenkins


3- Docker and some basic concepts of networking


4- Git and Github

# Step by Step Description of the TASK we are going to do

1- Make a file 



       mkdir /jenkinstask



Go inside this file and create a subfile


      cd /jenkinstask


      mkdir task



Now we go inside this file


      cd task


and now we do git clone to copy our github repsitory inside this file


     git clone https://github.com/Avanish474/task.git
  
  
This repository has prewritten code in it.We are are going to use git to tell you how we created this code.In Git terminal,do the following:


     mkdir task
  
  
    cd task
  
  
    git init
 
  
    cat >> index.html
  
    Welcome
  
    (control+D)
  
  
    git add index.html
  
  
    git commit -m "first commit"
  
  
Now go to github and crreate a repository without initializing it and now in the git terminal:
  
  
    git remote add origin  https://github.com/Avanish474/task.git
  
  
    git push -u origin master
  
  
Now we shift to dev branch by using the following command:
  
  
    git branch dev
  
  
    git checkout dev
  
  
    cat >> index.html
  
    This is me
   
    (control+D)
  
  
  
    git add index.html
  
  
    git commit -m "first commit"
  
  
    git push -u origin dev
  
  
So this were the steps involved in making the code.


Now back in the linux terminal we set the git credential to push to the repository without it asking us any username and password

     $ git config --global credential.helper store
     $ git push http://example.com/repo.git
     Username: <type your username>
     Password: <type your password>
   
   
Make a bash script to merge the master and dev branch which would help in doing the 3rd jenkins job.


     gedit mergebranch


    #!/bin/bash

    git merge dev
    git push -u origin master


Now we have to make make two storage files for production and testing code:

    mkdir /productionenv 

    mkdir /testingenv
  
  
 2-  First we create a job called Githubpullandownload  which will download the production code in the jenkins workspace and store it in /productionenv
 
 
 3-Then we create a job called Jenkinspullfromdev which will download the testing code in the jenkins workspace and store it in /testingenv
 
 
 4- Our final task is to check whether code from testingenv is opening the website or not and if it is opening the website we'll merge the two codes and trigger the job Githubpullanddownload
  
 





  
  
  
  
  
