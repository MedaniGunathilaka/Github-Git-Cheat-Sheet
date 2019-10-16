# GitHub Git Cheat Sheet

Git  is  an open  source  distributed  version  control  system  that  facilitates  GitHub  activities  on  your  laptop  or 
desktop. This cheat sheet will help you with commonly used Git command line instructions for quick reference.

### Catalog

- **[Install Git](#install-git)**
- **[How to use Git](#how-to-use-git)**
- **[Configure tooling](#configure-tooling)**
- **[Create repositories](#create-repositories)**
- **[Make changes](#make-changes)**
- **[Group changes](#group-changes)**
- **[Refactor Filenames](#refactor-filenames)**
- **[Suppress Tracking](#suppress-tracking)**
- **[Save Fragments](#save-fragments)**
- **[Review History](#review-history)**

## INSTALL GIT

### For Windows users
1. Download [Git for Windows Setup](https://git-scm.com/download/win)
2. Install Git through the setup. Usually all configurations can be left in default settings.

### For macOS users
Download [Git for Mac](https://git-scm.com/download/mac)

### For Linux users
#### Debian/Ubuntu
For the latest stable version for your release of Debian/Ubuntu
```bash
$ sudo apt-get update
$ sudo apt-get get install git
```
For Ubuntu, this PPA provides the latest stable upstream Git version
```bash
$ sudo add-apt-repository ppa:git-core/ppa
$ sudo apt update
$ sudo apt install git
```

#### Fedora
For releases up to Fedora 21
```bash 
$ yum install git
```
For Fedora 22 and later
 ```bash
$ dnf install git
```

#### Gentoo
```bash
$ emerge --ask --verbose dev-vcs/git
```

#### Arch Linux
```bash
$ pacman -S git
```

## HOW TO USE GIT

**Windows**<br>
Right click on any location and click `git bash`.

**Linux and Mac**<br>
Open `Terminal` to use git.

## CONFIGURE TOOLING

**Configure user information for all local repositories**<br>

Set the name you want attached to your commit transactions
```bash
$ git config --global user.name "[name]"
```

Set the email address you want attached to your commit transactions
```bash
$ git config --global user.email "[email address]"
```

## CREATE REPOSITORIES

**Start a new repository or obtain one from an existing URL**

Create a new local repository with the specified name
```bash
$ git init [project-name]
```

Download a project and its entire version history
```bash
$ git clone [url]
```

## MAKE CHANGES

**Review edits and craft a commit transaction**

List all new or modified files to be commited
```bash
$ git status
```

Show file differences not yet staged
```bash
$ git diff
```

Snapshot a file in preparation for versioning
```bash
$ git add [file]
```
Snapshot all files of the current directory in preparation for versioning
```bash
$ git add .
```

Unstage the file (reset), but preserve its contents
```bash
$ git reset [file]
```

Record file snapshots permanently in version history
```bash
$ git commit -m "[descriptive message]"
```

## GROUP CHANGES

**Name a series of commits and combine completed efforts**

List all local branches in the current repository
```bash
$ git branch
```

Create a new branch
```bash
$ git branch [branch-name]
```

Switch to the specified branch and updates the working directory
```bash
$ git checkout [branch-name]
```

Combine the specified branch's history into the current branch
```bash
$ git merge [branch-name]
```

Delete the specified branch
```bash
$ git branch -d [branch-name]
```

## REFACTOR FILENAMES

**Relocate and remove versioned files**

Deletes the file from the working directory and stages the deletion.
```bash
$ git rm [file]
```

Removes the file from version control but preserves the file locally.
```
$ git rm --cached [file]
```

Changes the file name and prepares it for commit.
```
$ git mv [file-original] [file-renamed]
```

## SUPPRESS TRACKING

**Exclude temporary files and paths**

Lists all ignored files in this project
```
$ git ls-files --other --ignored --exclude-standard
```

A text file named .gitignore suppresses accidental versioning of files and paths matching the specified paterns
```
*.log
build/
temp-*
```
## SAVE FRAGMENTS

**Shelve and restore incomplete changes**

Temporarily stores all modified tracked files
```
$ git stash
```
Lists all stashed changesets
```
$ git stash list
```
Restores the most recently stashed files
```
$ git stash pop
```
Discards the most recently stashed changeset
```
$ git stash drop
```
## REVIEW HISTORY

**Browse and inspect the evolution of project files**
Lists version history for the current branch
```
$ git log
```
Lists version history for a file, including renames
```
$ git log --follow [file]
```
Shows content differences between two branches
```
$ git diff [first-branch]...[second-branch]
```
Outputs metadata and content changes of the specified commit
```
$ git show [commit]
```
