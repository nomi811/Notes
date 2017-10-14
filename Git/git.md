# <a name="top">Git</a>


### [Basic Commands](#basic_commands)
### [Branches](#branches)
### [Moving Around](#moving)
### [Remotes](#remotes)

##### <a name="basic_commands">Basic Commands</a> :point_up:[top](#top)

`$git init` sets up a repository to be tracked by Git

`$git add .` adds all files to staging area

`$git add <filename>` adds the filename listed

`$git commit -am 'description of commit'` adds changes and commits to staging area. will not add new files or folders

`$git commit -m "message description"` adds message at the command line. If leave off it will take you to Vim to add the commit message.

`$git status` checks to see if everything is up to date or if changes have been made that haven't been committed yet.

`$git push` will push changes to GitHub. Only works with this simple version after setting it by using `$git push -u origin master`

`$git log` prints out a log of changes
    - `q` will quit and take you back to command prompt
    - `space bar` will page down

##### <a name="branches">Branches</a> :point_up:[top](#top)

`$git branch` view branches, `*` marks current branch

`$git branch <new_branch>` creates a new branch named "new_branch"

`$git checkout <branch_name>` switch to that branch name

`$git merge <branch_name>` merges the branch with master

`$git branch -d <branch_name>` deletes the branch from your Git project

##### <a name="moving">Moving Around</a> :point_up:[top](#top)

`$git reset HEAD <filename>` resets the file in the staging area to be the same as the HEAD commit. Does not discard from working directory, just removes from staging area.

`$git reset <SHA>` can use first 7 characters of so. Makes a new HEAD from that point.

`$git checkout HEAD <filename>` discards changes in the working directory

##### <a name="remotes">Remotes</a> :point_up:[top](#top)

`$git clone remote_location clone_name` "remote_location" tells Git where to find the remote web address or file path. Can click "clone button" on Git repository to add to clipboard and copy the url address. "clone_name" is the name you give to the directory in which Git will clone the repository.

`$git remote -v` to see a list of a Git project's remotes

`$git fetch` to see if changes have been made to the remote and bring those changes down to your local copy. Does not merge changes from remote into local reository. Brings changes onto a "remote branch"

`$git merge origin master` will merge the branches

`$git push origin <your_branch_name>` will push your branch up to the remote origin. From there it can be reviewed and then merged into the master branch.

`$git remote rm origin` removes origin

:point_up:[top](#top)
