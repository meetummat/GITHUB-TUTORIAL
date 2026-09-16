# Git is a version control system

* Git is a distributed version control system (DVCS) used to track changes to files and manage the history of a project.
* Git helps us maintain different versions of a codebase.
* With Git, we can inspect the history of a repository and return to or work with previous versions when needed.

/--------------------------------------------------------------------------------

# Centralized and Distributed Version Control Systems

## 1. Centralized Version Control System

* The main repository and its history are maintained on a central server.
* Developers generally work with the central server when they need to share or retrieve changes.
* If the central server or the connection to it is unavailable, operations that require the server may not be possible.

## 2. Distributed Version Control System

* Git is a distributed version control system.
* Each clone contains the project's files and its history, so many Git operations can be performed locally without an internet connection.
* Developers can share their commits with a remote repository when they have a network connection.
* A remote repository is commonly used for collaboration, but Git itself does not require a central server.

/--------------------------------------------------------------------------------

# Git/GitHub

## 1. Git

* Git is a fast, reliable, and widely used version control system.
* Git works offline for many operations. For example, we can create commits, create branches, and inspect history without an internet connection. We need a network connection for operations involving a remote repository, such as push and fetch.
* Git tracks changes to files inside a repository.
* `git init` initializes a directory as a Git repository by creating a `.git` directory that stores Git's metadata and history.
* With Git, we can see the history of a repository.

## 2. GitHub

* GitHub is an online platform for hosting Git repositories and collaborating on software projects.

/--------------------------------------------------------------------------------

# How to use Git

* There are mainly three common ways to use Git:
  1. Through Terminal or Git Bash.
  2. Through VS Code.
  3. Through GitHub Desktop.

Git Bash, VS Code, and GitHub Desktop are different interfaces for working with Git. They all use Git underneath.

/--------------------------------------------------------------------------------

# Using Git

* Four fundamental commands for a basic workflow are `git init`, `git status`, `git add`, and `git commit -m "Message"`.
* After modifying files, we normally stage the changes and then commit them.

## Commands in Git

1. `git init` - Initializes an existing directory as a Git repository.

2. `git status` - Shows the state of the working tree and staging area, including modified, staged, and untracked files.

3. `git diff` - Shows the differences between the working tree and the staged version of the files. By default, it shows changes that have not yet been staged.

4. `git diff --cached --stat` - Shows a summary of the changes currently staged for the next commit, including the number of files changed and the number of lines added or removed.

5. `git config --global user.name "Your Name"` - Sets the name Git records in your commits.

6. `git config --global user.email "you@example.com"` - Sets the email address Git records in your commits. This commit identity is separate from GitHub authentication.

7. `git add index.html` - Stages the current changes to `index.html` for the next commit. The file is not physically moved from the working directory.

* We can stage multiple files with one command, for example:
  `git add index.html style.css`

* `git add .` - Stages all eligible changes under the current directory.

8. `git commit -m "Message"` - Creates a commit containing the changes currently staged in the index and records that snapshot in the repository's history.

* We use `git commit -m "Message"` to create a commit with a message describing the changes.

9. `git log` - Shows the commit history, including commit IDs, authors, dates, and commit messages.

10. `git log --oneline` - Shows a shorter version of the commit history, usually with one commit per line. The latest commit is pointed to by `HEAD` and the current branch.

* `git log --oneline -5` shows the latest 5 commits.
* If Git opens a pager, press `q` to return to the terminal.

11. `git restore --staged filename` - Unstages the specified file while keeping its changes in the working tree.

12. `.gitignore` - A file that specifies untracked files and directories that Git should normally ignore. It does not automatically stop tracking a file that has already been committed.

13. `git check-ignore -v "Single User Setup/Github and Github Desktop/filename"` - Checks whether the specified file is being ignored by Git and shows the `.gitignore` rule and file responsible for ignoring it.

14. `.gitkeep` - Git does not track empty directories. `.gitkeep` is a common convention for placing a file inside an otherwise empty directory so that the directory can be represented in the repository.

