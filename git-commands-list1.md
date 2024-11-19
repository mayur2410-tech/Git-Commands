# Git Commands and Explanation #

# Part 1: Introduction to Version Control and Git
## Task 1: Install and Configure Git
**1.Configure Git with your username and email:**
```bash
git config --global user.name "Your Name"
```
- This command set your name Globally in Git account
```bash
git config --global user.email "your-email@example.com"
```
- This command set your Email Globally in Git account

**2.View your Git configuration:**
```bash
git config --list
```
- This command show the username and email which is set to your account
## Task 2: Initialize a Repository

 **1.Create a new project folder and navigate to it:**

 ```bash
 mkdir MyProject
 ```
 - This command create a new folder named MyProject

 ```bash
 cd MyProject
 ```
 - This command navigate to my project folder

**2.Initialize it as a Git repository:**
```bash
git init
```
- This command a hidden ```.git``` folder will appear in the directory, indicating it’s now under version control.

## Task 3: Create a File and Make Multiple Commits

**1.Create a new file and add content:**
```bash
echo "My First Project" > README.md
```
- This command create a new file. but if the file is already exist  whatever you write in " " will be replaced by original content it means it delet the original content and replace it with new one.

**2.Stage the file:**
```bash
git add README.md
```
- This command add the file to staging area

**3.Commit the file:**
```bash
git commit -m "Initial commit: Added README.md"
```
- This command commit the file with a meaningful message

**4.Make changes to the file:**
```bash
echo "Added a description" >> README.md
```
- This command also create a file if it not exisit.But if it exist then preserve the content and add new content at end

**5.Stage and commit the changes:**
```bash
git add README.md
git commit -m "Updated README with a description"
```
- This commands use when you edit the file and for pushing it on repository

## Task 4: Check Status and Log

**1.Check the repository’s current status**
```bash
git status
```
- This command show on which branch you are present
- Also show whether files are in staging area or not

**2.View commit history in detail:**
```bash
git log --oneline --graph --decorate
```
- This command are used to see commit history
 
  i.`git log`= this show all commit history

  ii.`--oneline` = this show all commits in one line

  ## Task 5: Create and Clone a Repository 

  **1.Create a repository on GitHub named `example-repo.`**
  
  **2.Clone it locally:**
  ```bash
  git clone http://codinggita.com/example-repo
  ```  
- This command is used to clone or copy file from repository to local 

## Task 6: Understanding the Git Workflow

1. **Create a workflow file:**
   ```bash
   echo "Workflow example" > workflow.md
   ```
   Creates a file `workflow.md` with the text "Workflow example."

2. **Stage the file:**
   ```bash
   git add workflow.md
   ```
   Adds `workflow.md` to the staging area.

3. **Commit the file:**
   ```bash
   git commit -m "Added workflow example"
   ```
   Saves the changes to the repository with a description.

---


# Part 2: Working with Repositories
## Task 7: Branching and Merging

**1.Create a new branch for a feature:**
```bash
git branch feature-login
git checkout feature-login
```
- The `git branch` command create a new branch `feature-login`
- The `git checkout` command switch to the create branch

**Or Use**
```bash
git checkout -b feature-login
```
- This command create a new branch and switch to it at the same time


**2.Add a new file and commit changes:**
```bash
echo "Login Page" > login.html
git add login.html
git commit -m "Added login page"
```
- `echo "Login Page" > login.html` = This command creates new file `login.html`
- `git add login.html` = This command add `login.html` to the staging area
- `git commit -m "Added login page"` = This command saves the changes to the repository

**3.Merge the feature branch into main:**
```bash
git checkout main
```
- This command switch to the `main` branch
```bash
git merge feature-login
```
- This command merge the `feature-login` branch into the `main` branch

## Task 8: Handling Merge Conflicts
**1.Create two branches:**
```bash
git branch branch-A
git branch branch-B
```
- The `git branch` command create two new branches `branch-A` and `branch-B`

**2.Modify the same line in README.md in both branches.**

**3.Merge branch-A into main:**
```bash
git checkout main
```
- This command switch to the `main` branch
```bash
git merge branch-A
```
- This command merge the `branch-A` branch into the `main` branch

**4.Attempt to merge branch-B into main (this will cause a conflict):**
```bash
git merge branch-B
```
- When you try to merge `branch-B` into `main`, Git detects that the same line in `README.md` has conflicting changes (made in both `branch-A`  and `branch-B`).

