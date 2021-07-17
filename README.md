# common-git-commands
This is a cheatsheet of common git commands with simple explanation for every command. I hope it's useful.

###/*
### created by Rahma Yasser
###*/

why git and github?
1. to keep track of project snapshots. //git
2. to coordenate work between members of the team remotely. //github


git config --list //shows the config list of your git, like email and username.
git config --global user.name "RahmaYasser" // example, to set any of config list attributes 


git status // shows status of working directory
git status -s // shows status of working directory in short form, m means modefied file, ?? means untracked file


git init //initializing git repo in your local directory.
git add <file_name> //adding this file to staging area
git add * OR git add -A OR git add .  //adding all modefied files to staging area 
git restore --staged <file_name> OR git reset HEAD <file_name> //removing file from staging area to working directory
git restore <file_name> //undo modification to a file, before you hit git add, you just modefied the file and want to undo modification.
git commit -m "msg" 
git push remote local //example git push origin master, -u means to pull and then push
git pull remote local //example git pull origin master

git log //to see all commits done
git log // it has a lot of args that you can use to see specific commits you done, refer to this for more info 
// https://devhints.io/git-log 


git diff //shows difference between modefied files, 
git diff --staged //shows files in staging area
//if this command isn't working properly refer to this https://stackoverflow.com/questions/8544211/git-diff-doesnt-give-any-output


git ls-files //list files in the working dir
git rm --cached <file_name> //to remove file from git only
git rm -f <file_name> //to remove file from git and from working dir
git rm -r --cached <dir_name> // remove dir from git only
git rm -rf  <dir_name> //remove dir from git and working dir


Git has the ability to tag specific points in a repository’s history as being important. Typically, 
people use this functionality to mark release points (v1.0, v2.0 and so on).
2 types of tags: 
1- annotated: contains a message about tag, the tagger name, email, and date 
2- lightweight: keeps only the tag name to the specified version of the project
git tag -a <tag_name> -m "msg" // creating annotated tag 
git tag <tag_name> // creating lightweight tag 
git tag // listing all tags
git show <tag_name> //showing specific tag
git delete --delete <tag_name> // for deleting a tag


//origin is an alias to the url of github rebo
git remote add origin <github_repo_url>
git remote
git remote -v
git push -u origin main //pushing to remote server
git clone <github_repo_url> //to get a clone of the repo locally



git branch <branch_name> //for creating new branch
git checkout <branch_name> //switching to branch
git branch // listing all branches
git checkout -b <branch_name> // equals (git branch <branch_name> + git checkout <branch_name>), create new branch and switch to it
git merge <branch_name> //to merge <branch_name> to the current branch
git branch -d <branch_name> //to delete a branch


//for aliasing, renaming commands, example, rename 'git remote' command with 'git rmt' 
git config --global alias.<alias_name> <actual_command>
git mv <old_file_name> <new_file_name> //renaming file 


stash // stash is a place where you put tracked files that you want to hide inside a stash away from the working directory, you don't want them to be commited for now 
git stash // putting files into stash
git stash save "msg" // to add message while creating a stash
git stash list //showing all stashes
git stash pop // remove files from stash back to staging area and delete the stash 
git stash pop stash@{id} //to remove files in specific stash and delete the stash
git stash apply // remove files in stash but keeps the stash
git stash apply stash@{id} // remove files in a specific stash but keeps the stash
git stash show stash@{id} // show what files inside stash
git stash drop // delete the last stash, and deletes the files inside it
git stash drop stash@{id} //delete a specific stash and the files inside it
git stash clear // delete all stashes with files inside them
