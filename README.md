# common-git-commands
<br />  

### /*
###  created by Rahma Yasser
### */ 
<br />  

#### why git and github?
*1. to keep track of project snapshots. //git*  
*2. to coordinate work between members of the team remotely. //github* 
<br />  

### *Git basic commands*
>initializing git repo in your local directory:
```
git init 
```
>adding this file to staging area
```
git add <file_name>
```
>adding all modified files to staging area:
```
git add * OR git add -A OR git add . 
```
>removing file from staging area to the working directory:
```
git restore --staged <file_name> OR git reset HEAD <file_name> 
```
>to undo modification to a file, before you hit git add, you just modified the file and want to undo modification:
```
git restore <file_name> 
```
>to add a commit:
```
git commit -m "msg" 
```
>to show status of working directory:
```
git status 
```
>to show status of working directory in short form, m means modified file, ?? means untracked file:
```
git status -s
```
>to see all commits done:
>git log has a lot of args that you can use to see specific commits you made, refer to this for more info 
 https://devhints.io/git-log 
```
git log
```

>to show difference between modified files, if this command isn't working properly refer to this
> https://stackoverflow.com/questions/8544211/git-diff-doesnt-give-any-output
```
git diff 
```
> to show files in staging area:
```
git diff --staged
```
>list files in the working directory:
```
git ls-files 
```
<br />  

### *Configuration*
*The following commands are about specifying git configuration settings* 
 
 
>to show the config list of your git, like email and username, etc:
```
git config --list
```
>example, to set any of config list attributes like username:
```
git config --global user.name "RahmaYasser"
```
<br />  

### *Removing files and directories*
>to remove file only from git:
```
git rm --cached <file_name>
```
>to remove file from git and from working directory:
```
git rm -f <file_name>
```
>to remove directory only from git:
```
git rm -r --cached <dir_name>
```
>to remove directory from git and working directory:
```
git rm -rf  <dir_name> 
```
<br />  

### *Moving and renaming files*
>moving the file to the directory:
```
git mv <file_name> <directory_name>
```
> renaming a file:
```
git mv <old_file_name> <new_file_name>
```
<br />  

### *Tags*
*Git has the ability to tag specific points in a repository’s history as being important. Typically, 
people use this functionality to mark release points (v1.0, v2.0 and so on).*<br />  
*2 types of tags:*  
*1- annotated: contains a message about tag, the tagger name, email, and date.*  
*2- lightweight: keeps only the tag name to the specified version of the project.*  
>creating annotated tag:
```
git tag -a <tag_name> -m "msg"
```
>creating lightweight tag:
```
git tag <tag_name>
```
> listing all tags:
```
git tag
```
>showing specific tag
```
git show <tag_name>
```
>for deleting a tag
```
git tag -d <tag_name>
```
<br />  

### *Branches*
>for creating new branch:
```
git branch <branch_name>
```
>switching to a branch:
```
git checkout <branch_name>
```
>listing all branches:
```
git branch
```
>to create a new branch and switch to it, equals (git branch <branch_name> + git checkout <branch_name>):
```
git checkout -b <branch_name>
```
>to merge <branch_name> to the current branch:
```
git merge <branch_name>
```
>to delete a branch:
```
git branch -d <branch_name>
```
<br />  

### *Aliasing*
*Giving a command an alias name means to rename a command with short or easier name you choose,  example: to rename 'git remote' command with 'git rmt'*
 
```
git config --global alias.<alias_name> <actual_command>
```
>example: git config --global alias.rmt remote
<br />  

### *Stash*
*stash is a place where you put tracked files that you want to hide inside a stash(box) away from the working directory, you don't want them to be tracked or commited for now*
 
>putting files into stash:
```
git stash 
```
>adding a message while creating a stash:
```
git stash save "msg"
```
>showing all stashes:
```
git stash list
```
>to remove files from stash back to staging area and delete the stash:
```
git stash pop
```
>to remove files in a specific stash back to staging area and delete the stash:
```
git stash pop stash@{id}
```
>to remove files in a stash but keeps the stash:
```
git stash apply
```
>to remove files in a specific stash but keeps the stash:
```
git stash apply stash@{id}
```
>to show which files inside a stash:
```
git stash show stash@{id}
```
>delete the last stash, and deletes the files inside it:
```
git stash drop
```
>delete a specific stash and the files inside it:
```
git stash drop stash@{id}
```
>delete all stashes with files inside them:
```
git stash clear
```
<br />  

### *Dealing with github*
*note: origin is an alias to the url of github rebo*
```
git remote add origin <github_repo_url>
```
>to show the remote server:
```
git remote
```
>to show the url of the remote server(github repo):
```
git remote -v
```
>pushing to remote server, example `git push origin main`
```
git push <remote> <branch>
```
> to get the code from github repo, example `git pull origin master`
```
git pull <remote> <branch>
```
>to pull the code before pushing it:
```
git push -u <remote> <branch>
```
>to get a clone of the repo locally
```
git clone <github_repo_url>
```
<br />  



