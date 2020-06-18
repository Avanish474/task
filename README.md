# TASK 1

#Task Description

JOB#1
If Developer push to dev branch then Jenkins will fetch from dev and deploy on dev-docker environment.

JOB#2
If Developer push to master branch then Jenkins will fetch from master and deploy on master-docke environment.
both dev-docker and master-docker environment are on different docker containers.

JOB#3
Manually the QA team will check (test) for the website running in dev-docker environment. If it is running fine then Jenkins will merge the dev branch to master branch and trigger #job 2

#Prerequisite

1- LINUX command knowledge
2- Basics of Jenkins
3- Docker and some basic concepts of networking
4- Git and Github

#Step by Step Description of the TASK we are going to do

1- Make a file 


mkdir /jenkinstask


Go inside this file and create a subfile


cd /jenkinstask


mkdir task


Now we go inside this file


cd task


and now we do git clone to copy our github repsitory inside this file


git clone https://github.com/Avanish474/task.git
