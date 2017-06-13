# GitCheatSheet
Very basic and necessary git command to geting started working with git and github
### Part 0 : Verifyig git installation

```
0.1    git --version          : if git installed, then it show the version, Otherwise you need to install it.
```

### Part 1 : Setting username and email 

First thing first you need to specify your name and your email , in which at every commit it declare who commit this . It's important to know this is nothing to do with your remote password like github or bitbucket accounts.
So First try these commands in order to find out if you already set these properties or not.
```
1.1     git config --global user.name     : return the global username 
1.2     git config --global user.email    : return the global email
```
If nothing returned , Then you need to specifiy global username and email by the following command  

```
1.3     git config --global user.name "Your Name" 
1.4     git config --global user.email You@YourMail.com 
```

This will set the global user.name and user.email , You can call 1.1 and 1.2 commands to see the result.
If you are a windows user , these changes is made in the following location: %USERPROFILE%\.gitconfig  

If you want to set the user name and email for specific git repo and not globally , then need to drop the --global parameter. This way your creadential will store in YourLocalGitRepo/.git/config file.

In case you have different identities and you don't want to have global identity then you can remove global identity with the following command in order to git force you in each repository set your identity.

```
1.5   git config --global --remove-section user.name
1.6   git config --global --remove-section user.email
```


### Part 2 : Creating git repository

```
2.1    git init  : it create new local git repository in current directory
2.2    git clone git@github.com:YourAccount/Repo.git : this will clone existing repsitory
```

### Part 3 : Local changes
```
3.1   git status                           : List which file staged, unstaged and untracked 

3.2   git add .                            : This will add all unstaged file to stage area
3.3   git add filename or Dirctory         : You can add a single file to the stage area
3.4   git add --all                        : Instead of adding file one by one, This command add the whole current directory to the stage area
3.5   git add -u                           : stage the updated (tracked) file only

3.6   git reset filename or directoyr      : Unstage the file that contain changes
3.7   git commit -m "Your Message"         : commit the staged snapshot 
```

### Part 4 : Update and Publish
```
4.1   git remote -v  / --verbose           : List all already configured remote
4.2   git remote add origin git@github.com:YourAccount/Repo.git           : Add new remote repo 
```
For updating remote repo
```
4.3   git remote set-url origin git@github.com:YourAccount/Repo.git     :This will update the url
```
### Part 5 : Branching

List the branches :
```
5.1  git branch                        : get local branches
5.2  git branch --all                  : get all local and remote branches
```

Creating local Branches :
```
5.3  git branch branch1                : Create local branch named branch1 from the last commit of the current branch.
5.4  git branch branch2 [starting point] : create a branch at a point other than the last commit of the current branch (also known as HEAD). A starting point could be any thing like revision sha 

5.5  git checkout branch1              : switch to branch1
```
Creating Remote Branch :
```
5.6  git push origin master:RemoteBranch1 : Create remote branch of master named RemoteBranch1.
5.7  git push --set-upstream origin remoteBranch2 : Create remote branch of local current branch.
```
5.8 is for the first time, After that on each branch you are , if the aproprieate remote branch exist , the git push command is enough.


renameing and removing the branchs :
```
5.9  git branch -m new_branch_name     : rename the current local branch, So that mean you need to checkout first then rename.
5.10  git branch -m target_branch   new_name    : rename the other local branch

5.11  git branch -d Branch1             : remove branch1 locally
5.12  git push origin --delete branch1  : remove branch1 on the origin
```

### Part 6 : Mergin
```
6.1 git merge branch1           : Merge branch1 to current branch
```
In some cases you may confilict , in these cases , you need to edit the files and fix the conflict manually , other wise you can abort the merge and get back to the previous state by the following command :
```
6.2 git merge --abort           : abort the merge and get back to the previous state.
```

### Part 7: Diff
```
7.1 git diff                    : this will show the unstaged changes of the current branch.
```
If a file is staged, but was modified after it was staged, git diff will show the differences between the current file and the staged version.

### Part 8: Pulling

The following command will fetch and then merge the changes automatically
```
8.1 git pull                  : retrieve changes from the remote repo to the curent local repo
8.2 git pull origin feature-A : retrieve changes from the remote feature-A branch to the current local repo
```
We can pulling manually
```
8.3 git fetch origin  : retrieve objects and update refs from origin
8.4 git merge origin/feature-A : actually perform the merge
```
