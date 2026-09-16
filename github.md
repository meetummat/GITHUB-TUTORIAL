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

* Big 4 commands - git init, git status, git add, git commit -m "Message".

* After modifying we have to add and commit it.

* Commands in git:- 
    1. git init - to initialze folder in a git.
    2. git status - to check the status of the reposetory.
    3. git diff - it spacifies what changes we have made and in which file we have made the changes.

    4. git config --global user.name "Meet" 
    5. git config --global user.email "meetummat@gmail.com" - if we commit or push some changes in repo then it tell everyone that these changes commit by Meet whose email is this.

    6. git add index.html - moved index.html from working directory to staging area.
    * we can also add many files with one git add command like "git add index.html style.css.
    * git add . - we can add all the files in staging area with just "git add ." command.

    7. git commit -m "Message" - now we have commited files with the message, we can come back to this step from any step because of commiting this stage. 
    * we use "git commit with -m and with any message.

    8. git log - to see the whole commits, this will show who commited that and also date and time.

    9. git log --oneline - it will show one commit in one line not unecessary. Latest commit will come with (Head --> main), it may open in a pager if there are many commits then press "q" to close the log and return to terminal.
    * with "git log --oneline -5 will show last 5 commits.

    10. git restore --staged filename - with this command we can move file back to working directory from staging area.

    11. .gitignore - If we want to not commit some file or folder then we have to make a file named ".gitignore" and write that file name or folder name in it and then git will ignore that file, that file will not be pushed.

    12. .gitkeep :-
    * git does not track the empty folders or empty     directories.
    * If we want git to track that folders then we can a file   in that folders named ".gitkeep".

    13. git branch branchname - this lets you make a new branch.

    14. git branch - list all the branches within a repo, and tell that on which branch you are working on.

    15. git switch branchname - this will switch to the other branch from main branch.

    16. git merge branchname - After switching to main branch and using this command and then ":wq" we can merge branch to main branch. 

    17. git branch -d branchname - to delete the ulternate branch.

    18. git switch -c branchname - it will make a new branch as well as switch to that branch, basically it is combination of "git branch branchname" and "git switch branchname".

    19. git stash - it will move modified file to stash. 

    20. git stash list - it will list the stash.

    21. git stash pop - gets back all the changes we did in files before moving them to stash.

    22. git stash apply - with this previous changes will remain and stash and also comes back to use as it was before stashing.

    23. git tag -a v1.0.0 -m "Message" - to make an annoteted tag.

    24. git tag v1.0 - to make a lightweight tag

    25. git tag - to list all the tags.

    26. git rebase branchname - to use rebase in any branch, mainly used with merge.

    27. git clone repo link - we can clone GitHub repo in git bash using link of HTTPS, SSH, GITHUB CLI. 

    28. git remote -v - it shows to which remote repo of github your local git repo is connected to. 
    * It gives the name of remote repo as "origin".

    29. git push origin main - pushes commits to github, origin is the name of remote repo and main the branch name where we sending commits to.

    30. git branch -M branchname - with this we can change the name of the branch we are working on. 

    31. git config --global init.defaultBranch main - After this git bash will name every dafault branch as "main" like github.

    32. git pull - to pull the files from github to git bash in our own local setup.
    * All the commits will come in out main branch done by every person on that repo on github.
    * git pull pulls the changes from github and merge that changes to working directory or main repo on git. 

    33. git fetch - also to pull the files from github but it does not merge that to working directory or puts that file in local repo.


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

# Branching in Github :-

* To use other branch instead of main branch then we can copy the components of main branch to other branch and then we can merge that to main branch and delete that other branch.

* Any changes we do within alternate branch after switching from main, if we again switch to main branch the main branch will remain as it was.

* And we can merge the other branch changes in the main branch by switching to main branch and then using merge command then ":wq"

* After that if we dont need the other branch anymore then we can delete that branch by "git branch -d branchname".

* While doing the work in alternate branch if anyone make any commits in the main branch then if we merge them, git will merge the commits as per the timeline like commit of other branch then commit of main branch then commit other branch not like all commits of main branch together and other branch together.

# Best practice of Braching :-
1. One feature = One branch --> Create a dedicated branch for each feature, bug fix, and improvement. 

2. Never develop directly on main --> Protect the main branch and keep it simple. All changes should go through pull request.

3. Delete merges branches - Once a branch is merged, delete it to keep the repo clean.

4. Use meaningful branch names --> Use clear, descriptive names that indicate ther purpose of the branch. 

5. Keep branches short-lived --> Merge your changes as soon as possible to reduce risk and conflicts.

    * Good branching habits lead to a cleaner history, fewer conflicts, and a healthier codebase.

