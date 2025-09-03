# Learning Git

## Purpose
Build proficiency and confidence in using Git.


## Requirements
Before you begin, ensure Git is installed and your environment is ready.

### Windows
CLI:
```
winget install --id Git.Git -e --source winget
```

GUI:
- Download and execute the [Git](https://github.com/git-for-windows/git/releases/download/v2.51.0.windows.1/Git-2.51.0-64-bit.exe) installer.

### For Linux
RHEL:
```
dnf install git
```

DEB:
```
apt install git
```

## What is Git
Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

A version control system (VCS) tracks changes to files over time. It allows you to:

- Revert to earlier versions of files or entire projects
- Collaborate with others, even on the same files, without overwriting each other’s work

Git is also considered a software configuration management (SCM) tool. While “VCS” and “SCM” are often used interchangeably, SCM encompasses additional practices beyond version control. A VCS can be used for projects other than software, including books and online tutorials.

## Basic Git Terminology
- __Working tree__: The set of nested directories and files that contain the project that's being worked on.
- __Repository (repo)__: The directory, located at the top level of a working tree, where Git keeps all the history and metadata for a project. Repositories are almost always referred to as repos. A bare repository is one that isn't part of a working tree; it's used for sharing or backup. A bare repo is usually a directory with a name that ends in .git (for example, project.git).
- __Hash__: A number produced by a hash function that represents the contents of a file or another object as a fixed number of digits. Git uses hashes that are 160 bits long. One advantage to using hashes is that Git can tell whether a file has changed by hashing its contents and comparing the result to the previous hash. If the file time-and-date stamp is changed, but the file hash isn’t changed, Git knows the file contents aren’t changed.
- __Object__: A Git repo contains four types of objects, each uniquely identified by an SHA-1 hash. A blob object contains an ordinary file. A tree object represents a directory; it contains names, hashes, and permissions. A commit object represents a specific version of the working tree. A tag is a name attached to a commit.
- __Commit__: When used as a verb, commit means to make a commit object. This action takes its name from commits to a database. It means you are committing the changes you have made so that others can eventually see them, too.
- __Branch__: A branch is a named series of linked commits. The most recent commit on a branch is called the head. The default branch, which is created when you initialize a repository, is called main, often named master in Git. The head of the current branch is named HEAD. Branches are an incredibly useful feature of Git because they allow developers to work independently (or together) in branches and later merge their changes into the default branch.
- __Remote__: A remote is a named reference to another Git repository. When you create a repo, Git creates a remote named origin that is the default remote for push and pull operations.
- __Commands, subcommands, and options__: Git operations are performed by using commands like git push and git pull. git is the command, and push or pull is the subcommand. The subcommand specifies the operation you want Git to perform. Commands frequently are accompanied by options, which use hyphens (-) or double hyphens (--). For example, `git reset --hard`.

## Configure Git
Before Git can track and attribute your changes, you need to set both a username and an email address in your configuration.  These can be set globally for all repositories or locally so that specific credentials are used for individual projects.
```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

Verify settings:
```
git config --list
```
## Working with Git

### Initialize a Repository
Git tracks changes to files within a specific folder. To start using Git, we’ll create a folder for our project (called the *working tree*) and tell Git to begin tracking it by initializing a repository inside that folder.

- Make a new folder to contain your project files.
- Navigate to your project folder using your terminal or command prompt.
- Run the following command to create a new Git repository and set the default branch name to `main`:

```
git init -b main
```

### Staging & Committing Changes
Now that our repository is set up, let’s create a file and commit it so we can see the process in action.

- Create a new file in your project folder (for example, `hello.txt`) and add some content to it
- Stage and commit your changes in one step using:

```
git commit -am "<commit message>"
```

In Git, staging is the step between making changes in your working directory and recording them in the repository’s history with a commit.  It gives you the power to choose what files you want to commit.  In this case we are staging all files that have changes made using the `-a` switch.  The `-m` specifies that you want to pass a commit message.

### Branches
![Github Workflow](../assets/imgs/image.png)
When working on a project, a best practice is to track each new feature or fix in its own **branch**.  Branches allow multiple versions of the code to exist in parallel, so you can develop without interfering with the main codebase or other people’s work.

See what branches already exist
```
git branch -a
```

Create & switch to new branch
```
git checkout -b <new-branch-name>
```
The `-b` allows the creation of a new branch

Confirm your current branch
```
git status
```

## Repository Hosting

## 
GitHub, Gitlab, & Bitbucket are cloud platforms that host your git repository. These simplifies the processes of collaborating by providing shared code storage, web interfaces, command‑line tools, and built‑in workflows.

Let's add our project to github.

- Go to [GitHub](https://github.com) and sign in
- Click New (top‑right) -> fill in the repo name, description, visibility
- Do not initialize with a README, .gitignore, or license (since you already have a local repo)
- Click Create repository

```
git remote add origin https://github.com/<your-username>/<repo-name>.git
```

Verify
```
git remote -v
```

Now make a change and commit.

The change will not show up in github until you push your commits to github that can be done with
```
git push -u origin <branch>
```
The -u (or --set-upstream) flag tells Git to remember the remote/branch pair

### Creating a Pull Request

- Go to [GitHub](https://github.com) and navigate to your repository.
- Switch to the branch that contains the changes you want to merge.
- If your branch is ahead of `main`, GitHub will display a banner such as:  
   `This branch is X commits ahead of main`  
   with a `Contribute` dropdown.
- Click `Contribute` -> `Open pull request`.
- Add a clear, descriptive title and a brief explanation of the changes in the description field.
- Review the comparison to ensure the correct base branch (e.g., `main`) and compare branch are selected.
- Click __Create pull request__ to submit it for review.

## References
- [DevMountain](https://github.com/DevMountain/learn-git)
- [Git First-Time Setup](https://git-scm.com/book/ms/v2/Getting-Started-First-Time-Git-Setup)
- [Intro to Git Microsoft](https://learn.microsoft.com/en-us/training/modules/intro-to-git/)