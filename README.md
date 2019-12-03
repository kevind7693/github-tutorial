# GitHub Tutorial

_by Kevin Dong_


## Git vs. GitHub
__Git__: Is a version control system that allows you to manage and keep track of your code and edits. Git runs on local (doesn't need internet access unless you're using an ide). **Can work without github.**   

  
__Github__: Is a cloud based service that allows you to "push" your git repositories onto it. It also allows collaboration between 2 or more users on a single project. **Relies on git.**


---
## Initial Setup
Steps to make your own github account:  
1. Go to this [link](https://github.com/)
2. Click sign up
3. Follow the directions 
  
Steps to steup your IDE:
1. Go to this [link](https://ide.cs50.io/)
2. Sign in with your github account 
3. Go to this [link](https://github.com/hstatsep/ide50//)
4. Follow all the directions exactly as it says

**Importance of SSH Key**:  
> Make sure you have a SSH key since it allows you to commit your changes without having you to enter your username and password everytime unlike HTTPS which ask for your password and username everytime you try to commit a new change.

---
## Repository Setup
Steps for setting up your first repository on your ide (local):
1. `mkdir <folder name>` create a directory first.
2. `cd` into the directory you wish to make into a repository 
3. Once in the directory, type in `git init`
4. If successful you said see next to the folders name on the command line `(master)` 
5. If haven't, create a file using `touch <file name>.txt`
6. `c9 <file name>` into the file 
7. Make some edits in that file
8. After you're finished, do `git add <file name>`
9. After you do `git add`, you do `git commit -m <your message>`
10. Lastly you do `git push` to send all your commits to your remote repo (github)


Steps for setting up your remote repository on github and connecting it to your local:
1. Login to your github account 
2. Click on the `+` icon near the top right of the site then click on "New repository"
3. Type in your new repository's name (**Make sure your new repository's name is excatly the same as the  repository on your local ide, the repo that you want push to and pull from**)
4. **Make sure your link is in the SSH key** 
5. After that, login to your local ide
6. `cd` into the repo you just created on the remote (same name)
7. Type in `git remote add origin git@github.com:<Your github account name>/<Your repository name>.git`
8. Lastly type in `git push -u origin master`





---
## Workflow & Commands
**Commands To Know For Your Workflow**:
* `git init`: turns a directory into a repository. (like hiring a photographer to help take pictures of you)
* `git add <file name>` : adds your most recant edits onto the "stage" so that its ready for commiting. (you moving around and changing in order to get the best picture for the photographer to take)
    * `git add .` : adds all the edits of all the files you've worked in that certain dircetory/repo onto the stage for commiting
* `git commit -m <your message>` : takes a screenshot of what you just added onto the stage. (Saving your most recant edits/photographer taking the picture) **Don't write your commit messages in the past tense and make it short and concise.**
* `git status` : gives you an overview of your most recant edits.
    * Red message = edits haven't been added onto the stage (not ready for commiting)
    * Green message = edits are ready for commiting 
    * No message = No recant edits/changes (everything is up to date)
* `git push` : sends your commits from your local repo to your remote repo. (ide to github)
* `mkdir <folder name>` : creates a directory/folder
* `cd <folder name>` : moves into that particular folder
    * `cd ..` : goes up one level (Goes to the parent directory of the directory you are currently in)
    * `cd ~` : goes to the root directory (The highest directory or the directory of all directories)
* `touch <files name>.txt` : creates a file 
* `c9 <files name>` : moves into that particular file  
 


What ongoing workflow looks like on git:
1. You `cd` into the repository where the file you wish to work on is in.
2. You `c9 <file name>` into the file you wish to work on.
3. You make your edits and changes on the file 
4. You `git add <file name>` so that its ready for commiting 
5. You `git commit -m <your message>`
6. You `git push` your commits onto your remote repo (usually github)
7. Repeat from step 3 until you're finished 




---
## Rolling Back Changes
**Undoing an edit** : Use `git checkout --<filename>` to undo any edits since your last commit  

**Undoing a `git add`** : Use `git reset HEAD <file name>` to undo any "adding" to the stage  

**Undoing a `git commit`** : Use `git reset --soft HEAD~1` to remove the last commit you just committed  
If you want to undo the last commit and the add you can do `git reset --hard HEAD~1`

**Undoing a `git push`** :
1. Use `git log` to get the "sha" of the commit you want to revert back to
2. Use `git revert <sha>` to get the form of your work that you want back
3. Use `git reset --hard` to match your local ide with the commit you just reverted back to 
4. Use `git push origin +master` to push the commit that you just reverted back to from your local to your remote