# Merge Conflict :-
* when two different person modify the same file then we try to merge them the conflict occur.

* If conflict happens then git will mark whats the changes of main branch and the other branch then we have resolve that by ourselves what we want to keep in that file and then add and commit.

/------------------------------------------------------------------------------------------------------------------------

# Stashing in Git :-

* When we are working on something and then we have do other changes while this is not completed then we can use stash

* We can store the changes in stash temp. and then we can work on other changes after that we can go to that changes again using stash.

/------------------------------------------------------------------------------------------------------------------------

# Tagging in git :-
* Tags in git are used to make a mark on commits, or to mark releases.

* Two types of tags in git :-
1. Annoteted tag --> Stores metadata (tagger, date, message)
    * More info and secure (can be GPG signed)
    * Recommended for releases.
    * "git tag -a v1.0.0 -m "Release version 1.0.0"

2. Lightweight tag --> just a pointer to a commit 
    * No extra metadata 
    * Best for temporary or private use.
    * "git tag v1.0"

/------------------------------------------------------------------------------------------------------------------------

# Git Rebase :-

* We use rebase to avoid so many merge commits in a git.
* We know that if we are working on two separate branches then git will track the commits as per timeline if we merge them like which commit happened first comes first,
* like we made commit in other branch then made the commit in main branch then we have to use "git rebase main' in the other branch and then to switch to main and merge then we will see that other branch's commit comes after the main branch's commit even if we made it before the main branch's commit.

/------------------------------------------------------------------------------------------------------------------------

# Using GitHub to Host our Reposetories :-

* We use github to host reposetories.
* readme.md is a markdown file for our repo on github so write it carefully everytime.
* gitignore option - we can use this file and select which tech's gitignore file we want to make and git will make and give that file.
* with git pull we can fetch all the files from the repo of github to out local repo.

/------------------------------------------------------------------------------------------------------------------------

# Using Github Desktop :-
* We can connect vs code with the Github and can easily make changes, stage unstage and commit through it in the github desktop.

* Public repo and Private repo - If anyone tries to open the public repo in incognito then it will open but, private repo will not open.

* We can also make new branches easily and when we try to merge those branch in the main branch then then we have to preview pull request.
* Pull request - it is a req that we want to merge other branch to main branch, if someone changes in our repo then he will create a pull req then we have to see and merge that changes if we want in our mian repo.

* We can also do rebasing in github desktop.

* If we click on fetch origin then if someone has made the changes then those will be pulled.

* History feature shows all the commits we have made throughout.

# Forking :- 

* If we want to make any meaningful changes in the repo which are already present on github, then we can fork that repo and then in the github desktop we can clone that repo and can make commits and changes and then we can create pull request so that if owner of that repo thinks this changes is meaningful he can merge those changes into original repo.

* If we had made some meaningfull changes then we have to go to Pull request option on github and from there we can create new pull request and then can send req to owner of that repo.

/------------------------------------------------------------------------------------------------------------------------

# Using git in vs code :-

* We can commit push pull through vs code only.

* We can make new branch and all by clicking on the branchname below on the screen.

* M means the file is modified.
* U meand the file is untracked.
* By clicking on git icon and then "+" then we can stage that file and then can commit.

* Always use commit in present tense - not added filed but use add files.

* then is we click sync changes then it will push the changes to github.

* With "git graph" extecsion we can see the graph of branches and commits, in the vs code.

* After that if merge conflict happens then it shows that in which file it happened and also gives the option that what changed you want to accept current or upcoming or we can edit file ourselves.
* And then stage and continue.

* If 2 or more person working on a same project then with the collaborator option we can collaborate with them.
* And if we want to assign work then we can create issue and assign issue to them and check their work.

* Then they will create pull request after working and we can preview that req and merge to main branch.

* And we can commment in the issues and then when its done we can close the issue, with merging the pull req.

/------------------------------------------------------------------------------------------------------------------------

# Modern git workflow:- 

* We can use AI within github to write commits for us, with the star button in the commit message box.

* Also we can make another branch where we have worked with AI and the main branch where we have worked ourselves then which work is good commit and use that.

/------------------------------------------------------------------------------------------------------------------------

# Conclusion :-
* Git is best tool to manage the codebase.

* Always use present tense in commit messages, and commit messages should be meaningful.

* Make branches for every feature and for short time work merge and delete it.

* Put secrets and passwords in .env file and put in .gitignore and dont push .env on github.

* Always review the code before commit.

/------------------------------------------------------------------------------------------------------------------------
