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

## (Optional) Setting up your Github keys

If you want to skip using your username and password each time, you can follow the steps here to set up your ssh keys:

https://help.github.com/articles/generating-ssh-keys/


## Share your GitHub identity with your group. 

## Provide GitHub identities to your instructors. (Notetaker)

* Jennifer Davis, iennae
* Ryn Daniels, ryndaniels
 
## Accept invitation to GitHub JoeNGo Organization (Everyone)

Start on this step once your group's Notetaker has provided the GitHub identities for your group to your instructors.

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
Replace "TEAM" with your TEAM's name. 

* From the GitHub GUI interface, click on your TEAM-repo 
* From the GitHub GUI interface, click on "Fork" and fork into your personal account.
* cd ~/wd
* git clone https://github.com/USER/TEAM-repo.git
* cd TEAM-repo
* git remote -v
* update README.md with your name and email address.
* git add README.md
* git commit -m "added name"
* git push origin master
* From the GitHub GUI interface, click on the pull request icon.
* Add an appropriate message and "Create pull request"
* Merge the pull request in to your project.

## Discuss and decide on a branching strategy. (Team discussion)

What is the process that you will handle collaboration and branching for your repo?

### Update docs (Notetaker)

* add notes taken during the team discussion to skills.md within the repo.
* update docs/branch.md with the team decided strategy
* update docs/nodes.md with the team's node IP addresses

## Outcome 

You should have an updated TEAM-repo with

* updated README with everyone from your team's name and email address
* forked remote TEAM-repo
* updated docs/branch.md, skills.md