15. `git branch branchname` - Creates a new branch at the current commit but does not switch to it.

16. `git branch` - Lists the local branches and marks the currently checked-out branch.

17. `git switch branchname` - Switches to the specified existing branch.

18. `git merge branchname` - Merges the specified branch into the current branch. If Git opens Vim for a commit message, `:wq` saves the message and exits Vim. `:wq` itself does not perform the merge.

19. `git branch -d branchname` - Deletes a local branch that has already been merged.

20. `git switch -c branchname` - Creates a new branch and immediately switches to it. It combines branch creation and switching.

21. `git stash` - Temporarily stores supported uncommitted changes so that we can work on something else without committing those changes.

22. `git stash list` - Lists the stashes currently stored in the repository.

23. `git stash pop` - Applies the most recent stash and removes it from the stash list if the operation succeeds.

24. `git stash apply` - Applies the most recent stash but keeps the stash in the stash list.

25. `git tag -a v1.0.0 -m "Message"` - Creates an annotated tag containing additional metadata such as the tagger, date, and message.

26. `git tag v1.0` - Creates a lightweight tag, which is simply a reference to a commit without the additional metadata of an annotated tag.

27. `git tag` - Lists the tags in the repository.

28. `git rebase branchname` - Replays the commits of the current branch on top of the specified branch. Rebase can create a more linear history, but it rewrites commit history and should be used carefully on shared branches.

29. `git clone <repository-url>` - Creates a local copy of a Git repository, including its files and history. A repository can be cloned using an HTTPS or SSH URL. GitHub CLI provides a separate command, `gh repo clone owner/repository`.

30. `git remote -v` - Shows the remote repositories configured for the local repository and their URLs.

* `origin` is the conventional default name given to the remote when a repository is cloned. It is a remote name, not the name of GitHub itself.

31. `git push origin main` - Pushes the local `main` branch's commits to the remote named `origin`, updating its `main` branch.

32. `git branch -M branchname` - Renames the current branch to the specified name. The `-M` option forces the rename if necessary.

33. `git config --global init.defaultBranch main` - Configures Git to use `main` as the default initial branch name when creating new repositories with `git init`.

34. `git pull` - Fetches changes from a remote repository and then integrates those changes into the current branch. Depending on the configuration and options, the integration can use a merge or rebase.

35. `git fetch` - Downloads new commits and updates remote-tracking references such as `origin/main`, but does not integrate those changes into the current branch or modify the working files.

36. `git rm --cached -r SingleUserSetup` - Removes `SingleUserSetup` from Git's index while keeping the actual folder and its files on the computer. This can be useful when a folder was accidentally staged as a repository/reference and we want to re-add its contents normally.

37. `git rm --cached -r -f SingleUserSetup` - Force-removes `SingleUserSetup` from the Git index while keeping the files on the computer. Use this when the normal `git rm --cached -r` is blocked because the staged content differs from the working tree or `HEAD`.

38. `find . -type d -name ".git"` - Searches from the current directory and lists every `.git` directory. This is useful for checking whether there are nested Git repositories.

39. `rm -rf "./SingleUserSetup/.git"` - Removes the `.git` directory inside `SingleUserSetup` while keeping the `SingleUserSetup` folder and its other files. This converts that folder from a separate Git repository into an ordinary folder. Use this only when you intentionally want to remove that nested repository's Git history and metadata.

/--------------------------------------------------------------------------------

# 4 Main Locations When We Use Git

## 1. Working Directory

* The working directory (working tree) contains the files we currently work on.
* After `git clone`, the repository's files are placed in the working directory.
* After `git init`, the existing project files remain in the working directory and Git starts tracking their changes.

## 2. Staging Area

* The staging area (also called the index) contains the changes that are prepared for the next commit.
* We stage changes using `git add`.

## 3. Local Repository

* When we run `git commit`, the staged changes are recorded as a commit in the local repository's history.

## 4. Remote Repository

