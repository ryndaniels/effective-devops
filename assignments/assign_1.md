# Verify Local Environment

## Overview

In this exercise each participant configures and tests a local development environment.

## Introduction to Git

## Customize your workstation

* git config --global user.name "YOUR NAME"
* git config --global user.email "YOUR EMAIL ADDRESS"
 

Make a directory that is named as the same as your team name. Create a file that is the same as your first name without any special punctuation. Initialize the repo, and then make a commit.

* mkdir TEAM
* cd TEAM
* touch NAME
* git init
* git add .
* git commit -m "test git"

## Create a GitHub identity

* If you don't already have a github account, create one.
* Browse to http://github.com. Supply a username, email address, and password.
* Free plan is fine. Other plans allow you to have private repositories.

## Share your GitHub identity with your group. 

* Jennifer Davis, iennae
* Katherine Daniels, kdaniels

## Provide GitHub identities to your instructors. (Notetaker)

## Accept invitation to GitHub JoeNGo Organization

* Visit https://github.com/JoeNGo
* Accept invitation.

## Verify access to repo.

* git clone git@github.com:JoeNGo/initial-git-test.git
* git remote -v
* git push origin master
* update README.md with your name
* git status
* git add README.md
* git commit -m "added name"
* git status
* git push origin master

If you run into conflict, pull updates, handle the conflicts, and resubmit edits.

* git pull origin master


### Problems

* Are you getting an "Error: Permission to ORG/REPO denied to user" error?
 * Verify that you have been added to the organization to be able to write to repositories.

