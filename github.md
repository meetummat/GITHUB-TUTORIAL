# git is a version control systems 
* git helps you to maintain versions of a codebase.

/--------------------------------------------------------------------------------

# Centralized and Distributed version control system.

1. Centralised system - The whole code history is present on this server 
    * All the developer of a particular project contat to this server. 
    * If one of the coder's connection gets failed then he will not be able to contact to the server.

2. Distributed system - Made to solve the problem of centralised system. 
    * Git is a distributed version control system.
    * In this every developer has the copy of the project.
    * Every developer Push their changes to central/remote reposetory.

/--------------------------------------------------------------------------------

# Git/Github

1. Git :-
* Git is Fast, Reliable and Easy to use.
* Git also work ofline like in a flight you can comment and when you get internet you can push/pull that.
* Git tracks the changes in your code and converts the folders into reposetory and tracks through that.
* With git we can see the history of any reposetory.

2. Github :- 
* Github is a online platform where we host git reposetories.

# How to use git 
* there are mainly three ways - 
1. through Terminal or in git bash - old way.
2. through VS code 
3. through Github Desktop software.

/--------------------------------------------------------------------------------

# Using git:- 

    * Big 4 commands - git init, git    status, git add, git commit -m     "Message".  

* Commands in git:- 
    1. git init - to initialze folder in a git.
    2. git status - to check the status of the reposetory.

    3. git config --global user.name "Meet" 
    4. git config --global user.email "meetummat@gmail.com" - if we commit or push some changes in repo then it tell everyone that these changes commit by Meet whose email is this.

    5. git add index.html - moved index.html from working directory to staging area.
    * we can also add many files with one git add command like "git add index.html style.css.

    6. git commit -m "Message" - now we have commited files with the message, we can come back to this step from any step because of commiting this stage. 
    * we use "git commit with -m and with any message.

    7. git log - to see the whole commits, this will show who commited that and also date and time.

# 4 main locations where code is present when we use git
1. Working Directory -
    * Once we run "git clone" or "git init" then we will have git reposetory in working directory.
    * If we do some changes in our reposetory then still we will have that reposetory in working directory.

2. Staging Area - 
    * We move reposetory to Staging area by using "git add".
    * In staging file are present to be saved as a commit in reposetory.

3. Local Reposetory - 
    * Then we commit those files with message with the "git commit".

4. Remote Reposetory - 
    * Then if we want to share those changes with team we push those to a remote location using "git push".
    * if other members of team had made changes then we use "git pull" to access those files in our device.

*  with using git commands we can move our file from one direction to other.
* "git status" shows that in which stage which file is present.

/--------------------------------------------------------------------------------