* A remote repository is a repository hosted somewhere else, commonly on a service such as GitHub.
* We can share our local commits with the remote repository using `git push`.
* If other contributors have pushed changes to the remote, we can use `git fetch` to retrieve the remote updates or `git pull` to fetch and integrate them.

* Git commands allow us to move changes through the workflow:
  `Working Tree → Staging Area → Local Repository → Remote Repository`
* `git status` helps us understand which files have changes and whether those changes are staged.

/--------------------------------------------------------------------------------

# Branching in GitHub

* A branch is a movable reference to a commit. When a new branch is created, it initially points to the current commit. New commits then move that branch forward.
* A branch is not simply a separate copy of the project files.
* Changes made on one branch do not automatically appear on another branch until the histories are integrated, for example through merge or rebase.
* To merge a branch into `main`, first switch to `main` and then run `git merge branchname`.
* If Git opens Vim for a merge commit message, `:wq` saves the message and exits Vim.
* After a branch has been merged and is no longer needed, it can be deleted with `git branch -d branchname`.

* If `main` and another branch both receive commits after they diverge, Git combines their histories based on their common ancestor and the changes made on each branch. It does not simply merge commits according to their chronological order.

/--------------------------------------------------------------------------------

# Best Practices of Branching

1. **One feature = one branch** → Create a dedicated branch for a feature, bug fix, or other isolated change when appropriate.

2. **Protect `main` in collaborative projects** → Teams commonly protect the main branch and use feature branches and pull requests for changes. Direct commits to `main` are possible, especially in small personal projects.

3. **Delete merged branches** → Once a branch is merged and no longer needed, delete it to keep the repository clean.

4. **Use meaningful branch names** → Use clear, descriptive names that indicate the purpose of the branch, such as `feature/login`, `fix/navbar`, or `docs/git-notes`.

5. **Keep branches reasonably short-lived** → Integrate changes regularly to reduce the chance of large conflicts and difficult merges.

* Good branching habits can lead to a cleaner history, easier collaboration, and fewer conflicts.

/--------------------------------------------------------------------------------

# Merge Conflict

* A merge conflict occurs when Git cannot automatically reconcile changes between branches. This often happens when overlapping parts of a file have been changed differently.
* Two people can modify the same file without causing a conflict if Git can combine their changes automatically.
* When a conflict occurs, Git marks the conflicting sections in the file. We must resolve the conflict, stage the resolved file, and complete the merge or rebase.

/--------------------------------------------------------------------------------

# Stashing in Git

* When we are working on something and need to switch to another task before the current work is ready to commit, we can use `git stash`.
* A stash temporarily stores supported uncommitted changes so that we can work on another task.
* Later, we can reapply the changes with commands such as `git stash apply` or `git stash pop`.

* `git stash pop` → apply the stash and remove it if successful.
* `git stash apply` → apply the stash and keep it in the stash list.

/--------------------------------------------------------------------------------

# Tagging in Git

* Tags are references used to mark specific commits, commonly for releases or important points in a project's history.
* There are two common types of tags:

## 1. Annotated Tag

* Stores additional metadata such as tagger, date, and message.
* Annotated tags can also be signed.
* They are commonly used for releases.

```bash
git tag -a v1.0.0 -m "Release version 1.0.0"
```

## 2. Lightweight Tag

* A lightweight tag is simply a reference to a commit.
* It does not contain the additional metadata of an annotated tag.
* It can be useful when a simple pointer to a commit is enough.

```bash
git tag v1.0
```

* Creating a tag locally does not automatically publish it to GitHub. To push a specific tag:

```bash
git push origin v1.0.0
```

/--------------------------------------------------------------------------------

# Git Rebase

* Rebase replays a series of commits onto a new base commit.
* Rebase can produce a more linear project history and can reduce unnecessary merge commits.
* Rebase rewrites the commits that are replayed, so their commit IDs can change.
* Be careful when rebasing commits that have already been shared with other people.

Example:

```text
Before:

A---B---C        main
     \\
      D---E      feature

After `git rebase main`:

A---B---C---D'---E'    feature
```

