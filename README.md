# Git Commands Reference

This repository contains a comprehensive list of Git commands and their usage examples. It serves as a quick reference guide for developers to understand and use Git commands effectively.

## Table of Contents

- [Git Commands Reference](#git-commands-reference)
  - [Table of Contents](#table-of-contents)
  - [Basic Git Concepts :-](#basic-git-concepts--)
  - [Configuration](#configuration)
  - [Repository Initialization](#repository-initialization)
  - [Staging and Committing](#staging-and-committing)
  - [Viewing Status and Logs](#viewing-status-and-logs)
  - [Branching](#branching)
    - [Change `Branch` Name after Creation](#change-branch-name-after-creation)
  - [Merging and Rebasing](#merging-and-rebasing)
  - [Remote Repositories](#remote-repositories)
  - [Stashing](#stashing)
  - [Resetting and Restoring](#resetting-and-restoring)
  - [Tagging (LightWeight)](#tagging-lightweight)
  - [Tagging (Anotated)](#tagging-anotated)
    - [Notes on Tags](#notes-on-tags)
  - [Change Repository Name after Creation](#change-repository-name-after-creation)
    - [change the name of your repository from `old-repo-name` to `new-repo-name` on GitHub](#change-the-name-of-your-repository-from-old-repo-name-to-new-repo-name-on-github)
  - [Miscellaneous](#miscellaneous)
  - [Should do and Shouldn't do](#should-do-and-shouldnt-do)
    - [Should Do](#should-do)
    - [Shouldn't Do](#shouldnt-do)
  - [How to Contribute to an Open Source GitHub Repo](#How-to-Contribute-to-an-Open-Source-GitHub-Repo)
  - [Git Docs](#git-docs)

## Basic Git Concepts :-

- **pull**: Fetches changes from a remote repository and merges them into your current branch.
- **push**: Pushes changes from your local repository to a remote repository.
- **merge**: Combines changes from different branches.
- **commit**: Saves changes to the local repository.
- **gitignore**: Specifies files and directories to be ignored by Git.
- **stash**: Temporarily saves changes without committing them.
- **branch**: Creates, lists, or deletes branches in a repository.
- **log**: Displays commit history.
- **reset**: Un-does commits or changes based on different options.

## Configuration

1. **`git --version`**  
   To show the Git version.

   **Example:**
   If you want to check the installed version of Git on your system, you can open your terminal and run the following command:

   ```sh
   git --version
   ```

   This will output something like:

   ```sh
   git version 2.30.0
   ```

   The exact version number will depend on the version of Git installed on your system.

2. **`git config --global user.name "<your_name>"`**  
   Configure the Git username.

   **Example:**
   If you want to set your Git username to "Jane Smith", you would run the following command in your terminal:

   ```sh
   git config --global user.name "John Doe"
   ```

   This command sets the global Git username to "Jane Smith", which will be used for all your Git commits.

3. **`git config --global user.email "<your_email>"`**  
   Configure the Git email address.

   **Example:**
   If you want to set your Git email address to `<johndoe@example.com>`, you would run the following command in your terminal:

   ```sh
   git config --global user.email "johndoe@example.com"
   ```

   This command sets the global Git email address to `<johndoe@example.com>`, which will be used for all your Git commits.

4. **`git config user.name`**  
   Show the configured Git username.

   **Example:**
   If you want to check the username that is currently configured for Git, you would run the following command in your terminal:

   ```sh
   git config user.name
   ```

   This command will output the username that is currently set, for example:

   ```sh
   John Doe
   ```

5. **`git config user.email`**  
   Show the configured Git email.

   **Example:**
   If you want to check the email address that is currently configured for Git, you would run the following command in your terminal:

   ```sh
   git config user.email
   ```

   This command will output the email address that is currently set, for example:

   ```sh
   johndoe@example.com
   ```

## Repository Initialization

1. **`git init`**  
   Initialize a new Git repository.

   **Example:**
   If you want to initialize a new Git repository in your current directory, you would run the following command in your terminal:

   ```sh
   git init
   ```

   This command will create a new `.git` directory in your current directory, which will contain all the necessary files for the Git repository.

## Staging and Committing

1. **`git add <file_name>`**  
   Add a specific file to the staging area.

   **Example:**
   If you have made changes to a file named `index.html` and you want to add it to the staging area, you would run the following command in your terminal:

   ```sh
   git add index.html
   ```

   This command stages the `index.html` file, making it ready to be committed to the repository.

2. **`git add .`**  
   Add all files to the staging area.

   **Example:**
   If you have made changes to multiple files in your project and you want to add all of them to the staging area, you would run the following command in your terminal:

   ```sh
   git add .
   ```

   This command stages all the modified and new files in the current directory and its subdirectories, making them ready to be committed to the repository.

3. **`git commit -m "<message>"`**  
   Commit changes with a message.

   **Example:**
   If you have staged your changes and want to commit them with a message, you would run the following command in your terminal:

   ```sh
   git commit -m "Add new feature"
   ```

   This command creates a new commit with the message "Add new feature", including all the changes that have been staged.

4. **`git commit --amend`**  
   Modify the most recent commit message.

   **Example:**
   If you have just made a commit but realize that you need to change the commit message, you can amend the most recent commit with a new message by running the following command:

   ```sh
   git commit --amend -m "Corrected commit message"
   ```

   This command will replace the most recent commit message with "Corrected commit message". Note that this should be used with caution if the commit has already been pushed to a remote repository, as it rewrites commit history.

## Viewing Status and Logs

1. **`git status`**  
    To show the status of the working directory and staging area.

   **Example:**
   If you want to check the status of your working directory and staging area, you would run the following command in your terminal:

   ```sh
   git status
   ```

   This command will output information about the current branch, any changes that have been staged, changes that have not been staged, and untracked files. For example:

   ```sh
   On branch master
   Your branch is up to date with 'origin/master'.

   Changes to be committed:
     (use "git reset HEAD <file>..." to unstage)
       modified:   index.html

   Changes not staged for commit:
     (use "git add <file>..." to update what will be committed)
     (use "git restore <file>..." to discard changes in working directory)
       modified:   style.css

   Untracked files:
     (use "git add <file>..." to include in what will be committed)
       script.js
   ```

2. **`git log`**  
    Show the commit history.

    **Example:**
    If you want to view the commit history of your repository, you would run the following command in your terminal:

    ```sh
    git log
    ```

    This command will display a list of commits in reverse chronological order, showing details such as commit hash, author, date, and commit message. For example:

    ```sh
    commit 1a2b3c4d5e6f7g8h9i0j
    Author: John Doe <johndoe@example.com>
    Date:   Mon Jan 1 12:34:56 2023 -0700

        Initial commit

    commit 0j9i8h7g6f5e4d3c2b1a
    Author: Jane Smith <janesmith@example.com>
    Date:   Tue Jan 2 14:56:78 2023 -0700

        Add new feature
    ```

3. **`git log --oneline`**  
    Show a brief commit history.

    **Example:**
    If you want to view a brief commit history of your repository, you would run the following command in your terminal:

    ```sh
    git log --oneline
    ```

    This command will display a condensed list of commits, showing only the commit hash and commit message. For example:

    ```sh
    1a2b3c4 Initial commit
    0j9i8h7 Add new feature
    3e4f5g6 Fix bug in script
    ```

4. **`git show head`** or **`git log -1`**  
    Check where the HEAD is pointing.

   **Example:**
   If you want to check the details of the most recent commit where the HEAD is pointing, you can use either of the following commands in your terminal:

   ```sh
   git show head
   ```

   or

   ```sh
   git log -1
   ```

   These commands will display the details of the latest commit, including the commit hash, author, date, and commit message. For example:

   ```sh
   commit 1a2b3c4d5e6f7g8h9i0j
   Author: John Doe <johndoe@example.com>
   Date:   Mon Jan 1 12:34:56 2023 -0700

       Initial commit
   ```

## Branching

1. **`git branch`**  
    List all local branches (default is `master`).

   **Example:**
   If you want to list all the local branches in your repository, you would run the following command in your terminal:

   ```sh
   git branch
   ```

   This command will output a list of all local branches, with an asterisk (*) indicating the currently checked-out branch. For example:

   ```sh
   * master
     feature-branch
     bugfix-branch
   ```

2. **`git branch -r`**  
    List all remote branches.

    **Example:**
    If you want to list all the remote branches in your repository, you would run the following command in your terminal:

    ```sh
    git branch -r
    ```

    This command will output a list of all remote branches. For example:

    ```sh
    origin/HEAD -> origin/master
    origin/master
    origin/feature-branch
    origin/bugfix-branch
    ```

3. **`git branch -a`**  
    Show both local and remote branches.

    **Example:**
    If you want to list all the branches in your repository, including both local and remote branches, you would run the following command in your terminal:

    ```sh
    git branch -a
    ```

    This command will output a list of all local and remote branches. For example:

    ```sh
    * master
      feature-branch
      bugfix-branch
      remotes/origin/HEAD -> origin/master
      remotes/origin/master
      remotes/origin/feature-branch
      remotes/origin/bugfix-branch
    ```

4. **`git branch <branch_name>`**  
    Create a new branch.

    **Example:**
    If you want to create a new branch named `feature-branch`, you would run the following command in your terminal:

    ```sh
    git branch feature-branch
    ```

    This command will create a new branch named `feature-branch` based on the current HEAD. You can then switch to this new branch using `git checkout feature-branch` or `git switch feature-branch`.

5. **`git switch <branch_name>`**  
    Switch to a specific branch.

    **Example:**
    If you want to switch to an existing branch named `feature-branch`, you would run the following command in your terminal:

    ```sh
    git switch feature-branch
    ```

    - **`git add .`** (add branch file)  
    - **`git commit -m "message"`** (commit branch file)  

    Shortcut to create and switch to a branch:  
    - **`git switch -c <branch_name>`**

    ```sh
    git switch -c new-feature-branch
    ```

    **Example:**
    If you want to create a new branch named `new-feature-branch` and switch to it immediately, you would run the following command in your terminal:

    ```sh
    git switch -c new-feature-branch
    ```

    This command will create the `new-feature-branch` and switch to it in one step.

6. **`git branch -d <branch_name>`**  
    Delete a local branch.

    **Example:**
    If you want to delete a local branch named `feature-branch`, you would run the following command in your terminal:

    ```sh
    git branch -d feature-branch
    ```

    _Note_: After deleting the branch locally, it will still exist remotely. To delete the remote branch, you can use the following command:

    ```sh
    git push origin --delete feature-branch
    ```

7. **`git push origin --delete <branch_name>`**  
    Delete a remote branch.

    **Example:**
    If you want to delete a remote branch named `feature-branch`, you would run the following command in your terminal:

    ```sh
    git push origin --delete feature-branch
    ```

    This command will remove the `feature-branch` from the remote repository.

### Change `Branch` Name after Creation

1. **Make sure you are on the branch you want to rename switch to branch:**

   - **`git switch <branch_name>`**

2. **Rename the branch:**

   - **`git branch -m <branch_name>`**

   - **Note- If you haven’t pushed the `branch` yet, you’re done. But if you already pushed and need to update the `remote`**

3. **Pushed the `branch` to `remote`**

   - `git push origin -u <branch_name>`

4. **Delete the old `branch` on `remote` (only if already pushed)**

   - `git push origin --delete <branch_name>`

## Merging and Rebasing

1. **`git merge <branch_name>`**  
    Merge branches.

   **Example:**
   Suppose you have a branch named `feature-branch` that you want to merge into your current branch (e.g., `master`).

   ```sh
   git checkout master
   git merge feature-branch
   ```

## Remote Repositories

1. **`git remote`**  
    Show the current remote repositories.

    **Example:**
    Suppose you want to see all the remote repositories configured for your local repository.

    ```sh
    git remote
    ```

    This command will list all the remote repositories, such as `origin`.

2. **`git remote rename <old_name> <new_name>`**  
    Rename a remote repository.

    **Example:**
    Suppose you have a remote repository named [`origin`]and you want to rename it to [`upstream`]

    ```sh
    git remote rename origin upstream
    ```

    After running this command, the remote repository previously referred to as [`origin`] will now be referred to as [`upstream`]

3. **`git remote remove <repo_name>`**  
    Remove a remote repository.

    **Example:**
    Suppose you have a remote repository named [`upstream`] that you want to remove from your local repository.

    ```sh
    git remote remove upstream
    ```

    After running this command, the remote repository [`upstream`] will be removed from your list of remote repositories.

4. **`git push origin <branch_name>`**  
    Push branch code to the remote repository.

    **Example:**
    Suppose you have made some changes in your local branch named [`feature`]and you want to push these changes to the remote repository named [`origin/feature`]

    ```sh
    git push origin feature
    ```

    After running this command, the changes in your local [`feature`]branch will be pushed to the [`feature`] branch in the remote repository name [`origin/feature`].

5. **`git push origin master`**  
    Push changes to the master branch (avoid pushing directly to master; use merge instead).

    **Example:**
    Suppose you have made some changes in your local [`master`]branch and you want to push these changes to the remote repository named [`origin/master`]

    ```sh
    git push origin master
    ```

    After running this command, the changes in your local [`master`]branch will be pushed to the [`master`]branch in the remote repository [`origin/master`].

6. **`git push origin <local_branch>:<remote_branch>`**  
    Push changes from a local branch to a remote branch.

    **Example:**
    Suppose you have a local branch named `feature-branch` and you want to push its changes to a remote branch named `remote-feature-branch` in the remote repository [`origin/feature-branch`]

    ```sh
    git push origin feature-branch:remote-feature-branch
    ```

    After running this command, the changes in your local `feature-branch` will be pushed to the `remote-feature-branch` in the remote repository [`origin/feature-branch`]

7. **`git fetch <remote>`**  
    Fetch changes from a remote without merging them.

    **Example:**
    Suppose you want to fetch the latest changes from the remote repository named [`origin/master`] without merging them into your local branches.

    ```sh
    git fetch origin
    ```

    After running this command, the latest changes from the remote repository [`origin/master`] will be fetched and stored in your local repository. You can then review these changes before deciding to merge them.

8. **`git pull <remote> <branch_name>`**  
    Fetch and merge changes from a remote branch.

    ```sh
    git pull origin feature-branch
    ```

    _Note_: Resolve merge conflicts manually if they occur.

    _Shortcut_: **`git pull`** (pulls from the current branch).

    ```sh
    git pull
    ```

9. **`git clone <https>`**  
    Clone a specific repository.

    ```sh
    git clone https://github.com/user/repo.git
    ```

10. **`git checkout origin/<branch_name>`**  
    Checkout a branch from a remote repository.

    **Example:**
    Suppose you want to checkout the `main` branch from the remote repository.

    ```sh
    git checkout origin/main
    ```

11. **`git remote -v`**  
    Display the URLs of the remote repositories associated with your local Git repository. It shows both the fetch and push URLs for each remote.

    **Example:**
    Suppose you want to see the URLs of the remote repositories configured for your local repository.

    ```sh
    git remote -v
    ```

    This command will output a list of remote repositories along with their fetch and push URLs. For example:

    ```sh
    origin  https://github.com/user/repo.git (fetch)
    origin  https://github.com/user/repo.git (push)
    ```

12. **`git remote add upstream <owners original repo link>`**  
    This command is used to add a new remote repository to your local Git repository. This is commonly used in forked repositories to keep your fork up-to-date with the original repository. Replace `<owners original repo link>` with the URL of the original repository you forked from. After that, verify the remote upstream has been added using `git remote -v`.

    **Example:**
    Suppose you have forked a repository from `https://github.com/owner/repository.git` and you want to add it as an upstream remote to your local repository.

    ```sh
    git remote add upstream https://github.com/owner/repository.git
    ```

    After adding the upstream remote, you can verify it by running:

    ```sh
    git remote -v
    ```

    You should see output similar to this:

    ```sh
    origin    https://github.com/yourusername/repository.git (fetch)
    origin    https://github.com/yourusername/repository.git (push)
    upstream  https://github.com/owner/repository.git (fetch)
    upstream  https://github.com/owner/repository.git (push)
    ```

## Stashing

1. **`git stash`**  
    Temporarily stash changes to work on something else.

    ```sh
    git stash
    ```

    **Example:**
    Suppose you have made some changes to your code and you need to switch branches without committing those changes. You can stash them with a message:

    ```sh
    git stash save "WIP: refactoring code"
    ```

2. **`git stash list`**  
    List all saved stashes.

    **Example:**
    Suppose you have stashed several changes and you want to see the list of all saved stashes.

    ```sh
    git stash list
    ```

    This command will output a list of all stashes, like so:

    ```sh
    stash@{0}: WIP on main: 1234567 Refactoring code
    stash@{1}: WIP on feature-branch: 89abcdef Adding new feature
    ```

3. **`git stash pop`**  
    Apply the most recent stash and remove it from the stash list.

    **Example:**
    Suppose you have stashed some changes and now you want to apply the most recent stash to your working directory and remove it from the stash list.

    ```sh
    git stash pop
    ```

    This command will apply the most recent stash and remove it from the stash list, effectively restoring your working directory to the state it was in when you stashed the changes.

4. **`git stash apply`**  
    Apply the most recent stash without removing it from the list.

    **Example:**
    Suppose you have stashed some changes and now you want to apply the most recent stash to your working directory without removing it from the stash list.

    ```sh
    git stash apply
    ```

    This command will apply the most recent stash, but it will remain in the stash list for future use.

5. **`git stash drop stash@{0}`**  
    Remove a specific stash by ID.

    **Example:**
    Suppose you have a stash with the ID `stash@{0}` that you no longer need and want to remove it.

    ```sh
    git stash drop stash@{0}
    ```

    This command will remove the stash with the ID `stash@{0}` from the stash list.

6. **`git stash clear`**  
    Clear all stashes.

    **Example:**
    Suppose you have multiple stashes saved and you want to remove all of them at once.

    ```sh
    git stash clear
    ```

    This command will remove all stashes from the stash list, effectively clearing all saved stashes.

## Resetting and Restoring

1. **`git restore <file>`**  
    Discard changes in the working directory (before committing).

    **Example:**
    Suppose you have made changes to a file named `example.txt` and you want to discard those changes.

    ```sh
    git restore example.txt
    ```

    This command will discard any changes made to `example.txt` in the working directory, reverting it to the last committed state.

2. **`git restore --staged <file_name>`**  
    Unstage a file that was previously added to the staging area.

    **Example:**
    Suppose you have staged a file named `example.txt` and you want to unstage it.

    ```sh
    git restore --staged example.txt
    ```

    This command will remove `example.txt` from the staging area, but the changes will remain in your working directory.

3. **`git reset <commit_hash>`**  
    Remove a commit but keep the changes in the working directory.

    **Example:**
    Suppose you have a commit with the hash [`a9bc1d234`] that you want to remove from the commit history but keep the changes in your working directory.

    ```sh
    git reset a9bc1d234
    ```

    This command will remove the commit [`a9bc1d234`] from the commit history, but the changes introduced by that commit will remain in your working directory.

4. **`git reset --hard <commit_hash>`**  
    Remove a commit and the associated changes permanently.

    **Example:**
    Suppose you have a commit with the hash [`a9bc1d234`] that you want to remove from the commit history along with all the changes introduced by that commit.

    ```sh
    git reset --hard a9bc1d234
    ```

    This command will remove the commit [`a9bc1d234`] from the commit history and discard all the changes associated with that commit, effectively reverting your working directory to the state it was in at the specified commit.

5. **`git revert <commit_hash>`**  
    Create a new commit that undoes a previous commit.

    **Example:**
    Suppose you have a commit with the hash [`a9bc1d234`] that introduced some changes you want to undo. You can create a new commit that reverts those changes.

    ```sh
    git revert a9bc1d234
    ```

    This command will create a new commit that undoes the changes introduced by the commit [`a9bc1d234`] effectively reverting the repository to the state it was in before that commit, while preserving the commit history.

6. **`git checkout <commit_hash>`**  
    Checkout an old commit.

    **Example:**
    Suppose you want to checkout an old commit with the hash [`a9bc1d234`]to review the state of the repository at that point in time.

    ```sh
    git checkout a9bc1d234
    ```

    _Note_: This puts you in a detached HEAD state.

7. **`git switch master`**  
    Go back to the master branch.

    **Example:**
    Suppose you are currently on a feature branch and you want to switch back to the [`master`] branch.

    ```sh
    git switch master
    ```

    This command will switch your working directory to the [`master`] branch.

## Tagging (LightWeight)

1. **`git tag <version>`**  
    This command is used to create a lightweight tag for the current commit. Tags are often used to mark release points (e.g., v1.0.0, v2.0.0) in your project's history.

    **Example:**
    To create a tag named `v1.0.1` for the current commit, you would use the following command:

    ```sh
    git tag v1.0.1
    ```

2. **`git tag <version> <commit hash>`**  
    This command is used to create a lightweight tag for a specific commit. This is useful when you want to tag a commit that is not the current commit, such as an earlier commit in the project's history.

    **Example:**
    To create a tag named `v1.2.0` for a specific commit with the hash `a9h0b2`, you would use the following command:

    ```sh
    git tag v1.2.0 a9h0b2
    ```

3. **`git tag -d <version>`**  
    This command is used to delete a tag from your local repository. It does not affect the remote repository.

    **Example:**
    To delete a tag named `v1.2.1` from your local repository, you would use the following command:

    ```sh
    git tag -d v1.2.1
    ```

4. **`git push origin :refs/tags/<version>`**  
    This command is used to delete a tag from the remote repository. The syntax involves pushing an empty reference to the tag, effectively removing it from the remote.

    **Example:**
    To delete a tag named `v1.2.1` from the remote repository, you would use the following command:

    ```sh
    git push origin :refs/tags/v1.2.1
    ```

5. **`git push origin <version>`**  
    This command is used to push a single tag to the remote repository. This is useful when you have created a new tag locally and want to share it with others by pushing it to the remote repository.

    **Example:**
    To push a tag named `v1.5.0` to the remote repository, you would use the following command:

    ```sh
    git push origin v1.5.0
    ```

6. **`git push origin --tags`**  
    This command is used to push all local tags to the remote repository. This is useful when you have created multiple tags locally and want to push them all to the remote repository in one go.

    **Example:**
    To push all local tags to the remote repository, you would use the following command:

    ```sh
    git push origin --tags
    ```

## Tagging (Anotated)

1. **`git log --oneline`**  
    This command is used to display the commit history in a compact format. You can use it to find and copy the commit hash you want to tag.

    **Example:**

    ```sh
    git log --oneline
    ```

2. **`git tag -a <version> <commit hash> -m "tag message"`**  
    This command is used to create an annotated tag for a specific commit. Annotated tags store extra metadata such as the tagger name, email, date, and a message.

    **Example:**
    To create an annotated tag named `v1.0.0` for a commit with the hash `abc123` and a message "Release version 1.0.0: Added new features and fixed bugs", you would use the following command:

    ```sh
    git tag -a v1.0.0 abc123 -m "Release version 1.0.0: Added new features and fixed bugs"
    ```

3. **`git tag -a <version>`**  
    This command is used to create a new annotated tag for the current commit.

    **Example:**
    To create an annotated tag named `v5.5.0` for the current commit, you would use the following command:

    ```sh
    git tag -a v5.5.0
    ```

4. **`git push origin <version>`**  
    This command is used to push a single tag to the remote repository.

    **Example:**
    To push a tag named `v5.5.0` to the remote repository, you would use the following command:

    ```sh
    git push origin v5.5.0
    ```

5. **`git show <tag>`**  
    This command is used to show information about a particular tag, including the commit it points to and the tag message.

    **Example:**
    To show information about a tag named `v5.0.0`, you would use the following command:

    ```sh
    git show v5.0.0
    ```

### Notes on Tags

- **Lightweight Tags:** These are simple tags that are just pointers to a specific commit. They do not store any additional information beyond the commit hash.
- **Annotated Tags:** These tags store additional metadata such as the tagger's name, email, date, and a message. They are useful for providing more context about the tagged commit, such as release notes or version information.

## Change Repository Name after Creation

### change the name of your repository from `old-repo-name` to `new-repo-name` on GitHub

- Let's say you want to change the name of your repository from `old-repo-name` to `new-repo-name` on GitHub after it has already been created and pushed to GitHub. Here are the steps to do that

1. **Change the repository name on GitHub**  
    - Go to your repository on GitHub.
    - Click on the "Settings" tab.
    - Under the "Repository name" section, change the name from `old-repo-name` to `new-repo-name`.
    - Click "Rename" to save the changes.

2. **Check remote after renaming**
    - After renaming the repository on GitHub, you can check the current remote repositories configured in your local repository by running:
  
    ```sh
     git remote -v
    ```

    This will show you the current remote `URLs` associated with your `local repository`.

    ```sh
    origin  https://github.com/your-username/old-repo-name.git (fetch)
    origin  https://github.com/your-username/old-repo-name.git (push)
    ```

3. **Now Just rename the local folder to match the new repository name**

4. **Update the remote URL in your local repository**

   ```sh
   git remote set-url origin https://github.com/yourusername/new-repo-name.git
   ```

   - This command updates the remote URL for the `origin` remote to point to the new repository name.

5. **Verify the remote URL has been updated**

    ```sh
    git remote -v
    ```

    - This will show you the updated remote URLs associated with your local repository.

    ```sh
     origin  https://github.com/your-username/new-repo-name.git (fetch)
     origin  https://github.com/your-username/new-repo-name.git (push)
    ```

## Miscellaneous

1. **`git push origin master`**  
    Push local changes to the master branch (or replace master with a branch name).

    **Example:**
    Suppose you have made some changes to your local repository and committed them. To push these changes to the remote repository's master branch, you would use the following command:

    ```sh
    git push origin master
    ```

2. **`.gitignore`**  
    Create a `.gitignore` file to specify files and directories that should be ignored by Git.

    **Example:**
    Create a `.gitignore` file in your project directory and add the following content to ignore `node_modules` and `log` files:

    ```sh
    # .gitignore
    node_modules/
    *.log
    ```

    **Explanation:**
    - `node_modules/`: This line tells Git to ignore the `node_modules` directory.
    - `*.log`: This line tells Git to ignore all files with a `.log` extension.

    **Usage:**
    After creating and editing the `.gitignore` file, you can add and commit it to your repository:

    ```sh
    git add .gitignore
    git commit -m "Add .gitignore file"
    git push origin master
    ```

## Should do and Shouldn't do

### Should Do

1. **Commit Often**: Make frequent commits with meaningful messages.
2. **Use Branches**: Create branches for new features and bug fixes.
3. **Pull Before Push**: Always pull the latest changes from the remote repository before pushing your changes.
4. **Write Clear Commit Messages**: Use clear and descriptive commit messages to explain what changes were made and why.
5. **Review Code**: Review your code and others' code before merging to ensure quality and consistency.

### Shouldn't Do

1. **Commit Large Changes**: Avoid committing large changes all at once; break them into smaller, manageable commits.
2. **Force Push**: Avoid using `git push --force` as it can overwrite changes in the remote repository.
3. **Commit Sensitive Information**: Never commit sensitive information like passwords, API keys, or personal data.
4. **Ignore Conflicts**: Always resolve merge conflicts carefully and test the code after resolving conflicts.
5. **Use Vague Messages**: Avoid using vague commit messages like "fixed stuff" or "updated code."

## How to Contribute to an Open Source GitHub Repo

### 1) Fork the repository on GitHub (web UI)
- Go to the repo page on GitHub (the upstream repo).
- Click **`Fork`** (top-right). This creates github.com/your-username/<repo>. then click **create Fork**. see below image
<img width="1504" height="1134" alt="fork1" src="https://github.com/user-attachments/assets/61247c74-2d43-463d-9cb7-9b4197a050aa" />


**Now you'll see the copy of this repo will be available in your own profile.**

### 2) Clone your fork locally
- Now choose a folder you work in or create a new one
- Next, clone your fork from your profile
  
  ```sh
  git clone https://github.com/<your-username>/<repo>.git
  ```
- then go inside that folder

  ```sh
  cd <repo>
  ```
### 3) Create a new branch for your fix
- If you check the branches, you'll see only the  `master` branch
  ```sh
  git branch
  ```
  **`output:`**
  
  ```sh
  * master
  ```
- Create a new branch

  ```sh
  git switch -c fix/ssl-python313-compat #You can choose based on what you want to contribute, like fix, features, etc.
  ```
- make the changes and test locally (important)

### 4) Stage and commit your change
- add the change file (example)
  ```sh
  git add h2csmuggler.py
  ```
- commit the message (for example)
  ```sh
  git commit -m "compat: use SSLContext on Python 3.13+ with fallback to ssl.wrap_socket for older Pythons"
  ```
- **Commit message tips:** Short summary first line, optional longer description in commit body (not necessary for this small fix).
   
### 5) Push your branch to your fork
- push the changes
  
  ```sh
  git push origin fix/ssl-python313-compat
  ```
### 6) Open the Pull Request
- Go to your fork on GitHub: https://github.com/<your-username>/<repo>.
- You’ll see a Compare & pull request button for the branch — click it.
  - If not visible: go to the **`Pull requests tab`** → **`New pull request`** → **`set base repository`** to the upstream repo and base branch (main/master), and compare to your branch.
- Fill PR title & body and Submit the PR.

### 7) After opening the PR — what to expect & do
- Maintainers may ask questions or request changes. Respond politely, explain your tests.
- If they request a change, make changes on the same branch, **`git add`** → **`git commit`** → **`git push`** and the `PR` will update automatically.

### 8) Optional niceties (impress reviewers)
- Add a one-line comment in the code near your change, for example: **`# compatibility: Python 3.13 removed ssl.wrap_socket — use SSLContext`**
- Add the test command/example run in the PR description
- If the repo has a CONTRIBUTING.md, mention you followed it.

### 9) Final cleanup (syncing your fork later)
- If upstream advances, keep your fork in sync:
- Switches your current branch to master (the main working branch of your fork).
  
  ```sh
  git switch master
  ```
- Downloads (fetches) all the latest commits and branches from the original project’s repo (called upstream) — but doesn’t merge them yet.
  
  ```sh
  git fetch upstream
  ```
- Merges the latest updates from the original repo’s master branch into your local master branch, keeping your fork up to date.

  ```sh
  git merge upstream/master
  ```
- Uploads (pushes) your newly updated local master branch to your GitHub fork, so it stays in sync online.
  
  ```sh
  git push origin master
  ```
  
- **`In short:`** You’re just updating your fork → to match the latest version of the original repo.

## Git Docs

For more detailed information and additional commands, refer to the official Git documentation: [Git Documentation](https://git-scm.com/doc)
