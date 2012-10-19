# Abstract

This document serves as a community driven reference point for git users. The 
document lists ways of achieving various things in the wonderful world of git. 
Listed references are both basic git usage and the outright git power usage.

I do not in any way claim ownership of the content in this document. The 
document contains texts obtained from different freely available sources.

## Table of Contents

* [The Git Guide](#guide)
    * [Git Setup] (#setup)


## The Git Guide

<a name="setup">
## Git Setup
### Ubuntu

    $ sudo apt-get build-dep git-core

    $ wget latest-git-version.tar.gz # get it from http://git-scm.com/

    $ tar xvzf latest-git-version.tar.gz
    $ cd latest-git-version

    $ ./configure
    $ make
    $ sudo make install

    $ git --version
    $ cd ../;rm -r git-1.7.1 git-1.7.1.tar.gz 


## Create a new project/repository?

A git repository is simply a directory containing a special .git directory.

This is different from "centralised" version-control systems (like subversion), 
where a "repository" is hosted on a remote server, which you checkout into a 
"working copy" directory. With git, your working copy is the repository.

Simply run git init in the directory which contains the files you wish to track.

For example,

    $ cd <project directory path>
    $ git init

This creates a .git (hidden) folder in the current directory.

To make a new project, run git init with an additional argument (the name of the
 directory to be created):

    $ git init <name of directory>
(This is equivalent to: mkdir <name of directory> && cd <name of directory> && git init)

## Commit Changes
To commit one file. 

    $ git commit <file name>
When this is executed, git will ask for a commit message so as to tell other 
contributors or yourself what has changed. 

To commit All modified files execute the following command. Note that this will 
not commit new files that are yet to be tracked by git. See git 'add' command for
this

    $ git commit -a # -a switch pulls in all modified files

## Untrack a file without deleting it locally
    $ echo <filename> >> .gitignore
    $ git rm --cached <filename>

## Turning on color options (only for git 1.5.5+)
    $ git config --global color.ui "auto"
    
## Adding a remote repository and pulling a specific branch

    $ git remote add <repo name> <repo url>

    $ git pull <remote repo> <branch name>
Note: what 'git pull' does in the background is 'git fetch' and then 'git merge'

To list all branches in the remote branch

    $ git ls-remote --heads <remote repo>

ls-remote command returns SHA1 hash of the latest commit for that reference. The --heads switch lists
only branch names since ls-remote can list tags too.
    
## Branching
Create a local branch.

    $ git branch <new branch>

ProTip: To create a new branch and switch to it automatically;

    $ git branch -b <branch name>

To push the local branch to your remote repository

    $ git push <remote repo> <branch name>

To delete a remote branch

    $ git push <remote repo> <branch name>
or

    $ git push <remote repo> --delete <branch name>

To delete a local branch

    $ git branch -d <branch name>

To merge branches

    $ git merge <merging branch> <branch to be merged>
    
## Reverting to previous commits
To checkout a commit for inspection and discardable experiments. This puts the repo
in a 'detached HEAD' state. You can make changes and commit them or discard them
without impacting any of the branches by performing another checkout.

    $ git checkout <commit hash>
## 