* After rebasing, the feature branch can be merged into `main` using a fast-forward merge when appropriate.

## Basic Rebase Command

First switch to the branch you want to rebase:

```bash
git switch feature
```

Then rebase it onto `main`:

```bash
git rebase main
```

Here, the commits on `feature` are replayed on top of the latest commit in `main`.

## Interactive Rebase

Interactive rebase lets us inspect and modify a series of commits.

```bash
git rebase -i HEAD~3
```

Common options include:

* `pick` → Keep the commit.
* `reword` → Keep the commit but change its message.
* `edit` → Pause so the commit can be modified.
* `squash` → Combine the commit with the previous commit.
* `drop` → Remove the commit.

## Rebase with the Remote Branch

A common workflow is:

```bash
git fetch origin
git switch feature
git rebase origin/main
```

`git fetch origin` updates our local information about the remote. `git rebase origin/main` then replays the feature commits on top of the fetched `main`.

## Handling a Rebase Conflict

If Git stops because of a conflict:

```bash
git status
```

Resolve the conflicting file in your editor, then stage the resolved file:

```bash
git add filename
```

Continue the rebase:

```bash
git rebase --continue
```

If you want to cancel the rebase:

```bash
git rebase --abort
```

## Rebase vs Merge

Merge:

```bash
git switch feature
git merge main
```

Rebase:

```bash
git switch feature
git rebase main
```

Merge combines the histories and may create a merge commit. Rebase replays the feature commits on top of `main`, creating a more linear history.

## Rebase in GitHub Desktop

GitHub Desktop provides a graphical rebase workflow.

1. Switch to the branch you want to rebase.
2. Select **Branch → Rebase Current Branch**.
3. Select the branch you want to rebase onto.
4. Click **Rebase**.
5. Confirm by clicking **Begin Rebase**.
6. If conflicts occur, resolve them in your editor and continue the rebase.
7. If the branch was already pushed, GitHub Desktop may show **Force push origin** after the rebase.

GitHub Desktop also provides **Pull origin with rebase** when we want to pull remote changes while replaying our local commits on top.

## Rebase in VS Code

In VS Code, we can use the Source Control menu for a pull with rebase:

1. Open **Source Control**.
2. Select **More Actions (...)**.
3. Select **Pull (Rebase)**.
4. VS Code fetches the remote changes and replays the local commits on top.

We can also use the VS Code integrated terminal:

```bash
git fetch origin
git switch feature
git rebase origin/main
```

If a conflict occurs:

```bash
git status
git add filename
git rebase --continue
```

To cancel:

```bash
git rebase --abort
```

## Force Push After Rebase

If a branch that was already pushed is rebased, the remote history may no longer match the local history.

Prefer:

```bash
git push --force-with-lease origin feature
```

`--force-with-lease` is safer than a plain `--force` because it checks whether the remote branch has changed unexpectedly.

## Important Rebase Warning

Avoid rebasing a shared/public branch unless the team has agreed to rewrite its history. Rebase is safest on your own feature branch before other people depend on its commit history.

/--------------------------------------------------------------------------------

# Using GitHub to Host Our Repositories

* GitHub can host Git repositories and provides features for collaboration, such as pull requests, issues, code review, and branch protection.
* `README.md` is a Markdown file commonly used to explain a repository, including its purpose, setup instructions, usage, and other useful information.
* GitHub can help generate a `.gitignore` template for a selected language or framework.
* `git pull` can be used to fetch remote changes and integrate them into the current branch.

/--------------------------------------------------------------------------------

# Using GitHub Desktop

