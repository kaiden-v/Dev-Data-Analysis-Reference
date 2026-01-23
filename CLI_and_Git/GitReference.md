
# 🌳 Git / GitHub

## Initialize / Start a Repository

`git init`                     : initialize a new Git repository in current folder  
`git remote add origin <url>`  : link local repo to remote GitHub repository  

## Clone an Existing Repository

`git clone <url>`              : clone a GitHub repository to local machine  

## Check Status and Changes

`git status`                   : show current changes  
`git diff`                     : show detailed differences not yet staged  

## Stage & Commit

`git add <file>`               : stage a file for commit  
`git add .`                     : stage all files for commit  
`git commit -m "<msg>"`        : commit staged changes  

## Push & Pull

`git push`                     : push local commits to remote  
`git pull`                     : pull latest changes from remote  

## Branching

`git branch`                   : list all branches (current branch has a *)  
`git branch <name>`            : create a new branch  
`git checkout <name>`          : switch to an existing branch  
`git checkout -b <name>`       : create and switch to a new branch  
`git merge <branch>`           : merge another branch into current branch (for personal work merge into main locally)  
`git push -u origin <branch>`  : first push of a new branch, creates remote branch (for group use; then create a pull request into main on GitHub)  

## Viewing History

`git log`                      : show commit history  
`git log --oneline`            : show condensed commit history  
`git log --graph --oneline --all` : show branch graph history  

## Retrieving Saved Commit

`git restore <file>`                      : restores content of a file to the latest commit (used when file contents deleted)  
`git checkout -b <new-branch> <commit>`   : create a new branch at a past commit to retrieve or continue work safely  
`git revert <commit>`                     : create a new commit that undoes the changes of a previous commit  
`git reset --hard <commit>`               : reset current branch to a past commit, discarding all changes after it  

## Removing Cache Files
`git rm -r --cached <file>`                     : remove file from being tracked by git  
`git rm -r --cached .`                     : remove all files listed in .gitignore file from being tracked by git  

