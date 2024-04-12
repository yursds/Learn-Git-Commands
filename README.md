# How to start use git and github.

An explanation of git and github are in the following youtube link:
https://www.youtube.com/watch?v=l2yrJtwoC_E

After `git init` you can use `git reflog` or `git status` commands to see the logging and status changes in every step.
In general to init git and link to your github account:

    # creation of .git folder
    git init
    # add all files of current folder to the index
    git add .
    # describe your commit with a message (example "first commit")
    git commit -m "first commit"
    # creation of main/master branch with name "main"
    git branch -M main
    # link your local repostery to your remote github repostery, already created on github (example "https://github.com/yursds/git_initRepo.git")
    # default and typical name of local repostery is origin 
    git remote add origin https://github.com/yursds/git_initRepo.git
    # push "origin" to "main"
    git push -u origin main
