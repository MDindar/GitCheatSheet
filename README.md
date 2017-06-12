# GitCheatSheet
Very basic and necessary git command to geting started working with github
### Part 0 : Verifyig git installation

```
in cmd just try git --version, if git installed, then it show the version, Otherwise you need to install it.
```

### Part 1 : Setting username and email 

First thing first you need to specify your name and your email , in which at every commit it declare who commit this . It's important to know this is nothing to do with your remote password like github or bitbucket accounts.
So First try these commands in order to find out if you already set these properties or not.
```
1.1    $ git config --global user.name     : return the global username 
1.2    $ git config --global user.email    : return the global email
```
If nothing returned , Then you need to specifiy global username and email by the following command  

```
1.3    $ git config --global user.name "Your Name" 
1.4    $ git config --global user.email You@YourMail.com 
```

This will set the global user.name and user.email , You can call 1.1 and 1.2 commands to see the result.
If you are a windows user , these changes is made in the following location: %USERPROFILE%\.gitconfig  

If you want to set the user name and email for specific git repo and not globally , then need to drop the --global parameter. This way your creadential will store in YourLocalGitRepo/.git/config file.

In case you have different identities and you don't want to have global identity then you can remove global identity with the following command in order to git force you in each repository set your identity.

```
1.5  $ git config --global --remove-section user.name
1.6  $ git config --global --remove-section user.email
```


### Part 2 : Creating git repository

```
2.1   $ git init  : it create new local git repository in current directory
2.2   $ git clone https://github.com/YourAccount/YourGitRepo.git : this will clone existing repsitory
```

### Part 3 : Local changes
```
3.1  $ git status                           : List which file staged, unstaged and untracked 
3.2  $ git add .                            : This will add all unstaged file to stage area
3.3  $ git add filename or Dirctory         : You can add a single file to the stage area
3.4  $ git add --all                        : Instead of adding file one by one, This command add the whole current directory to the stage area
3.5  $ git add -u                           : stage the updated (tracked) file only .
3.6  $ git reset filename or directoyr      : Unstage the file that contain changes
3.7  $ git commit -m "Your Message"         : commit the staged snapshot 
```

### Part 4 : Update and Publish
```
4.1  $ git remote -v  Or --verbose           : List all already configured remote
4.2  $ git remote add <name> <url>           : Add new remote repository 
```    
for example : 
$ git remot add origin https://github.com/YourAccount/YourGitRepo.git  // https style
```
4.3  $ git remote set-url origin git@github.com:YourAccount/YourGitRepo.git // ssh style
                                             : this will update the url
```
### Part 5 : Brnaching

```
5.1 $ git branch                        : get local branches
5.2 $ git branch --all                  : get all local and remote branches
5.3 $ git branch branch1                : Create local branch named branch1
5.4 $ git branch -m new_branch_name     : rename the current local branch, So that mean you need to checkout first then rename.
5.5 $ git branch -m target_branch   new_name    : rename the other local branch
5.4 $ git checkout branch1              : switch to branch1
5.3 $ git branch -d Branch1             : remove branch1 locally
5.4 $ git push origin --delete branch1  : remove branch1 on the origin
```