# Git Commands and Explanation #

# Part 1:  Git Basics
## Task 1: Install and Configure Git
**1.Install Git from [git-scm.com](https://git-scm.com/).**

**2.Configure your global Git settings:**
```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```
- This sets your global Git username and email address.

**3.Verify the configuration:**
```bash
git config --list
```
- This command show the username and email which is set to your account
## Task 2: Initialize a Git Repository
**1.Create a directory and initialize it as a Git repository:**
```bash
mkdir MyProject
cd MyProject
git init
```
- This creates a new directory called `MyProject`, navigates into it, and initializes a new Git

# Part 2: Basic Workflow
## Task 3: Creating and Committing Files
**1.Create a new file:**
```bash
echo "Hello Git" > file1.txt
```
- This command is used to create a new file called `file1.txt` with the content "Hello Git"

**2.Stage and commit the file:**
```bash
git add file1.txt
git commit -m "Initial commit: Added file1.txt"
```
- This command add file  to staging area and commit with a meaningful message

## Task 4: Viewing Changes
**1.Modify the file:**
```bash
echo "Git is awesome!" >> file1.txt
```
- This command is used to modify the content of `file1.txt` at the end  `Git is awesome`.

**2.Check file status and differences:**
```bash
git status
git diff
```
- `git status`=this command is used to check the status of the file in the staging area and the repository
- `git diff`=this command is used to check the difference between the content or what changes between two commits
## Task 5: Undoing Changes
**1.Unstage a staged file:**
```bash
git reset file1.txt
```
- The command git reset file1.txt is used to unstage changes made to file1.txt that were previously added to the staging area with git add.

**2.Discard uncommitted changes:**
```bash
git checkout -- file1.txt
```
- This command  If you've made changes to file1.txt but have not staged or committed them yet.
You want to undo your changes and return the file to its previous version from the last commit.
# Part 3: Branching and Merging
## Task 6: Branch Management
**1.Create a branch and switch to it:**
```bash
git checkout -b feature-branch
``` 
- This command is used to create a new branch called `feature-branch` and switch to it.

**2.List branches:**
```bash
git branch
```
- This command is used to list all the branches in the repository.

**3.Rename a branch:**
```bash
git branch -m <old-branch-name> <new-branch-name>
```
- This command is used to rename a branch.
## Task 7: Merging Branches
**1.Merge feature-enhanced into main:**
```bash
git checkout main
git merge feature-enhanced
``` 
- `git checkout main`= This command is used to switch to the main branch.
- `git merge feature-enhanced`=
This command is used to merge the  `feature-enhanced` branch into the `main`
## Task 8: Handling Merge Conflicts
**1.Create two conflicting branches and resolve a conflict manually:**
```bash
git merge <branch-name>
```
- This command is used to merge the specified branch into the current branch.

**2.Uses**
```bash
git add <resolved-file>
git commit
```
# Part 4: Remote Repositories
## Task 9: Remote Setup
**1.Add a remote repository:**
```bash
git remote add origin https://github.com/your-username/repo.git
```
- This command Adds a new remote repository to your local.

**2.Verify the remote:**
```bash
git remote -v
```
- This command used to view the remote repositories associated with your local Git repository
- `-v`:This option stands for **"verbose"**, and it displays more information, specifically the URLs of the remotes for fetching and pushing.

## 10.Task 10: Push and Pull
**1.Push changes to the remote repository:**

```bash
git push -u origin main
```
- This command is used to push local commits to a remote repository.

**2.Pull changes from the remote:**
```bash
git pull origin main
```
- `git pull`: Fetches changes from a remote repository and merges them into your current branch.
- `origin` :Refers to the default remote repository (usually the one you cloned from).
- `main` : Specifies the branch you want to pull changes from.
## Task 11: Cloning a Repository
**1.Clone a remote repository:**
```bash
git clone https://github.com/your-username/repo.git
```
- This command is used to create a local copy of a remote repository.
# Part 5: Advanced Git
## Task 12: Stashing Changes
**1.Save uncommitted changes:**
```bash
git stash
```
- This command is used if you are not sure the content is wright or wrong then used stash it save the changes in stash area

**2.Apply stashed changes:**
```bash
git stash apply
```
- restores your changes to the working directory but does not commit them to the repository

**3.Drop the stash:**
```bash 
git stash drop
```
- The `git stash drop` command is used to delete a specific stash from your stash list. It removes the stash permanently

## Task 13: Tagging Commits
**1.Create and annotate a tag:**
```bash
git tag -a v1.0 -m "Version 1.0 release"
```
-  `git tag`=Creates tag for specific commit 
- `-a`=Create annotated tag named `v1.0`
- `-m "Version 1.0 release"`= Adds a message describing the purpose of the tag (like a commit message).

**2.Push the tag to the remote:**
```bash
git push origin v1.0
```
- `git push:` Uploads changes from the local repository to the remote repository.
- `git origin:` Specifies the remote repository (default remote name for GitHub or other services).
- `git v1.0:` Refers to the tag v1.0 that you want to push to the remote repository
## Task 14: Rewriting Commit History
**1.Use interactive rebase to modify commit messages:**
```bash
git rebase -i HEAD~3
```
- `git rebase`=This command is used to reapply commits on top of another branch or commit.
- `-i`=  interactively rewrite commit history. 
- `HEAD~3`=  The `HEAD~3` notation means "the last three commits

## Task 15: Cherry-Picking Commits
**1.Apply a specific commit to another branch:**
```bash
git cherry-pick <commit-hash>
```
-  This command is used to apply changes from a specific commit to your current branch

# Part 6: Collaboration
## Task 16: Forking and Pull Requests
**1.Fork a repository and clone it locally:**
```bash
git clone https://github.com/your-username/forked-repo.git
```
- This command is used to download a copy of the forked repository to your local machine

**2.Make changes and push them:**
```bash 
git checkout -b fix-typo
echo "Typo fixed" >> README.md
git commit -m "Fixed a typo"
git push origin fix-typo
```
- `git checkout -b fix-typo`: Creates a new branch named `fix-typo` and
- `git commit -m "Fixed a typo"`: Commits the changes with a meaningful message

- `git push origin fix-typo`: Pushes the changes to the remote repository

**3.Open a pull request on GitHub.**
- Go to the GitHub repository and click on the "New pull request" button
- Select the branch you want to merge into the main branch
- Add a title and description to the pull request
## Task 17: Simulating Team Collaboration
**1.Simulate a conflict by having two users modify the same file.**
- User 1: `git checkout master && echo "Conflict!" >> README.md && git commit
- User 2: `git checkout master && echo "Conflict!" >> README.md && git commit
- `git merge --no-commit --no-ff master`: Merge the changes from the `master
- `git status`: Check the status of the repository to see the conflict

**2.Practice resolving the conflict as a team.**
- `git add README.md`: Stage the file with the conflict
- `git merge --continue`: Continue the merge process
- `git commit`: Commit the resolved conflict
# Part 7: Ignoring Files

## Task 18: Using .gitignore

**1.Create a .gitignore file:**
```bash
echo "node_modules/" > .gitignore
git add .gitignore
git commit -m "Added .gitignore"
```
- This command is used to create a `.gitignore` file and add it to the repository

**2.Verify that ignored files are not staged:**
```bash
git status
```
- This command is used to check the status of the repository and see that the ignored files are not

# Part 8: Automation and Cleanup
## Task 19: Cleaning the Repository
**1.Remove untracked files:**
```bash
git clean -f
```
- This command is used to remove untracked files from the working directory

## Task 20: Aliases and Shortcuts
**1.Create an alias for frequently used commands:**
```bash
git config --global alias.st status
```
- This command create an alias shortcut instead for writing `git status` we can write `git st`
```bash
git config --global alias.cm commit
```
- This command create an alias shortcut instead for writing `git commmit` we can write `git cm`

**2.Use the alias:**
```bash
git st
```
- this show `git status`
```bash 
git cm -m "Message"
```
- this show `git commit`







