**5.Resolve the conflict manually in README.md, then:**
```bash
git add README.md
git commit -m "Resolved merge conflict between branch-A and branch-B"
```
- After resolve conflict manually , add and commit the changes to the repository

## Task 9: Renaming and Deleting Branches
**1.Rename a branch:**
```bash
git branch -m old-branch-name new-branch-name
``` 
- This command rename the `old-branch-name` to `new-branch-name`

**2.Delete a branch:**
```bash
git branch -d feature-login
```
- This command delete the `feature-login` branch

# Part 3: Advanced Git Operations
## Task 10: Using Git Stash

**1.Make changes to a file but don’t commit:**
```bash
echo "Temporary work" >> temp.md
```
- This command create an file `temp.md` with content `Temporary work`

**2.Stash the changes:**
```bash
git stash
```
- This command is used if you are not sure the content is wright or wrong then used stash it save the changes in stash area

**3.View stashed changes:**
```bash
git stash list
```
- This command view the list of stash area

**4.Apply the stashed changes:**
```bash
git stash apply
```
- ``git stash apply ``restores your changes to the working directory but does not commit them to the repository

**5.Drop the stash after applying:**
```bash
git stash drop
```
- The `git stash drop` command is used to delete a specific stash from your stash list. It removes the stash permanently,
## Task 11: Rewriting History with Interactive Rebase
**1.Create multiple commits:**
```bash
echo "Commit 1" > file1.txt && git add file1.txt && git commit -m "Commit 1"
echo "Commit 2" > file2.txt && git add file2.txt && git commit -m "Commit 2"
echo "Commit 3" > file3.txt && git add file3.txt && git commit -m "Commit 3"
```
- This commands create,add,commit at once time in one line and `&&`use if previous one is succed then the next will be executed

**2.Squash commits into one:**
```bash
git rebase -i HEAD~3
```
- `git rebase`=This command is used to reapply commits on top of another branch or commit.
- `-i`=  interactively rewrite commit history. 
- `HEAD~3`=  The `HEAD~3` notation means "the last three commits
## Task 12: Cherry-Picking Commits
**1.Create a new branch:**
```bash
git checkout -b cherry-pick-example
```
- This command create a new branch named `cherry-pick-example`and also switch to it

**2.Cherry-pick a specific commit from another branch**
```bash
git cherry-pick <commit-hash>
   ```
- This command is used to apply changes from a specific commit to your current branch
## Task 13: Tagging Commits
**1.Tag the current commit:**
```bash
git tag -a v1.0 -m "Version 1.0 release"
```
- `git tag`=Creates tag for specific commit 
- `-a`=Create annotated tag named `v1.0`
- `-m "Version 1.0 release"`= Adds a message describing the purpose of the tag (like a commit message).

**2.Push the tag to the remote repository:**
```bash
git push origin v1.0
```
- `git push:` Uploads changes from the local repository to the remote repository.
- `git origin:` Specifies the remote repository (default remote name for GitHub or other services).
- `git v1.0:` Refers to the tag v1.0 that you want to push to the remote repository
## Task 14: Working with Remote Repositories
**1.Add a remote repository:**
```bash
git remote add origin <repository-url>
```
- This command is used to connet our local repositor to remote repository

**2.Push your changes to the remote repository:**
```bash
git push origin main
```
- This command is used to upload your changes to the remote repository
## Task 15: Forking and Contributing
**1.Fork a repository on GitHub.**
**2.Clone the fork locally:**
```bash
git clone <forked-repo-url>
```
- This command is used to download a copy of the forked repository to your local machine

**3.Create a new branch, make changes, and push:**
```bash
git checkout -b fix-typo
echo "Typo fixed" >> README.md
git add README.md
git commit -m "Fixed a typo"
git push origin fix-typo
```
- This command is used to create a new branch, make changes, and push them to the remote repository

**4.Open a pull request on GitHub.**
# Part 4: Additional Practice
## 16: Simulate Team Collaboration
**1.Create a repository and share it with a friend.**

**2.Both make changes to the same file simultaneously.**

**3.Practice resolving merge conflicts and pushing changes.**
## Task 17: Git Ignore

**1.Create a .gitignore file:**
```bash
echo "node_modules/" > .gitignore
```
- This command create a file that specifies intentionally untracked files that Git should ignore.

**2.Add files and ensure ignored files are not staged:**
```bash
git add .
```
- This command add all files in the current directory to the staging area.











