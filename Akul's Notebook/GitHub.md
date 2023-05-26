
**Description: Notes from *The Git & GitHub BootCamp on Udemy***

# <u>Git</u>
[Git Docs](https://git-scm.com/doc)

- common workflow: 
	- treat the master/main branch as the most stable build of an application.
	- no experiments on the master branch.
	- create a feature branch and then merge that feature branch back into the master branch.

## Section 4: Basic of Git: Adding and Committing
- Create a new file in Git Bash:
	```
	touch *file name*
	```
	- for example: if you want to create a new .py file by the name *Hello_World*:
		```
		touch Hello_World.py
		```
- To create a new folder:
	```
	mkdir *folder name*
	```
- Create a repository by using the command:
	```
	git init
	```
	- **NOTE: <u>DO NOT</u> create a repository inside a folder that is already a repository. Check if it is a repository using the command:**
		```
		git status
		```
	- This will create an invisible .git folder that will keep track of all the changes made.

- Phases of the entire workflow:
	1. <u>Working Directory:</u>
		- Editing the files in this stage. Making all the changes, etc.
		- Use this command to open the file in primary text editor (Visual Studio, in my case):
			```
			code .
			```
	2. <u>Staging Area:</u>
		- After the editing is completed, *add* the edited file(s) into staging area using the command *"git add"*. For example: you made changes in 7 (numbered 0-6) files but you want to create a single checkpoint for 3 (file numbers: 1, 4, and 6) out of the 7 files you made changes in.
			```
			git add file_1 file_6 file_4
			```
		- To add all the changes, use:
			```
			git add .
			```
	3. <u>Repository:</u>
		- A "commit message" needs to be given whenever a (group of) file(s) are being commited to the repository.
		- Use this command to commit:
			```
			git commit -m "message"
			```
		- Use this command to see all the commits in the repository:
			```
			git log
			```
		- sdsd


## Section 5: Commits in Detail
- A commit should encompass a single feature, change, or fix. Try and keep each commit focused on a single thing.
	- makes it easier to undo or rollback.
- Commits should have a present-tense imperative style, as if you are giving orders to the codebase to change its behavior.

- After configuring your default Git text editor, you can type in as long a message as you want. For longer messages, do not use this command:
	```
	git commit -m "message"
	
	# If you want to add all changed files and commit all at once:
	git commit -a -m "message"
	```
- instead, use this command (it will open the default Git text editor and you can add a lengthy commit message):
	```
	git commit
	```

- Amending commits: works only on the most recent commit, not on the commits made more than the recent commit ago.
	```
	git commit --amend
	```
	- This command will let you add any files you had forgotten and edit the commit message.

- To ignore tracking of a file, use this command to create a file that will store the names of all the files/folders that need to be stopped tracking:
	```
	touch .gitignore
	```
	- [This website](https://www.toptal.com/developers/gitignore) helps you determine what all to mention in the .gitignore file depending on what kind of a project you are working on.
	- Also refer to the [git docs](https://git-scm.com/docs/gitignore) for more formatting examples.


## Section 6: Working With Branches
- Branches allow you to create alternate timelines, which allows you to work on different things in the same code at the same time. Then you merge all the branches.
- *HEAD -> "branch"* points to the branch you are in right now.
- To view a list of all the branches, type this command:
	```
	git branch
	
	# for one-liner of the last commit in each branch:
	git branch -v
	```
- To create a new branch:
	```
	git branch <branch_name>
	```
- To switch branches:
	```
	git switch <branch_name>
	```
- To create a new branch and switch to it:
	```
	git switch -c <branch_name>
	```
- **NOTE: Always commit or stash any changes before switching branches.**
- To delete a branch:
```
# if it is an empty branch:
git branch -d <branch_name>

# to force a branch delete, in case you haven't merged it fully:
git branch -D <branch_name>
```


## Section 7: Merging Branches
- **<u>Fast-forward merge</u>:**
	- works only if the branch being merged into does not have any commits. If you try to merge into a branch that has any more commits after the branch2 was created, it'll show a "merge conflict" error
	```
	git switch <receiving_branch_name>
	git merge <branch_name>
	
	# for example: you want to merge a branch named "bugfix" into the the "master" branch:
	git switch master
	git merge bugfix
	```
- If the same line in a file is edited in two different branches and they are merged, it will show a conflict.
- Resolving conflicts:
	1. Open the file with merge conflicts.
	2. Edit the file(s) to remove the conflicts
	3. Remove the conflict "markers" in the document
	4. Add and commit!


## Section 8: Comparing Changes with Git Diff
- To look at all the changes made in the working directory:
	```
	# unstaged changes only:
	git diff
	
	# staged changes only:
	git diff -staged 
	# OR
	git diff -cached
	
	# staged and unstaged changes:
	git diff HEAD
	
	```
- To look at changes made in a specific file:
	```
	# staged and unstaged changes:
	git diff HEAD <file_name>
	
	staged changes only:
	git diff -staged <file_name>
	```
- To compare changes between two branches:
```
git diff <branch1>..<branch2>
```
- To compare changes between two commits:
	- use commit hash after "git diff"
```
git diff <commit1_hash>..<commit2_hash>
```


## Section 9: The Ins and Outs of Stashing
- When switching branches, Git will either
	1. throw an error, if there is a conflict; or
	2. you will carry the uncommited changes with you to the new branch you are switching to.
- Use this command to solve the problem of switching without having to commit:
	```
	git stash
	```
	- Saves your uncommited changes so you can come back to them.
- To remove the most recently stashed changes and re-apply them:
	```
	git stash pop
	```
- To apply the most recently stashed changes without removing them from stash:
	```
	git stash apply
	```
- To view all the stashes:
	```
	git stash list
	```


## Section 10: Undoing Changes & Time Travelling
- To travel back in time to a specific commit:
```
git checkout <commit_hash>

# Puts you in a detached HEAD state
```
- To go re-attach the head:
```
git switch <branch_name>
```
- To reference to commits relative to the position of the HEAD:
```
git checkout HEAD~1 # refers to the commit before the HEAD

git checkout HEAD~4 # refers to 4 commits before the HEAD
```
- To go to the file(s) back to whatever it looked like in your last commit:
```
git checkout HEAD <file1> <file2> <file3>
# OR
git checkout -- <file1> <file2> <file3>
# OR
git restore <file1> <file2> <file3>
```
-  To restore a file to an earlier commit:
```
# To reference a commit relative to the position of the HEAD
git restore --source HEAD~1 <file1> <file2> <file3>

# To reference a commit by their commit hash
git restore --source <commit_hash> <file1> <file2> <file3> 
```
- To unstage a file:
```
git restore --staged <file1> <file2> <file3>
```
- To remove commits:
```
git reset <commit_hash>
# This will remove all the commits after the commit that has been mentioned, but it will not undo the changes made in the files.
# Useful if you want to take a bunch of old changes and move them to a different branch, because it doesn't undo the changes and only removes the commits (moving all the changes back to the "Working Directory")

git revert <commit_hash>
# This will also do the same thing as git reset but it will not delete any commits. This is useful in case you are collaborating with others and using "git reset" might result into mismatched commit history.
```
- To remove the commits and the changes made:
```
git reset --hard <commit_hash>
```


# <u>GitHub</u>

## Section 11:  GitHub: The Basics
- To clone a repo:
```
git clone <url>
# NOTE: MAKE SURE YOU ARE NOT INSIDE A REPO
```
- Setting up an SSH Key allows you to be authenticated without having to write username and password every single time you ineract with GitHub from the command line.
- Creating a GitHub repo:
	- If you already have a Git on local machine:
		1. Create a new repo on GitHub
		2. Connect the local repo (add a remote)
		3. Push your changes to GitHub
	- Starting from scratch:
		1. Create a new repo on GitHub
		2. Clone that repo to local machine
		3. Do some work locally
		4. Push your changes to GitHub
- Remote:
	- To view all the remotes:
		```
		git remote -v
		```
	- To add a new remote:
		```
		git remote add <name> <url>
		```
- To push work on GitHub:
	```
	git push <remote> <branch>
	
	# To create an upstream, i.e. after running this command there's no need to write the entire command, you can just write "git push" and it will do the job. 
	git push -u <remote> <branch>
	```
- To push a branch to a different branch name in the remote:
	```
	git push <remote> <local-branch>:<remote-branch>
	```


## Section 12: Fetching & Pulling
- 