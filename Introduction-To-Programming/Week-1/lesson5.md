### Introduction To Version Control

Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later. Git is a popular version control system, and GitHub is a web-based platform that uses Git for version control and collaboration.

## Basics if Git
# Installing Git:

  - Windows: Download and install Git from [git-scm.com](https://git-scm.com/download/win).

  - Mac: Use Homebrew to install Git.

    brew install git

  - Linux: Use the package manager.

    sudo apt-get install git

# Configuration:

  - Set your username and email address, which will be associated with your commits.

    ```bash 
git config --global user.name "Your Name"
```

    ```bash 
git config --global user.email "your.email@example.com"
```

### Basic Git Commands
# Initializing a Repository:

  - Create a new Git repository.

    ```bash
git init
```

# Cloning a Repository:

  - Clone an existing repository from GitHub.

    ```bash
git clone https://github.com/username/repository.git
```

# Making Changes:

  - Check the status of your repository.

    ```bash
git status
```

  - Add changes to the staging area.

    ```bash 
git add filename
```

    ```bash
git add .
```

  - Commit changes to the repository.

    ```bash
git commit -m "Commit message"
```

# Viewing History:

  - View the commit history.

    ```bash
git log
```

# Branching and Merging:

  - Create a new branch.

    ```bash
git branch branch_name
```

  - Switch to a different branch.

    ```bash
git checkout branch_name
```

  - Merge changes from one branch into another.

    ```bash
git checkout main
```

    ```bash
git merge branch_name
```

# Working with Remote Repositories:

  - Add a remote repository.

    ``` bash
git remote add origin https://github.com/username/repository.git
```

  - Push changes to a remote repository.

    ```bash 
git push origin branch_name
```

  - Pull changes from a remote repository.

    ```bash
git pull origin branch_name
```

### Creating a Repository on GitHub:

  - Go to [GitHub](https://github.com) and sign in.

  - Click on the "New repository" button.

  - Fill in the repository name, description, and choose whether it should be public or private.

  - Click "Create repository".

# Connecting Local Repository to GitHub:

  - Follow the instructions provided after creating the repository to push your local repository to GitHub.

## Collaboration on GitHub
# Forking a Repository:

  - Forking creates a copy of a repository under your GitHub account.

  - Navigate to the repository you want to fork and click the "Fork" button.

# Creating Pull Requests:

  - Pull requests let you tell others about changes you've pushed to a repository.

  - Navigate to the original repository and click the "New pull request" button.

  - Compare your branch with the main branch and create the pull request.

### Practical Git and Github
## Setting Up a Repository:
Create a new directory and initialize it as a Git repository.

     ```bash
    mkdir my_project

     cd my_project

     git init
```

# Create a README file and add it to the repository.

     ```bash
     echo " My Project" > README.md

     git add README.md

     git commit -m "Add README"
```

## Pushing to GitHub:

**Create a repository on GitHub.**
**Connect your local repository to GitHub.**

    ```bash 
    git remote add origin https://github.com/yourusername/my_project.git

     git push -u origin main
```

## Collaboration:

# Create a new branch for a feature.

     ```bash
git checkout -b feature_branch
```

# Make changes, add, and commit.

     ```bash
echo "Some new feature" > feature.txt
```

## Assignments:
# Initialize a Git Repository:

   - Create a new directory and initialize it as a Git repository.

   - Create a new file, add it to the repository, and make your first commit.

# Clone a Repository:

   - Clone an existing repository from GitHub.

   - Make changes, commit them, and push the changes back to the repository.

# Branching and Merging:

   - Create a new branch in your repository.

   - Make changes in the new branch, commit them, and merge the branch back into the main branch.

# Collaborate on a Project:

   - Fork an existing repository on GitHub.

   - Make changes and create a pull request to the original repository.


