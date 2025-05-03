# Git Commands Guide

This guide explains the main Git commands.

## Table of Contents
1. [Setting Up Git](#setting-up-git)
1. [Creating a Repository](#creating-a-repository)
1. [Checking the Status](#checking-the-status)
1. [Adding Files](#adding-files)
1. [Deleting Files](#deleting-files)
1. [Committing Changes](#committing-changes)
1. [Creating a New Branch](#creating-a-new-branch)
1. [Link to a Remote Repository (GitHub)](#link-to-a-remote-repository-github)
1. [Pushing Changes](#pushing-changes)
1. [Example of First Initialization of (remote) Repository](#example-of-first-initialization-of-remote-repository)

## Setting Up Git
Before you start using Git, you need to configure your username and email.
I suggest using [Github CLI](https://cli.github.com/):

```sh
gh auth login
```
and follow the instructions. Otherwise,

```sh
git config user.name "Your Name"
git config user.email "your.emailexample.com"
```
This sets your identity for the current Git repositories on your system.
You can add the `--global` flag if you want to configure all the repositories on your system, i.e.,

```sh
git config --global user.name "Your Name"
git config --global user.email "your.emailexample.com"
```
You can see the set configuration simply with
```sh
git config user.name
git config user.email
```
you can add the `--global` flag if you want see the global configuration.

## Creating a Repository
To create a new Git repository,

```sh
git init
```
This initializes a new Git repository in your current directory.

## Checking the Status
To check the current status of your repository:

```sh
git status
```
This shows the status of your working directory and staging area.

## Adding Files

```sh
# To add a new file to your repository
git add <file-name>
# To add multiple files to your repository
git add <file-name-a> <file-name-b>
```
To add all files in the current directory:

```sh
git add .
```
**REMEMBER** to commit the changes!

## Deleting Files
To delete a file from your working directory and index:

```sh
git rm <file-name> --cache
```
**REMEMBER** to commit the changes with meaningful message!

## Committing Changes
To save your changes to the repository:

```sh
git commit -m "Meaningful message that describes the changes you made"
```

## Creating a New Branch
To create and switch to a new branch:

```sh
git checkout -b <branch-name>
```
This creates a new branch and switches to it.

## Link to a Remote Repository (GitHub)
Create a repository on [GitHub](https://github.com) and link it to your local repository:

```sh 
git remote add origin https://github.com/<Your-repository-name>.git
```

## Pushing Changes
To push a branch to the remote repository:

```sh
git push -u origin <branch-name>
```
This command explicitly specifies that you want to push a particular branch (`<branch-name>`) to the remote repository named `origin`.  Default name of remote repository on GitHub is `origin`. 

The `-u` flag in `git push -u origin main` stands for `--set-upstream` and is used to set the remote branch as the upstream branch for the local branch. This means the local branch will be linked to the specified remote branch, allowing you to use shortened commands in the future.   For example:
```sh
git push 
git pull
```

---
---

## Example of First Initialization of (remote) Repository
```sh
# Create and initialize the .git folder
git init
# Add all files of the current folder to the stage
git add .
# Describe your commit with a message (example: "first commit")
git commit -m "first commit"
# Create main/master branch with name "main"
git branch -M main
# Link your local repository to your remote GitHub repository, already created on GitHub (example: "https://github.com/yursds/git_initRepo.git")
# Default name of remote repository on GitHub is origin 
git remote add origin https://github.com/yursds/git_initRepo.git
# Push "origin" to "main"
git push -u origin main
```