* GitHub Desktop provides a graphical interface for many Git operations such as viewing changes, staging, committing, branching, fetching, pulling, pushing, and creating pull requests.
* VS Code can be used together with GitHub Desktop for editing code while GitHub Desktop handles many Git operations.
* A public repository can generally be viewed by anyone, including users who are not signed in. A private repository requires appropriate access.
* We can create new branches easily and create pull requests when we want to propose changes for another branch.
* A pull request is a proposal to merge changes from one branch (the head branch) into another branch (the base branch). The base branch does not have to be `main`.
* We can also perform certain rebase operations through GitHub Desktop.
* To rebase the current branch, use **Branch → Rebase Current Branch**, choose the branch to rebase onto, and follow the **Rebase → Begin Rebase** steps.
* If conflicts occur during the rebase, resolve them and continue the rebase. If a previously pushed branch was rebased, GitHub Desktop may require **Force push origin** to update the remote.
* **Pull origin with rebase** can be used when we want remote changes to be applied first and our local commits replayed on top.
* `Fetch origin` downloads information about new commits from the remote and updates remote-tracking information. It does not automatically integrate those changes into the current branch.
* The History feature shows the commits in the repository.

/--------------------------------------------------------------------------------

# Forking

* A fork is a personal copy of another user's or organization's repository under your GitHub account.
* If we want to contribute to a repository where we do not have direct write access, we can fork it, clone our fork, create changes, commit them, push them to our fork, and then create a pull request to the original repository.
* The owner or maintainers of the original repository can review the pull request and decide whether to merge it.
* A pull request can be created from the GitHub website after pushing the changes to the fork.

/--------------------------------------------------------------------------------

# Using Git in VS Code

* VS Code provides a graphical interface for many Git operations, including viewing changes, staging, committing, branching, pulling, and pushing.
* We can create or switch branches using the branch controls in VS Code.
* `M` means the file is modified.
* `U` means the file is untracked.
* By clicking the Git/Source Control icon and then `+`, we can stage a file and then commit the staged changes.
* Commit messages should be clear and commonly use the imperative/present form, for example `Add files`, `Fix login bug`, or `Update README`.
* `Sync Changes` in VS Code synchronizes the local branch with its configured remote and may involve pulling and pushing changes, depending on the repository state and settings.
* To pull using rebase in VS Code, open **Source Control → More Actions (...) → Pull (Rebase)**.
* We can also use the VS Code integrated terminal for rebase commands such as `git fetch origin`, `git switch feature`, and `git rebase origin/main`.
* If a rebase conflict occurs, resolve the file, stage it, and run `git rebase --continue`; use `git rebase --abort` to cancel the rebase.
* With a Git Graph extension, we can visualize branches, commits, and their relationships.
* When a merge conflict occurs, VS Code can show the conflicting files and provide options such as accepting the current change, incoming change, both changes, or manually editing the file.
* After resolving a conflict, stage the resolved files and complete the merge or rebase.
* For collaboration, GitHub provides features such as collaborators, issues, and pull requests.
* Issues can be used to describe tasks, bugs, or improvements and assign work to contributors.
* After completing the work, a contributor can create a pull request for review and possible merging.
* Issues can be discussed and closed when the related work is completed.

/--------------------------------------------------------------------------------

# Modern Git Workflow

* GitHub and other development tools can provide AI-assisted features, such as generating suggested commit messages.
* AI-generated commit messages should still be reviewed to make sure they accurately describe the changes.
* When using AI-assisted development, keep changes isolated in branches when appropriate, review the generated code, test it, and commit only changes that you understand and want to keep.

/--------------------------------------------------------------------------------

# Conclusion

* Git is a widely used tool for managing versions and collaborating on codebases.
* Use clear, meaningful commit messages. Imperative/present-style messages such as `Add login page` or `Fix navbar bug` are common.
* Use branches for isolated features, bug fixes, or experiments when appropriate, especially in collaborative projects.
* Store secrets outside source code when possible. During local development, environment variables or `.env` files can be used, and `.env` should normally be included in `.gitignore`.
* Never commit passwords, API keys, tokens, or other secrets to a public repository.
* If a secret is accidentally committed, simply deleting the file is not enough; the exposed credential should be revoked or rotated.
* Always review your changes before committing them.
* Use `git diff` to review unstaged changes and `git diff --cached` to review staged changes before committing.

/--------------------------------------------------------------------------------

