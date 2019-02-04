# Git-Tutorial
A quick tutorial on git commands. Needs better organization, but I wrote this for myself as a reminder
since i switch from git to tfs to whatever, and I need this to remind me what side of the brain to use.

# Starting Fresh

### Navigate to your source and initialize the repo
```shell
cd /to/your/source/code
git init . 
```

### Once the repo is initialized
#### @see https://help.github.com/articles/adding-a-remote/
```
# adds everything from the current dir down to 
git add .       the repo

# Commit the changes locally
git commit -m "Initial commit”

# Send the changes to the remote if you havent already created the remote
# It's easier to create the remote via github.com, then pull the repo locally

git clone https://github.com/your_github_user_name/your_project_repo.git

# But if you haven't then you can push changes like this:
git remote add origin https://yourusername@github.com/your_github_user_name/your_project_repo.git   
```

### Setup the reference to the remote repo (if you've already done that then...)
```
# you should be on master, but use this to check
git status

# then push your changes to the remote repo on the master branch
git push remote master 

# and finally commit
git status----> master
git commit ->> commit my current of files edited on master
```

# Normal working flow when starting
```
# go to master branch
git checkout master

# pull the latest
git pull

# create a local branch to work from
git checkout -b newbranchname

# or, switch to your local branch if its already there
git checkout branchname

# Edit your files using your editor of choice
# if you have added new files, do:

git add .

# finally do: **note..this will not overwrite the file on master**
git commit -m "some commit message"
# do a git status just to confirm you're on your local branch
git status

# Merge your changes into master (locally)
# note... DO NOT "git rebase yourbranch"
git checkout master
git pull
git checkout yourbranch
git rebase master
git checkout master
git merge yourbranch

# if you need to merge manually, then do so. Remember, in a larger team,
# there may be code needed from both files to be merged. Don't assume your
# code is the only source

# if you dont need to merge manually, then:
git push
```
### checkout from GITHub
```
cd /to/your/local/dir/for/the/project
git clone username@hit:/path/to/repository
```
### Add files from current dir
```
git add *
git commit -m “Add Files” .
git push origin master
git remote add origin <server>
```
## Modifying Files
### Edit the file
### commit the changes (use . to catch all changes)
```
git commit -m ‘Some Message’ .  
git push origin master
```
### Push branch to remote

```
git checkout master
git pull
git checkout feature_branch_name
git rebase master
# edit files (add them if needed)
git add .
git commit -m "Some message" .
git push -u origin feature_branch_name
```
