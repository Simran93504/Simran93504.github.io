# What is Git? <br>
Git is a popular version control system. <br>
It is used for:<br>

Tracking code changes <br>
Tracking who made changes <br>
Coding collaboration <br>

## Working with Git 
- Initialize Git on a folder, making it a Repository
- Git now creates a hidden folder to keep track of changes in that folder
- When a file is changed, added or deleted, it is considered modified
- You select the modified files you want to Stage
- The Staged files are Committed, which prompts Git to store a permanent snapshot of the files
- Git allows you to see the full history of every commit.
- You can revert back to any previous commit.
- Git does not store a separate copy of every file in every commit, but keeps track of changes made in each commit!

# Git Getting Started

## Git Install
You can download Git for free from the following website: https://www.git-scm.com/

## Using Git with Command Line
For Windows, you can use Git bash, which comes included in Git for Windows. For Mac and Linux you can use the built-in terminal.

The first thing we need to do, is to check if Git is properly installed:

``` simran@LAPTOP-N3JFRHHJ MINGW64 ~
$ git --version
git version 2.39.0.windows.2 
```
## Configure Git
Now let Git know who you are.
```
simran@LAPTOP-N3JFRHHJ MINGW64 ~
$ git config --global user.name "Simran"

simran@LAPTOP-N3JFRHHJ MINGW64 ~
$ git config --global user.email "simranies888@gmail.com"
```
## Creating Git Folder
Now, let's create a new folder for our project:

```
simran@LAPTOP-N3JFRHHJ MINGW64 ~
$ mkdir myproject

simran@LAPTOP-N3JFRHHJ MINGW64 ~
$ cd myproject

```
**mkdir** makes a new directory.

**cd** changes the current working directory.

## Initialize Git
Once you have navigated to the correct folder, you can initialize Git on that folder:

```
simran@LAPTOP-N3JFRHHJ MINGW64 ~/myproject
$ git init
Initialized empty Git repository in C:/Users/simra/myproject/.git/
```
## Git Adding New Files
You just created your first local Git repo. But it is empty.

So let's add some files, or create a new file using your favourite text editor. Then save or move it to the folder you just created.
```
simran@LAPTOP-N3JFRHHJ MINGW64 ~/myproject (master)
$ ls
index.html
```
Then we check the Git status and see if it is a part of our repo:
```
simran@LAPTOP-N3JFRHHJ MINGW64 ~/myproject (master)
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html

nothing added to commit but untracked files present (use "git add" to track)
```
## Git Staging Environment
As you are working, you may be adding, editing and removing files. But whenever you hit a milestone or finish a part of the work, you should add the files to a Staging Environment.

Staged files are files that are ready to be committed to the repository you are working on. You will learn more about commit shortly.

```
simran@LAPTOP-N3JFRHHJ MINGW64 ~/myproject (master)
$ git add index.html

simran@LAPTOP-N3JFRHHJ MINGW64 ~/myproject (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   index.html

```
You can also stage more than one file at a time. Let's add 2 more files to our working folder.

```

simran@LAPTOP-N3JFRHHJ MINGW64 ~/myproject (master)
$ git add .

simran@LAPTOP-N3JFRHHJ MINGW64 ~/myproject (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
        new file:   index.html

```
