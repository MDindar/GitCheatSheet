# GitCheatSheet
Very basic and necessary git command to geting started working with github
### Part 0 : Verifyig git installation

```
in cmd just try git --version, if git installed, then it show the version, Otherwise you need to install it.
```

### Part 1 : Setting username and email 
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

If you want to set the user name and email for specific git repo and not globally , then need to drop the --global parameter.


### Part 2 : Creating git repository

```
2.1   $ git init  : it create new local git repository in current directory
2.2   $ git clone https://github.com/YourAccount/YourGitRepo.git : this will clone existing repsitory
```

### Part 3 : Local changes
```
3.1  $ git status                           : List which file staged, unstaged and untracked 
3.2  $ git add .                            : This will add all unstaged file to stage area
3.3  $ git add SingleFile.txt               : You can add a single file to the stage area
```