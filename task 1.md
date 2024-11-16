# Git Commands and Explanation #

## Part 1: Introduction to Version Control and Git
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
- This command create a new file. but if the file is already exist  whatever you writ ein " " will be replaced by original content it means it delet the original content and replace it with new one.

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

