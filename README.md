
# Common Git commands

## Created by: Rahma Yasser

### Sections
- [Why git and github?](https://github.com/RahmaYasser/common-git-commands#why-git-and-github)
- [Git basic commands](https://github.com/RahmaYasser/common-git-commands#git-basic-commands)
- [Configuration](https://github.com/RahmaYasser/common-git-commands#configuration)
- [Removing files and directories](https://github.com/RahmaYasser/common-git-commands#removing-files-and-directories)
- [Moving and Renaming files](https://github.com/RahmaYasser/common-git-commands#moving-and-renaming-files)
- [Tags](https://github.com/RahmaYasser/common-git-commands#tags)
- [Branches](https://github.com/RahmaYasser/common-git-commands#branches)
- [Aliasing](https://github.com/RahmaYasser/common-git-commands#aliasing)
- [Stash](https://github.com/RahmaYasser/common-git-commands#stash)
- [Rebase](https://github.com/RahmaYasser/common-git-commands#rebase)
- [Squash](https://github.com/RahmaYasser/common-git-commands#squash)
- [Dealing with GitHub](https://github.com/RahmaYasser/common-git-commands#dealing-with-github)
 ---

### *Why git and github?*
*1. To keep track of project snapshots. //git*  
*2. To coordinate work between members of the team remotely. //github* 

### *Git basic commands*
>Initializing git repo in your local directory:
```
git init 
```
>Adding this file to the staging area:
```
git add <file_name>
```
>Adding all modified files to the staging area:
```
git add * 
```
>or
```
git add -A
```
>or
```
git add .
```
>Removing file from staging area to the working directory:
```
git restore --staged <file_name> 
```
>or
```
git reset HEAD <file_name>
```
>To undo modification to a file, before you hit git add, you just modified the file and want to undo modification:
```
git restore <file_name> 
```
>To add a commit:
```
git commit -m "msg" 
```
>To show status of the working directory:
```
git status 
```
>To show status of the working directory in short form. In output, 'm' means modified file while '??' means untracked  file:
```
git status -s
```
>To see all commits done:
>git log has a lot of options that you can use to see specific commits you made, refer to this for more info 
 https://devhints.io/git-log 
```
git log
```

>To show difference between modified files, if this command isn't working properly refer to this
> https://stackoverflow.com/questions/8544211/git-diff-doesnt-give-any-output
```
git diff 
```
> To show files in staging area:
```
git diff --staged
```
>List files in the working directory:
```
git ls-files 
```
>Move the repository back to a previous commit, discarding any changes made after that commit, please refer to the fifth answer here before using this command:
>https://stackoverflow.com/questions/4114095/how-do-i-revert-a-git-repository-to-a-previous-commit 
```
git reset --hard <commit_id>
```

### *Configuration*
*The following commands are about specifying git configuration settings* 
 
 
>To show the config list of your git, like email and username, etc:
```
git config --list
```
>Example, to set any of config list attributes like username:
```
git config --global user.name "RahmaYasser"
```

### *Removing files and directories*
>To remove a file only from git:
```
git rm --cached <file_name>
```
>To remove a file from git and from working directory:
```
git rm -f <file_name>
```
>To remove a directory only from git:
```
git rm -r --cached <dir_name>
```
>To remove a directory from git and working directory:
```
git rm -rf  <dir_name> 
```

### *Moving and renaming files*
>Moving a file to a directory:
```
git mv <file_name> <directory_name>
```
> Renaming a file:
```
git mv <old_file_name> <new_file_name>
```

### *Tags*
*Git has the ability to tag specific points in a repository’s history as being important. Typically, people use this functionality to mark release points (v1.0, v2.0 and so on).*<br />  
*2 types of tags:*  
*1- annotated: contains a message about tag, the tagger name, email, and date.*  
*2- lightweight: keeps only the tag name to the specified version of the project.*  
>Creating annotated tag:
```
git tag -a <tag_name> -m "msg"
```
>Creating lightweight tag:
```
git tag <tag_name>
```
> Listing all tags:
```
git tag
```
>Showing specific tag
```
git show <tag_name>
```
>For deleting a tag
```
git tag -d <tag_name>
```

### *Branches*
>For creating new branch:
```
git branch <branch_name>
```
>Switching to a branch:
```
git checkout <branch_name>
```
>Listing all branches:
```
git branch
```
>To create a new branch and switch to it, equals (git branch <branch_name> + git checkout <branch_name>):
```
git checkout -b <branch_name>
```
>To merge <branch_name> to the current branch:
```
git merge <branch_name>
```
>To stop fast forward merging:
```
git merge --no-ff <branch_name>
```
Here are some diagrams illustrating the difference between fast forward and no fast forward:

![before_merging](https://user-images.githubusercontent.com/49435053/127746781-79410e4c-7139-4ecd-be12-98d6f71bb3ae.png)

![fast-forward2](https://user-images.githubusercontent.com/49435053/127747233-b83d98c9-ac09-4963-8469-0992ce42f303.png)

![no-ff-2](https://user-images.githubusercontent.com/49435053/127747305-275c319c-c606-4d5c-bb4f-0f5cfca0ca1d.png)

>To delete a branch:
```
git branch -d <branch_name>
```
>To pick a specific commit from a branch to the working branch, use the following command,
for more info please refer to this:
>https://www.atlassian.com/git/tutorials/cherry-pick
```
git cherry-pick <commit_reference>
```

### *Aliasing*
*Giving a command an alias name means to rename a command with shorter or easier name you choose,  example: to rename 'git remote' command with 'git rmt'*
 
```
git config --global alias.<alias_name> <actual_command>
```
>example: 
>git config --global alias.rmt remote

### *Stash*
*Stash is a place where you put tracked files that you want to hide inside a stash(box) away from the working directory, you don't want them to be tracked or commited for now*
 
>Putting files into stash:
```
git stash 
```
>Adding a message while creating a stash:
```
git stash save "msg"
```
>Showing all stashes:
```
git stash list
```
>To remove files from stash back to staging area and delete the stash:
```
git stash pop
```
>To remove files in a specific stash back to staging area and delete the stash:
```
git stash pop stash@{id}
```
>To remove files in a stash but keeps the stash:
```
git stash apply
```
>To remove files in a specific stash but keeps the stash:
```
git stash apply stash@{id}
```
>To show which files inside a stash:
```
git stash show stash@{id}
```
>Delete the last stash, and deletes the files inside it:
```
git stash drop
```
>Delete a specific stash and the files inside it:
```
git stash drop stash@{id}
```
>Delete all stashes with files inside them:
```
git stash clear
```

### *Rebase*
*The `git rebase` command allows you to easily change a series of commits, modifying the history of your repository. You can reorder, edit, or squash commits together.*
>To show a list of commits, `n` is the numer of commits to work on:
```
git rebase -i HEAD~{n}
```
![1](https://user-images.githubusercontent.com/48657780/126626468-1195bbde-b8c4-4286-83fb-1655982bf71d.jpg)


### *Squash*
*To combine two or more commits into a single commit, A commit is squashed into the commit above it:*

>Edit the summary shown to you by the rebase command, leaving the commit you want to be the main commit as "pick" and changing all subsequent "pick" commands as "squash" or "s"

![2](https://user-images.githubusercontent.com/48657780/126628354-fdbc4a92-5fd0-432f-a8cb-c8b4b3f3c9d8.jpg)

Write/quit the editor twice (the second screen would allow you to change the commit message)  <br>
At this point, your commits are squashed into one. 

![3](https://user-images.githubusercontent.com/48657780/126631425-f1a9a55e-b863-4e00-a0dd-6f287fc264df.jpg)

>Run the following command to force a push of the new, consolidated commit:
```
git push -f
```

### *Dealing with github*
*Note: origin is an alias to the url of github rebo*
```
git remote add origin <github_repo_url>
```
>To show the remote server:
```
git remote
```
>To show the url of the remote server(github repo):
```
git remote -v
```
>Pushing to remote server, example `git push origin main`
```
git push <remote> <branch>
```
> To get the code from github repo, example `git pull origin master`
```
git pull <remote> <branch>
```
>To pull the code before pushing it:
```
git push -u <remote> <branch>
```
>To force a push when git rejects your `git push` command, because you made changes that may overwrite the previous commits, you can refer to this for more info:
>https://git-scm.com/docs/git-push#:~:text=To%20force%20a%20push%20to,push%20to%20the%20master%20branch). 
```
git push -f
```
>To get a clone of the repo locally
```
git clone <github_repo_url>
```
You can download commits, branches from a remote repo into your local repo without merging them using fetch command. Unlike `git pull`, `git fetch` provides you the choice of merging the downloaded branches, but `git pull` do both operations, (download+merge).
>To fetch all of the branches from a repo
```
git fetch <repo>
```
>To fetch a particular branch from repo
```
git fetch <remote>  <branch>
```
>To sync your forked repository with the original repository(to pull the updated code from the original repository), you can do the following:

1. Make an alias for the original repository.
   ```
   git remote add originrepo <URL_of_the_original_repo>
   ```
   in this example I created an alias called 'originrepo' for the repository that I made a fork from.
   
2.  Use git fetch to download the changes from the original repository.
    ```
    git fetch originrepo
    ```
    note: this will add the  fetched code to your current branch, so make sure that you switch to the desired branch before using this command.
3. Use git merge to merge the fetched changes into your local code if there are no conflicts.
    ```
    git merge originrepo/main main
    ```
    here, I merged the fetched code into main branch in my forked repo, you can use any branch.
<br />  
