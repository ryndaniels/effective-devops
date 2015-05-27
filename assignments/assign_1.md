# Verify Local Environment

## Overview

In this exercise each participant configures and tests a local development environment.

## Introduction to Git

## Customize your workstation (Everyone)

* git config --global user.name "YOUR NAME"
* git config --global user.email "YOUR EMAIL ADDRESS"
 

Make a directory that is named as the same as your team name. Create a file that is the same as your first name without any special punctuation. Initialize the repo, and then make a commit.

* mkdir TEAM
* cd TEAM
* touch NAME
* git init
* git add .
* git commit -m "test git"
* git status

## Create a GitHub identity (Everyone)

* If you don't already have a github account, create one.
* Browse to http://github.com. Supply a username, email address, and password.
* Free plan is fine. Other plans allow you to have private repositories.

## Share your GitHub identity with your group. 

## Provide GitHub identities to your instructors. (Notetaker)

* Jennifer Davis, iennae
* Katherine Daniels, kdaniels
 
## Accept invitation to GitHub JoeNGo Organization (Everyone)

Start on this step once you have provided your GitHub identity to your instructors.

* Visit https://github.com/JoeNGo
* Accept invitation.

## Verify access to repo. (Everyone)

* cd ~
* mkdir wd
* git clone git@github.com:JoeNGo/initial-git-test.git
* git remote -v
* update README.md with your name and email address.
* git status
* git add README.md
* git commit -m "added name"
* git status
* git push origin master

If you run into conflict, pull updates, handle the conflicts, and resubmit edits.

* git pull origin master

Why did you run into a conflict?

### Problems

* Are you getting an "Error: Permission to ORG/REPO denied to user" error?
 * Verify that you have been added to the organization to be able to write to repositories.

## Fork team repo (Everyone)

Fork your team's repo into your account, and clone it back to your workstation.

* From the GitHub GUI interface, click on "Fork" and fork into your personal account.
* git clone git@github.com:USER/TEAM-repo.git
* git remote -v
* update README.md with your name and email address.
* git status
* git add README.md
* git commit -m "added name"
* git status
* git push origin master

## Discuss and decide on a branching strategy. (Team discussion)

What is the process that you will handle collaboration and branching for your repo?

### Update docs/skills.md (Notetaker)

* add notes taken during the team discussion to skills.md within the repo.
* update docs/branch.md with the team decided strategy
