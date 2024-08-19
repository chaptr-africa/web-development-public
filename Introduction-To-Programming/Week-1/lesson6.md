### Advanced Git and Github
## Review of Basic Git and GitHub Concepts

- Quick recap of initializing a repository, cloning, basic commands (status, add, commit), viewing history, and basic branching and merging.

# Working with Branches

- Creating and Deleting Branches:

  - Create a new branch.

    ```bash
    git branch new_branch 
```   

  - Switch to the new branch.

    ```bash
    git checkout new_branch  
```  

  - Create and switch in one command.

    ```bash
    git checkout -b new_branch
```

- Delete a branch.

    ```bash
    git branch -d branch_name
```

- Merging Branches:

  - Merge a branch into the current branch

    ```bash
    git merge branch_name
```

  - Handle merge conflicts:

    - Open the conflicting files and resolve conflicts.

    - Add the resolved files.

    - Commit the merge.

Reverting and Resetting

- Revert a Commit:

  - Create a new commit that undoes changes

    ```bash
    git revert commit_id
```

- Reset to a Previous Commit:

  - Reset the current branch to a specific commit.

    ```bash
    git reset --hard commit_id
```

  - Soft reset (keeps changes in the working directory)

    ```bash
    git reset --soft commit_id
```

# Stashing Changes

- Stash Uncommitted Changes:

  - Save changes for later and revert to the last commit.

    ```bash
    git stash
```

  - List stashed changes.

  ```bash
    git stash list
```

  - Apply stashed changes.

    ```bash
    git stash apply
```

  - Apply and drop the stash.

    ```bash
    git stash pop
```

## Working with Remote Repositories

- Fetching and Pulling:

  - Fetch updates from the remote repository.

    ```bash
    git fetch
```    

  - Pull updates and merge with the local branch.

    ```bash
    git pull
```

- Pushing Changes:

  - Push changes to the remote repository.

    ```bash
    git push origin branch_name
```

# Working with Tags:

  - Create a tag.

    ```bash
    git tag -a v1.0 -m "Version 1.0"
```

  - Push tags to the remote repository.

    ```bash
    git push origin v1.0
```

## Collaborating on GitHub

- Issues and Pull Requests:

  - Issues:

    - Create an issue to track bugs, tasks, or enhancements.

    - Navigate to the Issues tab in a GitHub repository and click "New Issue".

    - Fill out the issue template and submit.

  - Pull Requests:

    - Ensure your branch is up to date with the main branch.

    - Push your branch to GitHub.

    - Navigate to the Pull Requests tab and click "New Pull Request".

    - Compare changes and create the pull request.

- Code Reviews:

  - Reviewing code in a pull request.

  - Adding comments and suggestions.

  - Approving or requesting changes.




## GitHub Actions

- Introduction to GitHub Actions:

  - Automate workflows directly in GitHub.

  - Common uses include CI/CD, code linting, testing, and deployment.




- Creating a Workflow:

  - Navigate to the Actions tab in your repository.

  - Choose a template or create your own workflow.

  - Example: Node.js CI.

   
```jsx
name: Node.js CI

    on: [push]

    jobs:

      build:

        runs-on: ubuntu-latest

        strategy:

          matrix:

            node-version: [12.x, 14.x, 16.x]
       steps:

        - uses: actions/checkout@v2

        - name: Use Node.js ${{ matrix.node-version }}

          uses: actions/setup-node@v2

          with:

            node-version: ${{ matrix.node-version }}

        - run: npm install

        - run: npm test
```
### Assignment
## Practical Exercise 1

- Branch Management:

  - Create a new branch, make changes, and merge it back into the main branch.

  - Handle a merge conflict and resolve it.

- Revert and Reset:

  - Make a few commits, then revert one of them.

  - Reset your branch to a previous commit and explain the differences between hard, soft, and mixed resets.

- Stashing:

  - Make changes to a file and stash them.

  - Make other changes and commit them.

  - Apply your stashed changes.

- Collaborative Work:

  - Fork a repository, create a feature branch, and make changes.

  - Create a pull request and go through a code review process.

- GitHub Actions:

  - Set up a simple GitHub Action to run a test suite on your project.

## Practical Exercise  2
Branch Management:

   - Create a new branch called feature-branch.

   - Make some changes and commit them.

   - Merge the branch back into main and resolve any conflicts.

Revert and Reset:

   - Create a file and make a few commits.

   - Revert one of the commits.

   - Soft reset to the first commit.

Stashing:

   - Stash your changes, make other changes, and then apply the stashed changes.

Collaborate on GitHub:

   - Fork a repository, create a feature branch, make changes, and create a pull request.

GitHub Actions:

   - Create a GitHub Action to automate testing your code.