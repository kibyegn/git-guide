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
# Ubuntu
$ sudo apt-get build-dep git-core

$ wget latest-git-version.tar.gz

$ tar xvzf latest-git-version.tar.gz
$ cd latest-git-version

$ ./configure
$ make
$ sudo make install

$ git --version
$ cd ../;rm -r git-1.7.1 git-1.7.1.tar.gz 

##

git remote add remote_repo git@github.com:user/repo.git


git pull remote_repo branchname
